# MlOps-task1
Using this tools- 
Jenkins
Git
Github 
Docker

TASK-1 

JOB#1
If Developer push to dev branch then Jenkins will fetch from dev and deploy on dev-docker environment.

JOB#2
If Developer push to master branch then Jenkins will fetch from master and deploy on master-docke environment.
both dev-docker and master-docker environment are on different docker containers.

JOB#3
Manually the QA team will check (test) for the website running in dev-docker environment. If it is running fine then Jenkins will merge the dev branch to master branch and trigger #job 2

Approach

Firstly, I created a local repository in my base OS and created a branch(dev). In this repository, I created a file called 'index.html'.

To automatically push it to GitHub whenever I commit any change in the file, I created a hook.

I also added a trigger so to automatically trigger the Job1.

Job -1

This Job will do multiple things. Whenever a new code is uploaded on GitHub, job will automatically get triggered and copy all the files from github to a location on my local system(here, /dev1).

Then it will check whether a docker of a particular name exists or not. If yes, then it will remove that docker container and then create a docker. 


Job - 2
If Developer push to master branch then Jenkins will fetch from master and deploy 
on master-docke environment.both dev-docker and master-docker environment are on different docker containers.

 Job-3

This job is the downstream project of Job 2.

In this job, jenkins will first copies the file from GitHub to the local system folder(here, /production). Then it will check whether a docker of a particular name exists or not. If yes, then it will remove that docker container and then create a docker.

The docker will be deployed with a port no. so that we all can access it.
