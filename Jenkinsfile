@Library('Django') _

pipeline{
    agent{
        label 'slave'
    }

    stages{
        stage('code'){
            steps{
                script{
                    code_stage("https://github.com/6355121720/django-notes-app.git", "main")
                }
            }
        }
        stage('build'){
            steps{
                script{
                    build_stage("django-app", "latest")
                }
            }
        }
        stage('push'){
            steps{
                script{
                    push_stage("dockerHubCred", "django-app", "latest")
                }
            }
        }
        stage('deploy'){
            steps{
                script{
                    deploy_stage()
                }
            }
        }
    }
}
