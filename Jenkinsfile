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
        }

        stage ('Test')
        {
            parallel 
            {
                stage ('Test-A')
                {
                    steps
                    {
                        echo "This is Test-A"
                    }
                }

                stage ('Test-B')
                {
                    steps
                    {
                        echo "This is Test-B"
                    }
                }

            }

            post {
                success{
                    echo "${WORKSPACE}"
                    archiveArtifacts artifacts: '**/target/*.jar'
                }
            }

        }

    }
}