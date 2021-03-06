# Liferay Setup Script
Multi platform script for setting up a Liferay Portal

## What it does?
1. downloads Liferay bundle (if it doesn't exists yet) with the following command
```shell
blade gw initBundle
```
2. gets the properties from the selected environment, sets liferay.home and database url name properties and inserts it in a `portal-ext.properties` file inside `bundles` folder

## Requirements
- python ^3
- blade ^4.0.9 

## Usage
1. clone the repository inside a Liferay Gradle Workspace
```shell
git clone https://github.com/marcosblandim/liferay-setup-script.git
```
2. execute it with the default values
```shell
python liferay-setup-script
```
- usage example
```shell
python liferay-setup-script --log-level DEBUG -d lportal -e dev /some/liferay/gradle/workspace/path
```
> use the following command to get help
```shell
python liferay-setup-script --help
```

## Future improvements
- make it possible to pass all fields available in wizard setup, even the database driver (see portal-impl properties file)
  - have default value for all fields
- improve docs
  - [usage](#usage)
- make it works for many versions (currently only works on 7.3)
- add the option to create the database and the portal in a docker
- improve logging
- external bundle option -> use bundle located outside the workspace
    - validate `liferay.workspace.home.dir` inside `gradle.properties` file
- flag for reseting `bundles` folder
- implement testing
- fix args help text
- validate workspace folder (https://github.com/liferay/liferay-blade-cli/blob/feaeddf8251999c262e3004cc8675bc82eb09c7e/cli/src/main/java/com/liferay/blade/cli/gradle/GradleWorkspaceProvider.java#L250)
- generate executable
- use some commit name validator
- dynamically check if blade is in the latest version
- add 3 missing properties: company.default.name (default site name), default.admin.first.name and default.admin.last.name (default admin first and last name)
- should the wizard env have de dev properties?
