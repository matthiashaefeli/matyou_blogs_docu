# How to write a test with a csv file

If we have a csv file importer how would we test it?

First we could create a csv file with test data to the spec/support folder and using this file to upload and test, but what happens if we have different columns with different tests? everytime we test a different column or row we would have to create a new file.

we can add an empty file to somewhere and before each test we add the row we need to test. At the end of the test we delete the temp file again.

```
# frozen_string_literal: true

require 'rails_helper'

describe FileImport do
  let(:importer) { FileImport.new }
  let(:file) { "#{Rails.root}/spec/support/test_file.csv" }
  let(:header) { "User,active,date,somethingelse" }
  let(:row1) { "'John Do',true,01/01/2020,10" }
  let(:row2) { "'',true,01/01/2020,10" }
  let(:row3) { "'John Do',false,01/01/2020," }

  describe 'import of data' do
    after(:each) { File.delete(file) }

    it 'imports file successfully' do
      rows = [header, row1]
      CSV.open(file, 'w') do |csv|
        rows.each do |row|
          csv << row.split(',')
        end
      end

      expect(importer.import_csv(file)).to eq 'done'
    end

    it 'returns error' do
      rows = [header, row3]
      CSV.open(file, 'w') do |csv|
        rows.each do |row|
          csv << row.split(',')
        end
      end

      expect(importer.import_csv(file)).to eq 'error'
    end
  end
end
```