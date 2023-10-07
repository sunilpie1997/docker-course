### commands

1. We can also provide alternate startup command (to execute inside container) after it starts up. <br>
   `docker run <image-name> <command>` <br>
   For example when we run -> `docker run busybox ls` <br><br>
   ![Reference](3_docker_cli/busybox-example.png)

2. But in below hello-world example, we cannot execute 'echo' or 'ls' commands because the executables or processes that these commands run behind the scenes does not exist in filesystem.<br><br>
   ![Reference](references/hello-world-error.png)

3. `docker ps` : list all runnning containers.
4. `docker ps --all` : list all containers ever created (includes exited ones).
5. `docker run <image-name>` <br><br>
   ![Reference](references/run-command.png) <br><br>
   ![Reference](references/run-command-2.png) <br><br>
   Creating is about getting file system ready without actually starting container and starting is about actually executing startup commands. <br>
   `docker run` =  
   `docker create hello-world` + `docker start -a <container-id>`
   <br>
   ![Reference](references/intialize-volumes.png) <br><br>
   Docker's run command by default shows all the logs coming out of container but start command is just the opposite. Adding **-a** watches for any output from container and prints it to console.

6. `docker system prune`<br>
   to remove stopped containers and reclaim space.<br><br>
   ![Reference](references/docker-prune-command.png)

7. `docker logs <container-id>` <br>
   to see output logs from a stopped container<br><br>
   ![Reference](references/docker-logs-command.png)

8. **stop** command gives some time to process to clean up and then shut down unlike **kill** command.<br><br>
   ![Reference](references/docker-stop-command.png)

9. Execute multiple commands inside container <br><br>
   ![Reference](references/multiple-commands-inside-container.png)
   <br>
   ![Reference](references/execute-multiple-commands.png)

   ### Purpose of -it flag

   It's a combination of -i and -t flags<br>
   ![Reference](references/purpose-of-it-flags.png)<br>
   ![Reference](references/it-flags.png)

10. To get access to a shell/terminal to execute commands in the container <br>
just like window powershell or linux bash, use: <br>
```docker exec -it <container-id> sh```
<br><br>
We can also use  ```docker run -it <image-id> sh```  to run shell (default <br>
startup command) when starting container. But most often we will have other <br>
primary process to run while starting container.<br>
In this way we can execute multiple commands at once interactively instead of
<br>using ```docker exec``` command again and again.
<br>
![Reference](references/command-processors.png)