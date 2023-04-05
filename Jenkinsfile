pipeline{
    agent any
    stages{
        stage('1-check jenkins status'){
            steps{
                sh '/var/lib/jenkins/workspace/techopsgroupparallel/group4jenkinsstatus.sh'
            }
        }
        stage('2-parallel-jobs first'){
            parallel{
                stage('2-check disk free space in mega byte'){
                    steps{
                       sh '/var/lib/jenkins/workspace/techopsgroupparallel/freedisk.sh'
                    }
                }
                stage('3-check disk usage'){
                    steps{
                        sh '/var/lib/jenkins/workspace/techopsgroupparallel/diskusage.sh'
                    }
                }
            }
        }
        stage('2-another parallel-jobs second'){
            parallel{
                stage('4-check lscpu'){
                    steps{
                        sh '/var/lib/jenkins/workspace/techopsgroupparallel/lscpustat.sh'
                    }
                }
                stage('5-check disk free space in giga byte'){
                    steps{
                      sh '/var/lib/jenkins/workspace/techopsgroupparallel/freediskgiga.sh'
                    }
                }
            }
        }
        stage('6-closing stage'){
            steps{
                echo "team5 group4 techops are done with parallel Jenkins build jobs"
            }
        }
    }
}
