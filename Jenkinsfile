// Uses Declarative syntax to run commands inside a container.
pipeline {
    agent {
        kubernetes {
          yamlFile 'jenkins-pod.yaml'
            // Can also wrap individual steps:
            // container('shell') {
            //     sh 'hostname'
            // }
           defaultContainer 'shell'
        }
    }
    stages {
        stage('Main') {
            steps {
                sh 'hostname'
            }
        }
    }
}
