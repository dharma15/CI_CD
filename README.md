# CI_CD
CI-CD pipeline job trigger on every commit on master
Create a git repo commit HelloWorld/Main.java  Jenkinsfile  Mainfest.mf
install Jenkins Server and configure Github
Go to manage jenkins add github repo url
create pipeline job
select the option pipeline script from SCM and provide Jenkinsfile name
fill the details like github URL and branch name
check Build Trigger on GitHub hook trigger for GITScm polling
 for Trigger we have add webhook on github
 On the GitHub web site:

Go to your repository’s page on GitHub.
Select Settings, Webhooks, Add webhook
In the Payload URL enter:
https://jenkins.princeton.edu/github-webhook/
In Content type select: application/json.
In the box Which events would you like to trigger this webhook? select Just the push event.
Click on Add webhook.
