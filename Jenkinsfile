pipeline{
    agent { label 'java11'}
    triggers { pollSCM ('* * * * *') }
    stages{
        stage('vcs') {
            steps {
                git url: 'https://github.com/jayainjeti/StudentCoursesRestAPI.git',
                    branch: 'develop'
            }
        }    
        stage('docker build') {
            steps {
                sh 'docker image build -t jayainjeti/scr:1.0 .'
            }
        }
        stage('docker Push') {
            steps {
                sh 'docker scan jayainjeti/scr:1.0'
                sh 'docker image push jayainjeti/scr:1.0'
            }
        }
    }
}
