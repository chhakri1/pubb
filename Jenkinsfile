pipeline {
    agent any 
    options { buildDiscarder(logRotator(numToKeepStr: '4')) }
    parameters { choice(name: 'DEPLOY_STAGE', choices: ['apply', 'destroy', 'vali'], description: 'lets try') }
      
        stages {
            stage ('tf init') {
                steps { 
                    sh 'terraform init'

                }
            }
            stage ('tf validate') {
                  
                steps {  sh 'terraform validate'

                }
            }
            stage( 'tf plan') {
                steps {
                    echo "plan sucess"
                }
            }
            stage ('tf apply') {
                when {
                    expression { params.DEPLOY_STAGE == 'apply' }
                }
                steps {  
                    //sh 'terraform apply --auto-approve'
                    echo "in splly srage"

                }
            }
        }
