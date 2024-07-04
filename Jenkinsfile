pipeline{
    agent {
        label 'nodejs'  // run the build job in particular agent
    }
    options { // set timeout for jobs
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 10, unit: 'SECONDS')
        disableConcurrentBuilds() // disabling concurrent builds at a time same job will not run
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
    }
}