## Ports

### Change port number

    sudo nano /etc/ssh/sshd_config
    Port 1222

(anything above 1024(?) lower are system reserved)

### Update firewall (ufw)

    sudo ufw default deny incoming
    sudo ufw default allow outgoing
    sudo ufw allow 549/tcp comment 'SSH'
    sudo ufw allow http
    sudo ufw allow https
    sudo ufw enable

    sudo ufw status

	sudo ufw reload


## Screens

### Creates a new screen session in which you can work

    screen 

### Exits the current screen

    CTRL+A D

### Returns to the previous screen (OR) displays the pid (2040.pts-0.ubuntu) if multiple screen opened

    screen -r

### Display screen list (like above in case of multiple screens)

    screen -ls

### Return to a selected screen

    screen -r 2040.pts-0.ubuntu

### Name a screen

    CTRL+A A
	:sessionname name_you_want

### Rename a screen

    CTR+A :
    sessionname name_you_want

### Kill a screen

    CTRL+D