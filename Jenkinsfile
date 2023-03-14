pipeline{
    agent ( label 'node1')
    triggers { pollSCM ('* * * * *') }
    stages{
        stage('vcs'){
            steps{
                git url: 'https://github.com/jayainjeti/StudentCoursesRestAPI.git'
                    branch: 'develop'
            }
        }    
        stage('docker build') {
            steps{
                sh 'docker image build -t jayainjeti/scr:1.0'
            }
        }
        stage('dockerPush') {
            steps{
                sh 'docker scan'
                sh 'docker image push jayainjeti/scr:1.0'
            }
        }
    }
}