# IRB command line

create file: ~/.irbrc and add code below:

```
IRB.conf[:PROMPT][:CUSTOM] = {
 :PROMPT_I => "#{RUBY_VERSION} :%03n > ", # default prompt
 :PROMPT_S => "#{RUBY_VERSION} :%03n%l> ", # known continuation
 :PROMPT_C => "#{RUBY_VERSION} :%03n > ",
 :PROMPT_N => "#{RUBY_VERSION} :%03n?> ", # unknown continuation
 :RETURN => " => %s \n",
 :AUTO_INDENT => true
}
IRB.conf[:PROMPT_MODE] = :CUSTOM
IRB.conf[:AUTO_INDENT] = true
```