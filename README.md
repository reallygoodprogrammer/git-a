# *git-a*ccount manager

A tool for easily commiting and interacting with remote
repos as different git accounts without manual configuration
on a per repo basis.

`git-a` creates a directory at ~/.git-a that will contain
a config file for managing git-a account data. An example
file is provided in [config\_example](config_example).

# Usage

```
usage: git-a [ add | remove | account-name git-command(s) ]
options:
    -c FILE     spcify a custom config file to use
    -D          delete the ~/.ssh/config entry on account remove
    -h          display a usage message
```

# Example

Here I create and use a new account called `myaccount` with 
`user.name=reallygoodprogrammer`, `user.email=myemail@email.com`, 
and a key to be added in a new `$HOME/.ssh/config` entry for use
with git.

```bash
git-a add myaccount reallygoodprogrammer \
        myemail@email.com /path/to/ssh/key

...

# using the new account 'myaccount':

git-a myaccount config user.name
reallygoodprogrammer
git-a myaccount config user.email
myemail@email.com

git-a myaccount commit -m "commiting as myaccount!"
git-a myaccount push
```
