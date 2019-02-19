# Install
```
git submodule  update --init
git submodule foreach 'test -e composer.json && composer install --ignore-platform-reqs || :'
git submodule foreach 'test -e package.json && npm install --ignore-platform-reqs || :'
```

## Update projects
```
git submodule foreach git pull --rebase
```

## Outdated deps
```
git submodule foreach 'test -e composer.json && composer outdated -D || :'
git submodule foreach 'test -e package.json && npm outdated || :'
```

## Grep in projects
Create a `~/.ackrc` file containing
```
--ignore-dir=.idea/
--ignore-dir=node_modules/
--ignore-dir=vendor/
--ignore-dir=bower_components/
--ignore-dir=bower_files/
```

Grep files
```bash
# grep php files
ackgrep --php expression

# grep all files
ackgrep expression
```

## Adding a project
```sh
git submodule add ssh://git@gitlab.easyflirt.com:222/prelinker-click-logger/bridghit.git bridghit
```