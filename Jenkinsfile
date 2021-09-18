// Uses Declarative syntax to run commands inside a container.
pipeline {
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        string(name: 'cmd', defaultValue: 'echo Hello ${params.PERSON}', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    agent {
        kubernetes {
          yamlFile 'templates/jenkins-shell-pod.yaml'
            // Can also wrap individual steps:
            // container('shell') {
            //     sh 'hostname'
            // }
           //defaultContainer 'shell'
        }
    }
    stages {
        stage('Example') {
            steps {
                container('shell'){
                    sh "${cmd}"

                    // echo "Biography: ${params.BIOGRAPHY}"

                    // echo "Toggle: ${params.TOGGLE}"

                    // echo "Choice: ${params.CHOICE}"

                    // echo "Password: ${params.PASSWORD}"
                }
            }
        }
    }
}
