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
        }

    post{
        always{
            echo 'cleaning up workspace'
            deleteDir()
        }
    }
}