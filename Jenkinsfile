pipeline{
    agent any


    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                sh 'sonar-scanner'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                sh 'jfrog rt upload'
            }
        }
    }

    // stages{
    //     stage('checkout'){
    //         steps{
    //             checkout([$class: 'GitSCM', branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[credentialsId: 'github access', url: 'https://github.com/sreenivas449/java-hello-world-with-maven.git']]])
    //         }
    //     }
    //     stage('build'){
    //         steps{
    //            bat 'mvn package'
    //         }
    //     }
    // }
}