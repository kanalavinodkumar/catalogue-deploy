pipeline {
    agent { node { label 'agent' } }
    environment{
        //here if you create any variable you will have global access, since it is environment no need of def
        packageVersion = ''
    }
        stage('Deploy') {
            steps {
                script{
                    echo "Deployment"
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