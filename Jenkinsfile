pipeline {
    agent any 
    tools {
        go 'go1.17'
    }
    environment {
        GO114MODULE = 'auto'
        CGO_ENABLED = 0 
    }
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
