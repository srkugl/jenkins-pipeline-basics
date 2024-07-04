pipeline{
    agent {
        label 'nodejs'  // run the build job in particular agent
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