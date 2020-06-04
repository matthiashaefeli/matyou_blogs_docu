# Yarn uninstall and install

I had problems with yarn the other day, and i wanted to uninstall and install yarn again

This worked for me:

```
brew uninstall --force yarn
npm uninstall -g yarn
yarn -v
```
=> 1.1.0

```
which yarn
```
=> /usr/local/bin/yarn

```
rm -rf /usr/local/bin/yarn
rm -rf /usr/local/bin/yarnpkg
which yarn
```
=> yarn not found
```
brew install yarn
brew link yarn
yarn -v
```
=> 1.22.4

