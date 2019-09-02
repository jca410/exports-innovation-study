# exports-innovation-study
This is a repository containing the basic environment for current research on the relationship between exporting activity and innovation.


To create a local version of this project you must:

* install [git](https://git-scm.com/downloads) in your platform
* choose a directory for the project
* open a command line tool and execute the code below

```Shell
$ cd path/to/project
$ git clone https://github.com/nettoyoussef/exports-innovation-study
```

To be able to use the container that runs the codes used in this project you need to install [Docker](https://docs.docker.com/install/) and [Docker-compose](https://docs.docker.com/compose/install/).
Then, proceed to the dockerfiles directory and:

* update the .env file to configure the login and password to access the Rstudio session inside the container
* update the path to the directory in the .env file
* execute the code below


```Shell
$ cd path/to/project/dockerfiles
$ docker-compose config
```


Check if the output has the same login and passwords you configured in the .env file
```
    ...
  r:
    build:
      args:
        PASSWORD: your-password
        USER: your-login
      ...
    environment:
      LOGIN_USER: your-login
      PROJECT_DIR: path/to/directory/your-login
      RSTUDIO_PWD: your-password
    ...
    volumes:
    - path/to/directory/:/home/your-login:rw
 ...   

 ```
 
 If everything looks correct, then you can execute the code below:
 
 ```Shell
$ docker-compose build
$ docker-compose up
 ```

After the installation of the container ends, if everything is working fine you will be able to access the image at your browser accessing the local port 8787:

```
http://127.0.0.1:8787
or
http://localhost:8787/
```

To see the containers created run:

```Shell
$ sudo docker ps -a
```

To see the images created and their size, run:

```Shell
$ sudo docker images
```



 







