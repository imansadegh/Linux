# SSH Services(Secure Shell)
Important Commands line
connect to another server with ssh:
ssh username@host_ip_address -p port_number   (Defualt Port is 22)
    Switches:
        -v      verberos
## Confige file ssh
vim /etc/ssh/sshd_config
if you change the defualt port , with this command you can see Listen port:
netstat -ntlp
after change the defualt port you need to config SE_Linux but now we don't have enough time to say about it, now with this command we turn_off SE_Linux:
setenforce 0
and:
vim /etc/selinux/config
on this file change it:
SELINUX=disabled

## Confige SSH_KEY
with this command authentication key generation, management and conversion
$ ssh_keygen
create public/private key in this location
/root/.ssh/id rsa
after that with this command you can copy public_key from server to your host:
$ ssh -copy-id USER_NAME@IP_ADDRESS
with this command you can remove all of keys on your host:
$ rm -fr .ssh/id rsa*