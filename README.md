# yarn-cookbook
[![Chef cookbook](https://img.shields.io/cookbook/v/yarn.svg?style=flat-square)]()
[![license](https://img.shields.io/github/license/aspyatkin/yarn-cookbook.svg?style=flat-square)]()  
**WIP**  
Chef cookbook to install [Yarn](https://yarnpkg.com/) package manager.

## Recipes

### yarn::default

Install or *upgrade* (default action) Yarn (it depends on `node['yarn']['upgrade_package']` attribute, which defaults to `true`).

### yarn::install_package

Install Yarn.

### yarn::upgrade_package

Install the latest version of Yarn.

## Resources

### yarn_install

Install all dependencies for a project.

``` ruby
yarn_install '/var/projects/test' do
  user 'vagrant'
  action :run
end
```

### yarn_run

Run a defined package script.

```ruby
yarn_run 'knex' do
  user 'vagrant'
  dir '/var/projects/test'
  args ['migrate:latest']
  action :run
end
```

## Disclaimer
1. This cookbook is under development. Use at your own risk.
2. This cookbook doesn't install Node.js itself, it presupposes that Node.js is installed on your system. Any method of installing Node.js on your system should work.
3. This cookbook works only on Ubuntu (14.04 has been tested so far)

## License
MIT @ [Alexander Pyatkin](https://github.com/aspyatkin)
