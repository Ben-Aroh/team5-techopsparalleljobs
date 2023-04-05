pipeline{
    agent any
    stages{
        stage('1-Unable to check jenkins status'){
            steps{
                 echo "testing jenkins"
                sh 'hostname'
            }
        }
        stage('2-parallel-jobs first'){
            parallel{
                stage('2-check disk free space in mega byte'){
                    agent {
                        label 'slave2'
                    }
                    steps{
                       sh '/home/jenkins/workspace/techopsgroupparallel/checkfreespacem.sh'
                    }
                }
                stage('3-check cpu and io statistics'){
                    steps{
                        sh '/home/jenkins/workspace/techopsgroupparallel/checkisostat.sh'
                    }
                }
            }
        }
        stage('2-another parallel-jobs second'){
            parallel{
                stage('4-check lscpu'){
                    agent {
                        label 'slave1'
                    }
                    steps{
                        sh '/home/jenkins/workspace/techopsgroupparallel/checklscpu.sh'
                    }
                }
                stage('5-check disk free space in human readable form'){
                    steps{
                      sh '/home/jenkins/workspace/techopsgroupparallel/checkdfh.sh'
                    }
                }
            }
        }
        stage('6-clossing'){
            agent{
                label 'slave2'
            }
            steps{
                echo "team5 group4 techops are done with parallel Jenkins build jobs"
            }
        }
    }
}
