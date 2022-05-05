pipeline {
    agent 'any'
    stages {
        stage('scm-clone') {
            steps {
                sh '''
                rm -rf *
                git clone 'https://github.com/nareshmacha/devpos.git'
                '''
            }
        }
         stage('project-str') {
            steps {
                sh '''
                pwd
                ls -ll
                '''
            }
        }
         stage('compilation') {
            steps {
                sh '''
                pwd
                ls -ll
                cd devpos
                ls -ll
                java -version
                mvn --version
                mvn clean
                mvn compile
                '''
            }
        }
        stage('test') {
            steps {
                sh '''
                pwd
                ls -ll
                cd devpos
                ls -ll
                java -version
                mvn --version
                mvn clean
                mvn test
                '''
            }
        }
        stage('package') {
            steps {
                sh '''
                pwd
                ls -ll
                cd devpos
                ls -ll
                java -version
                mvn --version
                mvn clean
                mvn package
                '''
            }
        }
    }
}
