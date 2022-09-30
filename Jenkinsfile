pipeline {
    agent any 
    stages {
        stage('Clone the repo') {
            steps {
                echo 'Clone the repo' 
                sh 'rm -rf test'
				sh 'git clone https://github.com/mrikiyanto/test.git'
            }
        }
         stage('SYNC docroot from latest updated repo') {
            steps {
				echo 'synchronize ' 
				sh 'rsync -avzyh /var/lib/jenkins/workspace/helloworld/test/ /var/www/html/simple-html/'
            }
        }
        stage('Check web is up') {
            steps {
				echo 'Check web get response 200' 
				sh 'curl -is http://riki2.kompas.cloud | head -n 1'
	        }
        }
    }
}
