# docker-compose-prestashop
The easiest way to install prestashop with multiple containers and persistent data thanks to docker-compose

Dockerfile is coming from daedelus/prestashop-web 
The initial solution coming from Jonathan Temlett and  is here :  http://www.mytutorials.co.za/2015/07/creating-prestashop-environment-in.html

To use it with docker-compose :
1. Pull this repo on your server

2. Fill in the docker-compose.yml with your own data

3. Launch the following command : docker-compose up
   Docker is normally building the container prestashop and start to run both prestashop and db container

4. Open your browser and go on your site

5. Follow the instruction : please fill in with the mandatory  
     variable :
     HOST: mysql
    PASSWORD: <yourrootpassword>
    As you like for the remaining item

 !!!! Prestashop ask you to create a database because it find nothing at all. Without this  question, do it directly in command line with docker exec (cf tuto daedelus)

 6. After installing, go into your running container to change the admin folder name et delete the install folder :

 docker exec -it <yourrunningprestashopcontainer> /bin/bash
 You are now in your runngin container

 Command to execute :
 mv /var/www/site/prestashop/admin /var/www/site/prestashop/admin231212321
 rm -rf /var/www/site/prestashop/install
