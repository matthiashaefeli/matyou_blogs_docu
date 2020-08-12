# Simple solution to download the user data from the DB to excel file (rails)
add to Gemfile
```
gem 'rubyzip', '>= 1.2.1'
gem 'axlsx', git: 'https://github.com/randym/axlsx.git', ref: 'c8ac844'
gem 'axlsx_rails'     
```

```
$ bundle install
```
In the controller add:
```
def index
    @users = User.order('created_at DESC')
    respond_to do |format|
        format.html
        format.xlsx {
            response.headers['Content-Disposition'] = 'attachment; filename="users.xlsx"'
        }
    end
end
```        
Add link in the view
```
<h1>List of products</h1>
<%= link_to 'Download as .xlsx', products_path(format: :xlsx) %>
```
Add file
views/users/index.xlsx.axlsx
and code below
add worksheet to workbook
add titles to the worksheet with add row
add contents to the sheet with add row
```
wb = xlsx_package.workbook
wb.add_worksheet(name: "Users") do |sheet|
    sheet.add_row ["Name", "Email", "Tel"]
    @users.each do |user|
    sheet.add_row [user.name, user.email, user.tel]
    end
end
```       
Boot up the server, navigate to the index page, and click on the Download link

and thats it !!