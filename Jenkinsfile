pipeline {
    agent {label 'slave1'}

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
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }

    }
}