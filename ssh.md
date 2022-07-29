Multiple Identity Configuration
-------------------------------
It is very common to have multiple SSH identities linked to the same user
account (e.g., GitHub SSH credentials and corporate SSH credentials for
an internal server).  One way to do this is the following
- Generate OpenSSH authentication keys for each of the two systems - this should
  lead to two key pairs which will be found somewhere like `${HOME}/.ssh`.  One
  would expect to see something like

```bash
$ find ${HOME}/.ssh -type f -iname 'id*'
/home/gmcastil/.ssh/id_rsa_foo.pub
/home/gmcastil/.ssh/id_rsa_foo
/home/gmcastil/.ssh/id_rsa_bar.pub
/home/gmcastil/.ssh/id_rsa_bar
```

Each of the public keys will be linked to an email address of some sort and will
need appropriate entries in `${HOME}/.ssh/config`, which should look something
like
```bash
$ cat ${HOME}/.ssh/config
# Foo SSH Config
Host					foo
HostName				foo.baz.com
PreferredAuthentications		publickey
IdentityFile				~/.ssh/id_rsa_foo

# Bar SSH Config
Host					bar
HostName				bar.baz.com
Port					7999
PreferredAuthentications		publickey
IdentityFile				~/.ssh/id_rsa_bar
```
where in this example. one of the hosts is operating a BitBucket server of some
sort that is listening on TCP port 7999. In this example, one would then use the
host names directly such as `git clone git@bar:some_user/some_repo.git
some_repo` to clone a git repository.

There are probably other ways to do this as well.
