pipeline{
    agent any

    environment{
        DOCKERHUB_USERNAME = "govindrao92"
        APP_NAME = "gitops-argo-app"
        IMAGE_TAG = "${BUILD_NUMBER}"
        IMAGE_NAME = "${DOCKERHUB_USERNAME}"+ "/" + "${APP_NAME}"
        REGISTRY_CREDS = 'dockerhub'

    }

    stages{
        stage('Cleanup workspace'){
            steps{
                script{
                    cleanWs()
                }
            }
        }
        stage('checkout scm'){
            steps{
                script{
                   // git credentialsId: 'github',
                    //url: 'https://github.com/govindrao92/gitops_argocd_project.git'
                    //branch: 'main'
                    //or
                    withCredentials([gitUsernamePassword(credentialsId: 'github', gitToolName: 'Default')]) {

                    }
                }
            }
        }
        stage('Build Docker Image'){
            steps{
                script{
                    docker_image = docker.build "${IMAGE_NAME}"
                }      
            }
        }
        
    }


}