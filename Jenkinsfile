pipeline {
    agent {
    
        label 'slave'
    
    }

    stages {
        stage('clone') {
            steps {
                script{
                    "git clone  https://github.com/jglick/simple-maven-project-with-tests.git"
                }
                
            }
        }

    
        stage('build') {
            steps {
                
                script{
                    "mvn -Dmaven.test.failure.ignore=true clean package"
                }
            }
        }
        stage('run') {
            steps {
                
               sh "nohup java -jar target/*.jar"
            
            }
        }
   }
}



