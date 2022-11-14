pipeline {
    agent any 
    stages {
        stage('Build') {
            steps {
                git branch: 'main', url: 'https://github.com/vaishnavnamboodirim/cicd-demo-golang'
                
                sh "go build main.go"
            }
        }
        
        stage('Test') {
            steps {
                sh "go test"
            }
        }
        
        stage('Deploy/Run') {
            steps {
                sh "nohup go run main.go 2>&1 &"
            }
        }
    }
}
