# devops_task2
This post is about how we can integrate git,github,docker & jenkins together to make a fully automated process from developer end to the operational team to reduce the manual work.
Here every tool is used for some specific purpose.This process consist of the following phases -
1.Base OS (RHEL8) - Here we start the services like jenkins,docker and stop the firewall using the systemctl start service_name.
Also here we make two directories to store the deployed files on production & testing system.
2.Docker - Using the docker we launch two os of httpd.In my case it is production_server & testing_server.
3.Github - We make a new repository here and initialise it.
4.Git - Clone the repo created on github using the git clone command.Also try to make another branch other than master like dev1.For auto push use the hook concept & create post-commit file in .git/hooks/.Make file in the dev1 also and commit it.
5.Jenkins - It is the soul of the complete process.Here we define three jobs to perform specific task.
a)Job1 - If the developer make some changes in the master branch then jenkins will fetch it & copy the file to the prodDir of production_server created using docker. 
b)Job2 - If the developer make some changes in the dev1 branch then jenkins will fetch it & copy the file to the testDir of production_server created using docker.
c)Job3 - It is triggered only if the Job2 run successfully.It will perform post trigger to run the job1 which will result in the merging of dev1 to master branch.
In the conclusion it can be said that if dev1 is ahead of the master branch & is stable then it will automaticallly merge with the master.
It is really good to learn such things & practising it.I am feeling thankful to Mr. Vimal Daga sir whose way of teaching made such complex looke so much easy.With no doubt he is the best mentor one can have.
 
