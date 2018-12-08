pipeline {

	agent any

	stages {
	
		stage('Build') {
			steps {
				echo "Building..."
				sh 'docker run -v `pwd`:/build damoncheng/public:debian-build-v1'
			}
		}

		stage('Test') {
			steps {
				echo "Testing..."
                                echo 'pwd : `pwd`'
                                echo 'ls : `ls`'
				sh './main config/hello.o'
			}
		}

		stage('Deploy') {
			steps {
				echo "Deploying...."
			}
		}
	
	}
	post {
	
		failure {
			mail to: "snhellogg@gmail.com", subject: 'The Pipeline failed :(', body: 'hello jenkins two'
		}
	
	}

}
