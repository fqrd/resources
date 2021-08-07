#### SSH

    ssh-keygen -t rsa -b 4096

> Custom name: ~/.ssh/id_rsa_example

#### Check SHA256 publickey

    ssh-keygen -lf ~/.ssh/id_rsa_example.pub

#### Custom key name configuration

> touch ~/.ssh/config (NOT ".config")

    Host github.com
        User git
        Hostname github.com
        IdentityFile ~/.ssh/id_rsa_example

### Submodules

    git clone git@github.com:fqrd/_libft.git --recursive

> if forgot the recursive, once cloned use

    git submodule update --init