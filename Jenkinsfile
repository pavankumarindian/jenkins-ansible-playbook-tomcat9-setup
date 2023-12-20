pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', changelog: false, poll: false, url: 'https://github.com/pavankumarindian/jenkins-ansible-playbook-tomcat9-setup.git'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                script {
                    sh "ansible-playbook -i /home/ubuntu install_tomcat9.yml -b"
                }
            }
        }
    }

    post {
        success {
            echo 'Tomcat9 installation completed successfully.'
        }

        failure {
            echo 'Tomcat9 installation failed.'
        }
    }
}
