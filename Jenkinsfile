pipeline {
    agent {
      kubernetes {
        cloud 'minikube'
        yaml """
apiVersion: v1
kind: Pod
spec:
  containers:
  - name: maven
    image: maven:alpine
    command:
    - cat
    tty: true
"""
        }
    }
    
    stages {
        stage ("Run Maven.") {
            steps {
                container('maven'){
                    sh 'mvn -version'
                }
            }
        }
    }
}
