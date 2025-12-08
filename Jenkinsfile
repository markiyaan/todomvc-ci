pipeline {
    agent any

    stages {
        stage('Preparation') {
            steps {
                echo 'Checking project structure...'
                sh 'ls -lah'
            }
        }

        stage('Build') {
            steps {
                echo 'Installing dependencies (if needed)...'
                sh '''
                    cd /root/todomvc/examples/angularjs_require
                    npm install || true
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Running Ansible deployment...'
                sh '''
                    ansible-playbook /root/ansible-deploy/deploy.yml \
                    -i /root/ansible-deploy/inventory.ini
                '''
            }
        }
    }
}
