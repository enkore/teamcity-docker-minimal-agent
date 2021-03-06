## TeamCity Minimal Agent Image Dockerfile

This project contains the Dockerfile and all necessary scripts to build the Docker image and run a TeamCity Build Agent inside the container.

If you need to build your own image, you need to perform the following:


You can use your own base image with the operation system of your choice and JAVA installed. TeamCity relies on the `JRE_HOME` environment variable. Just tag your own image with the `teamcity-base` tag.

1) Extract buildAgent.zip of any version you'd like to use into  the `dist/buildagent` folder and prepare agent config directory. In the same directory where the Dockerfile is placed, run
```
mkdir dist
unzip buildAgent.zip -d dist/buildagent
mv dist/buildagent/conf dist/buildagent/conf_dist
```

2) Run the `docker build` command:
```
docker build -t teamcity-agent-qabel .
```
 
