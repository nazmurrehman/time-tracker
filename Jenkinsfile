pipeline{
    agent any
    stages{
        stage('One'){
            steps{
                echo 'Hi, this is Nazmur from Globant'
            }  
        } 
        stage('Two'){
            steps {
                input('Do you want to proceed?')
            }
        }
        stage('Three'){
            when{
                not{
                    branch "master"
                }           
            }
            steps{
                echo "Hello"
            } 
        }
        stage('Four'){
            parallel{
                stage('Unit_Test'){
                    steps{
                       echo 'Running the unit test.... '
                    } 
                }
                stage('Integration_Test'){
                    agent{
                        docker{
                            reuseNode false
                            image 'ubuntu'
                        }
                    }
                    steps{
                        echo 'Running the integration test .....'
                    }
                }
            }
        }
    }    
}
                
