pipeline {
    agent any
    stages {
        stage ('Build Servlet Project') {
            steps {
                /*For windows machine */
               sh 'mvn clean package'

                /*For Mac & Linux machine */
               // sh  'mvn clean package'
            }

            post{
                success{
                    echo 'Now Archiving ....'

                    archiveArtifacts artifacts : '**/*.war'
                   
                }
                
                steps{
                   
                    build job : 'Deploy-StagingArea-Piple'
                    
                     }
            }
        }
    }
}
