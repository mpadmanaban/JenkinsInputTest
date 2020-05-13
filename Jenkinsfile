pipeline {
	agent any
	stages {
		stage('Linting') {
			steps {
				sh 'tidy -q -e *.html'
			}
		}
		stage('Promotion') {
			steps {
				timeout(time: 1, unit: "MINUTES") {
					input message: 'Approve Deploy?', ok: 'Yes'
				}
			}
		}
		stage('Deploy test') {
			steps {
				sh 'tidy -q -e *.html'
			}
		}
	}
}
