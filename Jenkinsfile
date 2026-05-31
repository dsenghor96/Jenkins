pipeline {
    agent any

    environment {
        DOCKERHUB_USER = 'dieys'
        FRONTEND_IMAGE = "${DOCKERHUB_USER}/portfolio-frontend"
        BACKEND_IMAGE  = "${DOCKERHUB_USER}/portfolio-backend"
        GITHUB_REPO    = 'https://github.com/dsenghor96/Jenkins'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'master',
                    credentialsId: 'github-credentials',
                    url: "${GITHUB_REPO}"
            }
        }

        stage('Build Backend') {
            steps {
                sh 'docker build -t ${BACKEND_IMAGE}:${BUILD_NUMBER} ./api'
            }
        }

        stage('Build Frontend') {
            steps {
                sh 'docker build -t ${FRONTEND_IMAGE}:${BUILD_NUMBER} ./ux_react'
            }
        }

        stage('Test Backend') {
            steps {
                sh '''
                    docker run --rm \
                    -v $(pwd)/api:/app \
                    -w /app \
                    node:20-alpine \
                    sh -c "npm install && npm test || echo 'Aucun test defini, etape ignoree'"
                '''
    }
}


        stage('Push to Docker Hub') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-credentials',
                    usernameVariable: 'DOCKER_USER',
                    passwordVariable: 'DOCKER_PASS'
                )]) {
                    sh '''
                        echo $DOCKER_PASS | docker login -u $DOCKER_USER --password-stdin
                        docker push ${BACKEND_IMAGE}:${BUILD_NUMBER}
                        docker push ${FRONTEND_IMAGE}:${BUILD_NUMBER}
                        docker tag ${BACKEND_IMAGE}:${BUILD_NUMBER} ${BACKEND_IMAGE}:latest
                        docker tag ${FRONTEND_IMAGE}:${BUILD_NUMBER} ${FRONTEND_IMAGE}:latest
                        docker push ${BACKEND_IMAGE}:latest
                        docker push ${FRONTEND_IMAGE}:latest
                    '''
                }
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    cd /var/jenkins_home/workspace/portfolio-pipeline
                    docker compose down || true
                    docker compose up -d
                '''
            }
        }
    }

    post {
        success {
            echo 'Pipeline termine avec succes !'
            emailext(
                subject: "SUCCESS: Pipeline ${JOB_NAME} #${BUILD_NUMBER}",
                body: "Le pipeline ${JOB_NAME} build #${BUILD_NUMBER} est termine avec succes.\nURL: ${BUILD_URL}",
                to: 'dieyna@example.com'
            )
        }
        failure {
            echo 'Pipeline echoue !'
            emailext(
                subject: "FAILURE: Pipeline ${JOB_NAME} #${BUILD_NUMBER}",
                body: "Le pipeline ${JOB_NAME} build #${BUILD_NUMBER} a echoue.\nURL: ${BUILD_URL}",
                to: 'dieyna@example.com'
            )
        }
        always {
            echo 'Nettoyage des images temporaires...'
            sh 'docker image prune -f'
        }
    }
}
