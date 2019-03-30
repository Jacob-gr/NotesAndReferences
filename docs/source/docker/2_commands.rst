########
Commands
########

Image Commands
------------------

Download an Image
''''''''''''''''''
.. code-block:: docker

    docker pull 'image name'

Container Commands
------------------

Print logs of detached container:
'''''''''''''''''''''''''''''''''
.. code-block:: docker

    docker container logs 'container name'

List Containers:
''''''''''''''''
.. code-block:: docker

   docker ps


List processes running inside a specific container
''''''''''''''''''''''''''''''''''''''''''''''''''
.. code-block:: docker

   docker container top 'container name'

List Details of one container config
''''''''''''''''''''''''''''''''''''''''''''''''''
.. code-block:: docker

   docker container inspect 'container name'

Performance stats for all or one container
''''''''''''''''''''''''''''''''''''''''''''''''''
.. code-block:: docker

   docker container stats [optional:'container name']

Getting a Shell Inside Containers
''''''''''''''''''''''''''''''''''''''''''''''''''
Think: -it = InTeractive

-t is a TTY and -i is Interactive, which keeps Standard Input (STDIN) open

Think: -exec = EXecute in EXisting

Start a new container interactively
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. code-block:: docker

   docker container run -it 'Image Name' [Args: e.g., 'bash']

Run additional command in existing container
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
.. code-block:: docker

   docker container exec -it

Container Networking Commands
------------------------------

Print logs of detached container:
'''''''''''''''''''''''''''''''''
.. code-block:: docker

    docker container logs 'container name'