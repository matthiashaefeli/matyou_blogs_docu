# Make your tables sortable
This is your table
```
<table class="yourclass">
    <thead>
        <tr>
            <th>name</th>
            <th>lastname</th>
            <th>email</th>
            <th>city</th>
        </tr>
    </thead>
    <tbody>
        <% for user in @users %> 
        <tr>
            <td><%= user.name %></td>
            <td><%= user.lastname %></td>
            <td><%= user.email %></td>
            <td><%= user.city %></td>
        </tr>
        <% end %>
    </tbody>
</table>
```       
Add this to your user controller
```
class UsersController < ApplicationController
    helper_method :sort_column, :sort_direction
    
    def index
        @products = Product.order(sort_column + " " + sort_direction)
    end
    
    # ...
    
    private
    
    def sort_column
        User.column_names.include?(params[:sort]) ? params[:sort] : "name"
    end
    
    def sort_direction
        %w[asc desc].include?(params[:direction]) ? params[:direction] : "asc"
    end
end
```       
Ad this to your application_helper.rb
```
def sortable(column, title = nil)
    title ||= column.titleize
    css_class = column == sort_column ? "current #{sort_direction}" : nil
    direction = column == sort_column && sort_direction == "asc" ? "desc" : "asc"
    link_to title, {:sort => column, :direction => direction}, {:class => css_class}
end
```        
Change your titles in the table
```
<th><%= sortable "name", "name" %></th>
<th><%= sortable "last", "lastname" %></th>
<th><%= sortable "email", "email" %></th>
<th><%= sortable "city", "city" %></th>
```        
Add this to your css
```
.yourclass th .current {
    padding-right: 12px;
    background-repeat: no-repeat;
    background-position: right center;
}
    
.yourclass th .asc {
    background-image: url(/images/up_arrow.gif);
    }
    
.yourclass th .desc {
    background-image: url(/images/down_arrow.gif);
}
```       
and thats it !!