add connection peers
`vim /etc/yggdrasil/yggdrasil.conf`

and you can edit to listen to all ports

to run `yggdrasil -useconffile /etc/yggdrasil/yggdrasil.conf`

if you got this problem `Admin socket failed to listen: listen unix /var/run/yggdrasil/yggdrasil.sock: bind: no such file or directory`

do
 - `mkdir /var/run/yggdrasil`
 - `chown yggdrasil /var/run/yggdrasil/`

now it should work :)

to create connection
`nc -6 -l -p [port number]`

this creates a simple network listener that waits for incoming connections on port 12345 using IPv6.
    nc = netcat (network utility)

    -6 = use IPv6 only

    -l = listen mode (wait for connections)

    -p 12345 = use port 12345

on another computer run `nc -6 [YGGDRASIL-IP] 12345`

