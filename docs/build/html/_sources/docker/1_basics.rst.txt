####################
Docker Basics
####################

**********************
Images vs. Containers
**********************
- An Image is the application
- A Container is an instance of that image running as a process
- You can have many containers running off the same image

Docker's default image "registry" is called Docker Hub

****************************************
What Happens in 'docker container run'
****************************************

1) Looks for that image locally in image cache
2) If it does not find it locally, then it looks in remote image repository
3) Downloads the latest version (if no version is specified)
4) Creates new container based on that image and prpares to start
5) Gives virtual IP on a private network inside docker engine
6) Opens up port specified (e.g., 80) on host and forwards to that same port in container
7) Container starts by using the CMD in the image Dockerfile

*******************
Containers vs. VMs
*******************
- Containers aren't Mini-VM's, they are just processes
- Limited to what resources they can access
- Exits when process stops

*****************************
Notes on Running Containers
*****************************
Containers only run as long as the command it ran on startup is active:

Containers only stay running while their initial command is running, 
which is the program itself unless an alternate argument is specified.
E.g., 'docker container run --name proxy nginx' will run until nginx is terminated
or the container is stopped. 'docker container run --name proxy -it nginx bash' will
run until bash is exited. 

Running a docker container exec function will not cause the docker container to exit
because it runs an additional process on the running container

Containers can only run what is included in the image:

E.g., Ubuntu can be started with a 'bash' argument to jump into the bash terminal,
but Alpine can't since bash isn't installed in the image file. You would need to us 
'sh' for Alpine, and from there install bash.

*****************************
Docker Networking
*****************************
    - Each container connected to a private virtual network bridge
    - Each virtual network routes through NAT firewall on host IP
    - All containers on a VN can talk to each other without -p 

Best Pactice is to create a new virtual network for each app:
    - network "my_web_app" for mysql and php/apache containers
    - network "my_api" for mongo and nodejs containers 

Note: Defaults work well in many cases, but easy to swap out parts and customize it

    - "Batteries Included, But Removable"

Some options:
    - Make new virtual networks 
    - Attach containers to more than on virtual network
    - Skip VNs and use host IP (--net=host)
        
        - Note: lose some of containerization benefits

    - Use different Docker network drivers to gain new abilities