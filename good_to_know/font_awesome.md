# Fontawesome Webpacker and rails 6

import fontawesome

```
$ yarn add @fortawesome/fontawesome-svg-core
$ yarn add @fortawesome/free-solid-svg-icons
$ yarn add @fortawesome/free-brands-svg-icons
$ yarn add @fortawesome/free-reguar-svg-icons
```

import fontawesome in application.js

```
import { library, dom } from '@fortawesome/fontawesome-svg-core'
import { fas } from '@fortawesome/free-solid-svg-icons'
import { faTwitter } from '@fortawesome/free-brands-svg-icons'
import { far } from '@fortawesome/free-regular-svg-icons'

library.add(far, fas, faTwitter)

dom.watch()
```
