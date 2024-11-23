
pipeline {
    agent any
    stages {
        stage ('GetProject') {
            steps {

                git branch: 'master', url: 'https://github.com/brendan-galway/brendanspetitions.git'


            }

        }
        stage ('build') {
            steps {
                sh 'mvn clean:clean'
                sh 'mvn dependency:copy-dependencies'
                sh 'mvn compiler:compile'
            }
        }
        stage ('Exec') {
            steps {
                sh 'mvn exec:java'
            }
        }
    }
}