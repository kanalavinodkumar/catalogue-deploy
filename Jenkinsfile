pipeline {
    agent { node { label 'agent' } }
    environment{
        //here if you create any variable you will have global access, since it is environment no need of def
        packageVersion = ''
    }
        stages{

            stage('Deploy') {
                steps {
                    script{
                        echo "Deployming version - ${params.version}"
                    }
                }
            }

            stage('Init') {
                steps {
                    script{
                        echo "Deployming version - ${params.version}"
                        sh '''
                        cd terraform
                        terraform init -reconfigure
                        '''

                    }
                }
            }

            stage('Plan') {
                steps {
                    script{
                        sh '''
                        cd terraform
                        terraform plan
                        '''

                    }
                }
            }
        }

    post{
        always{
            echo 'cleaning up workspace'
            deleteDir()
        }
    }
}