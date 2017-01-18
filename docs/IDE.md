# IDEA/WebStorm configuration for Semifour-Standard Style

##1. Set the code style
 - Find your IDE config dir (Usually `~/Library/Preferences/IntelliJIdea14`. [Or check here][webstorm-2]).
 - Create the `config_dir/codestyles` dir if it's not already there.
 - Copy the [SemifourStandard][semifour-standard-cs] file into the `codestyles` dir.
 
##2. Install `eslint` and `eslint-config-semifour-standard`
 - Run these 2 commands:
   - `npm install --global eslint eslint-config-standard eslint-config-standard-jsx eslint-plugin-promise eslint-plugin-react eslint-plugin-standard eslint-config-semifour-standard`
   - `echo '{"extends": ["semifour-standard", "standard-jsx"]}' > ~/.eslintrc`
 
##3. Set IDE preferences
 - Restart the IDE and open a Settings/Preferences screen
 - Under `Editor > Code Style > JavaScript` change `Scheme` to `Standard`
 - Under `Languages & Frameworks > JavaScript > Code Quality Tools > ESLint` select `Enable`. You may need to set `ESLint Package` to `/usr/local/lib/node_modules/eslint`


[semifour-standard-cs]: https://github.com/kevsul/semifour-standard/blob/master/docs/SemifourStandard.xml
[webstorm-2]: https://www.jetbrains.com/help/phpstorm/2016.1/directories-used-by-phpstorm-to-store-settings-caches-plugins-and-logs.html