Your Application Reference Number(ARN) is: 22-1010598891

Your Application Reference Number(ARN) is: 22-1010602545

pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
               sh 'pipenv --python python3 sync'
            }
        }
        stage('Test') {
            steps {
               sh 'pipenv run pytest'
               sh 'zip -r sbdl.zip lib'
            }
        }
        stage('Package') {
			when{
			   branch "master" ; branch 'release'
			}
            steps {
               sh 'zip -r sbdl.zip lib'
            }
        }
    }
}
