 # Host a website using Docker and Nginx <br/>
 - Login to your AWS account and download your passkey and launch the EC2 instance.  
- Launch PuTTY and add the IP address from instance and add key pair file and open the PuTTY terminal.
- Login to the OS by writing "ubuntu"
- After that I have to install docker in my OS .<br/>
- Now install Docker using following command:

 https://github.com/ShubhamTatvamasi/docker-install/raw/master/docker-install.sh

- Type following command to avoid using sudo always 

newgrp docker

- Then type (This will provides a list of the Docker containers on your machine)

docker ps

- You can check your docker version by typing:

docker --version

- Now, to use Nginx in our container use the following commands:

docker pull nginx


docker run --name docker-nginx -p 80:80 nginx

### Now you can type your instance's IP and see Nginx default web page.  
- Use following command to stop the container from running:

ctrl + c

- Use following command to reveals that the Docker container has been exited:

docker ps -a

- Use following command to see container's ID

docker run --name docker-nginx -p 80:80 -d nginx

- Use following command to see new information about container:

docker ps

- Use following command to stop the container:

docker stop docker-nginx

- Then remove default Nginx page and create new custom html file using following commands:

docker rm docker-nginx

mkdir -p ~/docker-nginx/html

Now navigate to file created:

cd ~/docker-nginx/html

- Now create a index.html and write a html code on code editor:

index.html

- Now write your code and save the file.
Then connect the file to instance:

docker run --name docker-nginx -p 80:80 -d -v ~/docker-nginx/html:/usr/share/nginx/html nginx

### Now go and check the link...
### Great! You did it.
