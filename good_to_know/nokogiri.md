# Can't install Nokogiri

Nokogiri is an XML/HTML/CSS parser. So if you want to programatically read or edit an XML document Nokogiri is the way to go.

If you have this error with bundle install:


ERROR:  Error installing nokogiri:
    ERROR: Failed to build gem native extension.


Try to install nokogiri
```
gem install nokogiri -v 1.8.2
```
if this is not working, open Xcode and, from the menu XCode -> Preferences update your Command Line Tools (Xcode 8.0). Then do:
```
bundle config build.nokogiri --use-system-libraries=true --with-xml2-include="$(xcrun --show-sdk-path)"/usr/include/libxml2
bundle install
```
or just do:
```
gem install nokogiri -v 1.8.2 -- --use-system-libraries=true --with-xml2-include="$(xcrun --show-sdk-path)"/usr/include/libxml2
```
