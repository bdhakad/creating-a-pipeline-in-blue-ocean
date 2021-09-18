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
        stage('only-if-true') {
            when {
                expression {
                    return true_or_false
                }
            }
            steps {
                echo "We ran the stage because true_or_false was true"
            }
        }
        stage('only-if-false') {
            when {
                expression {
                    return !true_or_false
                }
            }
            steps {
                echo "We ran the stage because true_or_false was false"
            }
        }
    }
}
