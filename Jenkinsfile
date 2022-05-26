pipeline {
    agent { label "ansible_docker" }
    stages {
        stage('Clone repository') {
            steps {
                git credentialsId: 'ef074c1b-f48b-49fa-8930-4eccf501d178', url: 'git@github.com:Constantin174/example-playbook.git'
            }
        }
        stage('Run ansible') {
            steps {
                sh 'ansible-galaxy install -p ./ -r requirements.yml'
                sh 'ansible-playbook ./site.yml -i ./inventory/prod.yml'
            }
        }
    }
}