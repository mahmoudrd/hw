pipeline {
    agent {
    
        label 'slave'
    
    }

    stages {
        stage('clone') {
            steps {
                
                sh "git 'https://github.com/jglick/simple-maven-project-with-tests.git"
                
            }
        }

    
        stage('build') {
            steps {
                
               sh "mvn -Dmaven.test.failure.ignore=true clean package"
            
            }
        }
        stage('run') {
            steps {
                
               sh "unhup java -jar target/*.jar"
            
            }
        }
   }
}

