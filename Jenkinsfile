pipeline {
    agent any
    parameters {
        booleanParam(name: "RunTest", defaultValue: true, description: "This parameter will decide whether to run the testing stage or not!")
    }
    stages {
        stage("Build"){
            steps{
                echo "Building Stage"
            }
        }

        stage("Testing"){
            when {
                expression{
                    params.RunTest == true
                }
            }
            steps{
                echo "Testing Stage"
            }
        }

        stage("Deployment"){
            steps{
                echo "Deployment Stage"
            }
        }
    }
    post{
        always {
                emailext body: "Test Email from Multi Branch Pipeline", recipientProviders: ["harshit.dawar55@gmail.com"], subject: "Test"
        }
    }
}