Assignments
Assignment1:

Install Nginx
Install below listed plugins
SSH plugin
Git plugin

Solution :  
####Installed the Nginx on the server and ssh plugin & Git plugin.

sudo yum install nginx -y
systemctl start nginx




Assignment2:

Enable password less login between jenkins & root user
Solution :

#######

Useradd Jenkins ( Created a jenkins user)
sudo su jenkins    ( Created a jenkins user)
ssh-keygen       (Created public and private key)
cd /home/jenkins/.ssh/

cat id_rsa.pub (Copy public key and switched the account to root.)
sudo su root
cd .ssh
sudo vim authorised_keys
sudo vim /etc/ssh/ssh_config   (Allow remote login)


Check Global configuration and provide SSH remote host(root) details

Solution : 
provide SSH remote host IP and the private key of jenkins user so that sync created with the public key which is being saved in root user can be accessed.


Assignment3:

Create a tag creator Jenkins Job
Job will create tag on your forked repo.
Job should accept 2 parameters
SRC_BRANCH
TAG_NAME

Assignment4:

Sync your forked jenkins repo with https://github.com/ot-training/jenkins.git (using multiple remote).
Create a Deployer Jenkins Job(static-code-deployment).
It will checkout code from https://github.com//jenkins.git (your forked repo).
Job will require a parameter TAG_NAME
It will use SSH Publish plugin to publish files from jenkins server to target server
Deploy index.html (existed inside attendees/assignments/day7) into nginx doc root.
Update index.html (with your name) and create a new tag.
Deploy with new tag.
Assignment5:

Install tomcat7

Solution :

######Installed tomcat through war file.
Started the services

Cd /opt/apache-tomcat7/bin/
./start.sh  (Start the tomcat services)


Install mysql
Yum group install mariadb   (Install all dependencies)
Systemctl start mariadb
Systemctl enable mariadb
mysql_secure_installation (Run this command configure the settings)
Systemctl restart mariadb



Fork ContinuousIntegration from opstree account.
Solution : Forked the above mentioned repository into my account.

Create a job Spring3HibernateApp-deployment
This job will be copy of static-code-deployment
Update deploymnet target to tomcat webapps directory
This job and code-stability (job from 6th day assignmnet) will have common workspace.
Deploy Spring3HibernateApp.war into tomcat7 (pick from workspace, copy into webapp of tomcat)

Verify you can acecess http://:8080/Spring3HibernateApp/

Soultion : 

I created a job with name "Spring3Hibernate" Maven type job

and provided the ROOT POM :  Spring3HibernateApp/pom.xml
Goal : clean install
war file created at /var/lib/jenkins/workspace/CodeStablity/Spring3HibernateApp/target

In the advance option maven mentioned war file alternate path in build option 
/opt/apache-tomcat7/webapps/

after the run the job
Still build job is failing with error : Unable to clone the repository
I am working on issue and will update you.


Assignment6:

Configure nginx in a way so that it can serve
static file (index.html) at http://
java application (Spring3HibernateApp) at http:///Spring3HibernateApp/
Hint: Add another location (Spring3HibernateApp/) and proxy_pass details in your nginx configireation.
Assignment7:
Deploy a demo node application
Fork node-js-sample repo into your account
Create a jenkins job to build node code and create a tar file(artifact)
Stop already application, Deploy tar file on a target server and start application again. Hint: Use pm2 to start and stop node process (process management)
