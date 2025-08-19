pipeline {
    agent {label 'slave1'}

    tools{
        maven 'maven'
    }

    stages{

        stage ('Build')
        {
            steps
            {
                echo "Building...."
                sh "mvn clean package"
            }
            post {
                success{
                    archiveArtifacts artifacts: '$WORKSPACE/target/*.war'
                }
            }
        }

    }
}