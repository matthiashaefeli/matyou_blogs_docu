# How to load a file into IRB

Run this code in the directory where the file is.

```
irb -r ./your_file.rb
```
Or

```
irb -I . -r your_file.rb
```
The -I option is necessary to add the current directory (.) to ruby's load path

Or

in the irb

```
require './your_file.rb'
```
Or

```
load './your_file.rb'
```
