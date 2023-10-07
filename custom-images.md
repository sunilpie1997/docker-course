### Creating custom images

NOTE: [Docker image build process in detail](https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/learn/lecture/11436706#overview)
<br>
<br>At each stage, the docker image obtained from previous step is taken, a <br>container is run from this image, that particular command / instruction is <br>executed, which makes a change in file system. We take this container's <br>file system snapshot and create another image from it and pass it as input <br>to next instruction. This whole process is repeated until we reach the end. <br>The last CMD instruction just tells docker to set it up as startup command <br>for final created image.

![Reference](references/image-from-dockerfile.png)<br>
![Reference](references/create-dockerfile.png)<br>
![Reference](references/use-progress-flag.png)<br>
![Reference](references/sample-dockerfile.png)<br>
![Reference](references/common-instruction-for-creating-image.png)<br><br>

Build process:
![Reference](references/step-1.png)<br>
![Reference](references/step-2.png)<br><br>

### Docker image build command<br>

1. checkout to directory where Dockerfile exists.
2. `docker build .`<br>
   **.** indicates build context (specifies the directory of files/folders to use for the build)<br>

3. [Build Process in detail](https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/learn/lecture/11436706#overview)

Analogy of Dockerfile instructions
![Reference](references/dockerfile-base-image.png)<br>
![Reference](references/base-image.png)<br><br>

Tagging image
![Reference](references/Tagging-image-1.png)<br>
(docker-id/custom-name:version)<br><br>

Manual docker image generation from container (just as in build process)

1. [manual image generation](https://www.udemy.com/course/docker-and-kubernetes-the-complete-guide/learn/lecture/11436722#overview)
2. ![Reference](references/manual-image-generation.png)
