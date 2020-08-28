pipeline {
	agent any
	stages {
		stage('check file in dir') {
			steps {
				sh 'ls -l'
			}
		}
	}
	post {
		success {
			echo 'this will be run when success'
			deploy adapters: [tomcat9(credentialsId: 'tomcat-admin', path: '', url: 'http://192.168.168.250:8080')], contextPath: '/normal', war: '**/*.war'
		}
	}
}