pipeline {
    agent any

    tools {
    
        maven "MAVEN_HOME"
    }

    stages {
        stage('Build') {
            steps {
              
                git 'https://github.com/RenuTech/MavenRepo.git'

                sh "mvn -Dmaven.test.failure.ignore=true clean package"
 
            }

            post {
               
                success {
                    
                    archiveArtifacts 'target/*.war'
                }
            }
        }
    }
}
