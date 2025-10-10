- This will be using Docker CLI

`docker version` allows you to check the version of docker and verify CLI and talk to the engine. 
`docker info` gives you the config values of the engine. 
`docker` is the root command and will print out all the commands which you can use. 


- Docker used to have lots of individual commands, and the list was getting too big. 
- We now use management commands, or command and subcommands. All new commands will follow this convention. `docker <command> <subcommand> (options)`
- Example: `docker run` is now `docker container run`
- Docker is very backwards compatible, so docker run will still work. But `docker container run` is the official way. 
- Most commands we will be learning, we will be taught the old way and the new way. 

