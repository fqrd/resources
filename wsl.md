> WSL2 requires virtualization which is only available in W10 Entreprise, Pro and Education

#### Change default user/username after wsl installation (in cmd)

(from: https://askubuntu.com/questions/816732/how-to-change-default-user-in-wsl-ubuntu-bash-on-windows-10)

    wsl.exe -u root
    sudo usermod -l newUsername oldUsername
    sudo usermod -d /home/newHomeDir -m newUsername

> But honestly, you're better off reinstalling the distro, it would prevent permissions issues.