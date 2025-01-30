@Library('Django') _

pipeline{
    agent:{
        label slave
    }

    stages{
        stage('code'){
            script{
                code_stage("https://github.com/6355121720/django-notes-app.git", "main")
            }
        }
        stage('build'){
            script{
                build_stage("django-app", "latest")
            }
        }
        stage('push'){
            script{
                push_stage("dockerHubCred", "django-app", "latest")
            }
        }
        stage('deploy'){
            script{
                deploy_stage()
            }
        }
    }
}
