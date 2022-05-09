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
        stage('sonar coverage') {
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
                mvn test
                mvn sonar:sonar
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
        stage('artifact upload') {
            steps {
                sh '''
                echo 'uploading artifacts to jfrog artifactory using jenkins pipeline'
                curl -uadmin:Admin@12345 -T /c/Users/nares/.jenkins/workspace/pipeline-Jenkinsfile/devpos/target/naresh-1.jar "http://localhost:8081/artifactory/devops/"
                '''
            }
        }
    }
}
