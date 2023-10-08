### Real Projects with docker

#### Nodejs web app

1. `FROM node:alpine` (versions or tags are specified after colon)<br>
   Specify base image that contains node and npm preinstalled <br>
   (with additional programs we might need for nodejs app).<br><br>
2. `WORKDIR /usr/app`<br>
   It will **create** that directory if it does not exist.<br>
   Also, it **prevents** adding our files and folders inside **root** directory where it can conflict with other files and folders that already exists inside root. It's basically our working directory where our project would exist. Also, if later we want to execute commands inside container using `docker exec`, we will be able to do that inside working directory automatically.<br>
   ![Reference](references/workdir-command.png)<br><br>
3. `COPY ./ ./` <br>
   Copy files to container (it's own isolated hard drive segment).<br>
   It will **COPY** files inside working directory we have specified above.
   <br><br>
   ![Reference](references/copy-files.png) <br><br>
4. `RUN npm install`<br>
   Install dependencies<br><br>
5. `CMD ["npm", "start"]`<br>
   **start** is a script inside package.json file that executes `node index.js`<br><br>

6. `docker build -t <docker-id>/<image-name> .`<br>
   So, image has been created with name/tag.<br><br>
7. `docker run -p 8080:8080 <image-id>` <br>
   Port mapping: forwarding of requests from outside of container to inside container<br>
   It is **NOT** specified in dockerfile as it's a runtime thing.
   <br><br>
   ![Reference](references/port-mapping.png)
   <br><br>
   ![Reference](references/port-mapping-command.png)
   <br><br>
