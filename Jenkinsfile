pipeline {
    agent { label 'jenkins-slave'}
    stages {
        stage('Echo hello') {
            steps {
                echo 'Hellow world'
            }
        }
        stage('Docker hub'){
            steps {
                withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {
                    sh 'docker build -t hoanbc/test123:v2 .'
                    sh 'docker push hoanbc/test123:v2'
                }
            }
        }
        //stage('SSH to gitlab server') {
        //    steps {
        //        sshagent(['gitlab-ssh-key']) {
        //            sh 'ssh -o StrictHostKeyChecking=no -l root srv-gitlab.systemtest.xyz touch /opt/test.txt'
        //        }
        //    }
        //}

    }
    post {
        always {
            mail bcc: '', body: 'Jenkins System 123', cc: '', from: '', replyTo: '', subject: 'Jenkins System 123 Bạn Siêu Víp', to: 'hoanbc@outlook.com'
        }
    }
}
