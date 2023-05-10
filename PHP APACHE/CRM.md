### Tutorial: Creating CRM Server using  Dockerfile

* Sign into the Azure Portal and Create one Ubuntu virtual machine.
* After creation of Virtual machine Install Docker on the virtual machine using below Commands
    ```curl -fsSL https://get.docker.com -o get-docker.sh```
    
    ```sh get-docker.sh```
*  After installing Docker add user to the Docker group. using ```sudo usermod -aG docker ubuntu```.  (in my case I am adding ubuntu user to the docker group). After adding user to the docker group exit from the VM and relogin again.
* Check ```docker info``` then you will able to see the server information.

* As per our need we need PHP and APACHE to run our CRM server. instead of taking ubuntu as a base image here I am taking base image as  ```php:8.0-apache``` and then i will try to create Dockerfile as per my need.


* Here is the sample Dockerfile.

```Dockerfile
FROM php:8.0-apache
RUN echo "<?php phpinfo(); ?>" > /var/www/html/info.php && \
    echo '<h1> Hi Chandra this is KrishnaPrasad </h1>' > /var/www/html/test.html
EXPOSE 80
```


