pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Stage 0: Building the application'
                echo 'release: 1.0.1'
                echo 'Stage 1: Cloning repository and installing dependencies'
                git branch: 'main', url: 'https://github.com/wenyupeng/evolze.git'
                echo 'npm install'
                echo 'npm run build'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Stage 2: Running unit and integration tests'
                echo 'npm test'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Stage 3: Performing static code analysis with ESLint'
                echo 'npx eslint .'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Stage 4: Running security scan with npm audit'
                echo 'npm audit --audit-level=high'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Stage 5: Building Docker image and pushing to staging environment'
                echo 'docker build -t myapp:staging .'
                echo 'docker tag myapp:staging chrisyp/myapp:staging'
                echo 'docker push chrisyp/myapp:staging'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Stage 6: Running integration tests against staging environment'
                echo 'npx cypress run --env baseUrl=https://staging.example.com'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Stage 7: Building and deploying Docker image to production'
                echo 'docker build -t myapp:production .'
                echo 'docker tag myapp:production chrisyp/myapp:production'
                echo 'docker push chrisyp/myapp:production'
            }
        }
    }
}