pipeline {
agent { label 'bgl-ccbu-lion3' }
environment {
 CLONE_DIR = "/ws/cbreluc-bgl/Sample_project"
}
stages {

stage ('Clone GIT Repo'){
steps{
    sh """
     if [ -d $CLONE_DIR ];then
        cd $CLONE_DIR
        /usr/cisco/bin/git clean -fxd
        /usr/cisco/bin/git pull origin master
     else
     /usr/cisco/bin/git clone git@github5.cisco.com:ccbu-test/sample_project.git -b master $CLONE_DIR
    fi
    """ 
}
}
stage ('BUILD'){
steps{
    sh """
      cd $CLONE_DIR 
      javac HelloWorld/Main.java
      java -cp . HelloWorld.Main
      jar -cfm Main.jar Mainfest.mf HelloWorld.Main HelloWorld/Main.class
     """
}
}
/*
stage('Test'){
            steps {
                sh 'make check'
                junit 'reports/**/*.xml' 
            }
        }
*/
stage('Deploy') { 
    	 input{
      message "Press Enter directory name for deploy"

      parameters {
      string(name:'directory', defaultValue: '', description: 'Directory name for deployment')
     }
     }

	steps{
        sh 'Deployment'
}
}
}
}
