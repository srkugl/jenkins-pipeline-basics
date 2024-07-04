pipeline{
    agent {
        label 'nodejs'  // run the build job in particular agent
    }
    options { // set timeout for jobs
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 10, unit: 'SECONDS')
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