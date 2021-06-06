pipeline {
  agent any
  stages {
    stage('Build stage') {
      steps {
        echo 'Build stage'
        dir(path: 'C:\\Users\\Aakarsh Yoga 7i\\Personal Documents\\01_Git_repositories\\AR_devops') {
          bat(script: 'run_script.bat', returnStatus: true, returnStdout: true, encoding: 'utf-8')
        }

        echo 'Build and execution successful!'
      }
    }
	
	stage('Upload') {
	dir(path: 'C:\\Users\\Aakarsh Yoga 7i\\Personal Documents\\01_Git_repositories\\AR_devops') {
		echo %cd% //Log current directory
		withAWS(region:'US East (Ohio) us-east-2',credentials:'Jenkins-github-s3') {
			 def identity=awsIdentity();//Log AWS credentials
			// Upload files from working directory 'dist' in your project workspace
			s3Upload(bucket:"jenkins-github-s3", workingDir:'hello.py', includePathPattern:'**/*');
		}
										}
					}

  }
}