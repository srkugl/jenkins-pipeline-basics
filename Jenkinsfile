pipeline{
    agent {
        label 'nodejs'  // run the build job in particular agent
    }
    options { // set timeout for jobs
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 10, unit: 'SECONDS')
        disableConcurrentBuilds() // disabling concurrent builds at a time same job will not run
        ansiColor('xterm')
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    environment{
        // set values use whenever you want in pipeline
        DEPLOY_TO = 'PROD'
        Greeting = 'Hello'
    }

    stages{
        stage("Build"){
            steps{
                echo "Build the app"
            }
        }
        stage("upload artifact"){
            steps{
                echo "Upload the artifact"
            }
        }
        stage("Deploy"){
            steps{
                echo "Deploy the app"
            }
        }
        stage("Accssing Parameters into pipeline"){
            steps{
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
            }
        }
        stage("PrintEnv"){
              input { // prompts the user acceptence
                message "Should we continue?"
                ok "Yes, we should."
                submitter "alice,bob"
                parameters {
                    string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
                }
            }
            steps{
                sh 'printenv'
            }
        }
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
                deleteDir() // deletes build folder after build completion
        }
    }
}