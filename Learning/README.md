# SSH Services(Secure Shell)
Important Commands line<br>
connect to another server with ssh:<br>
ssh username@host_ip_address -p port_number   (Defualt Port is 22)<br>
    Switches:<br>
        -v      verberos<br>
## Confige file ssh
vim /etc/ssh/sshd_config<br>
you can change anything in depnds on ssh service, my configuration of ssh is this:<br>
port number change it<br>
LogLevel VERBOSE<br>
PermitRootLogin without-password<br>
MaxAuthTries 3<br>
MaxSessions 3<br>
PasswordAuthentications yes<br>
GSSAPIAuthentication no<br>
AllowAgentForwarding no<br>
AllowTcpForwarding no<br>
X11Forwarding no<br>
UseDNS no<br>
Subsystem    sftp   /us/libexec/openssh/sftp-server -l  INFO<br>
if you change the defualt port , with this command you can see Listen port:<br>
netstat -ntlp<br>
after change the defualt port you need to config SE_Linux but now we don't have enough time to say about it, now with this command we turn_off SE_Linux:<br>
setenforce 0<br>
and:<br>
vim /etc/selinux/config<br>
on this file change it:<br>
SELINUX=disabled<br>

## Confige SSH_KEY
with this command authentication key generation, management and conversion<br>
$ ssh_keygen<br>
create public/private key in this location<br>
/root/.ssh/id rsa<br>
after that with this command you can copy public_key from server to your host:<br>
$ ssh -copy-id USER_NAME@IP_ADDRESS<br>
with this command you can remove all of keys on your host:<br>
$ rm -fr .ssh/id rsa<br>
You can start the SSH daemon in debug mode to get more detailed debugging output. This might help you identify the exact point where the daemon is encountering an issue:<br>
sudo /usr/sbin/sshd -Dd
