# vpn

## openconnect ocserv
# Clone 
clone the repository from [github](https://github.com/wppurking/ocserv-docker)
```
cd ~;
git clone https://github.com/wppurking/ocserv-docker.git;
docker run -d --privileged --name ocserv-docker -v ~/ocserv-docker/ocserv:/etc/ocserv -p 443:443 wppurking/ocserv
```
now you can connect to ocserv at your server's ip at port 443 like $ipaddress:443
# diffrent port
if you want to run ocserv on a another port like 4443 you should run the container with below command
<!-- ```
cd ~;
sed "s/#udp-port = 443 /udp-port = 4443/g" ocserv-docker/ocserv/ocserv.conf
``` -->
```
docker run -d --privileged --name ocserv-docker -v ~/ocserv-docker/ocserv:/etc/ocserv -p 4443:443 wppurking/ocserv
```
now you can connect to ocserv at your server's ip at port 443 like $ipaddress:4443

# User
There are two active user in the cloned repository\
you can test your conection with them\
wyatt:616\
holly:525\
you can create new usernames with The following command
```
docker exec -it $(docker ps -a | grep vpn_run | awk '{print $1}') ocpasswd yourname
```
# Note 
You may need to open your firewall ports
