# Naming conventions

## Role names
Begin with the phrase based on OS for which are written.
Examples:
- for Debian + Kubernetes
```
debsible.k8s-`role name`
```
- for CentOS + Kubernetes
```
centsible.k8s-`role name`
```
## Directory structure
Roles that are intended to be used as dependencies, should be stored in the `roles-dependencies` directory.
Example:
```
roles-dependencies/centsible.dep-yum
```
Collection of roles that are dedicated to one, main topic, should be grouped into a directory named after that topic.
Example:
```
centsible.docker
  centsible.docker-repository
  centsible.docker-install
```
## Tasks names
Begin with lowercase placed in a single quotation marks, in an imperative mode.
Example:
```
task: 'think of /etc/what/you/do'
```
## Variables names
Are prefixed with role name and two underscores. Names consisting of two or more words should be split by single underscore.
Example:

If role is named:
```
debsible.eat_cookies
```
then variable should be named:
```
eat_cookies__`variablename`
```
## Variables definition
The variables that are not intended to be changed or overwritten have to be placed in
```
vars/main.yml
```
The variables that can or should be overwritten have to be placed in
```
defaults/main.yml
```
## YAML files
If possible, all the YAML files should have
```
main.yml
```
name in roles and '.yml' extension.

There also should be a line break after three dashes in first line.
## Requirements
The requirements that have to be installed in CI/CD in order to pass validation/testing, should be added to `requirements.txt`
## Commit message
Has to answer the question "This commit will?"
eg. "Make you a little bit smarter"
## Pull requests
Should have the same name as its ticket.
In the description there should be an answer to the question:
Example:
  This commit will:
  "`keyword` `description of what your code do`"

eg. This commit will:
    "improve your dancing moves"
