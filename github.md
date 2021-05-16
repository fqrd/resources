#### SSH
ssh-keygen -t rsa -b 4096
Name: path/to/.ssh/id_rsa_github

> check SHA256 publickey

ssh-keygen -lf path/to/.ssh/id_rsa_github.pub

> /.ssh/config (NOT ".config")

    Host github.com
        User git
        Hostname github.com
        IdentityFile path/to/.ssh/id_rsa_github
