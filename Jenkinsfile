pipeline {
    agent any

    stages {
        stage('Preparation') {
            steps {
                echo "Checking project structure..."
                sh "ls -lah"
            }
        }

        stage('Build') {
            steps {
                echo "AngularJS TodoMVC does not require build step"
            }
        }

        stage('Deploy') {
            steps {
                echo "Running Ansible deployment..."
                sh "ansible-playbook /var/lib/jenkins/ansible-deploy/deploy.yml -i /var/lib/jenkins/ansible-deploy/inventory.ini"
            }
        }
    }
}
