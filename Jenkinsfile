pipeline{
    agent any
    stages{
        stage('1-check status jenkins'){
            steps{
                 sh 'bash -x /var/lib/jenkins/masterscript.sh' 
            }
        }
        stage('2-parallel-jobs first'){
            parallel{
                stage('2-check operating system statistics'){
                    agent {
                        label 'slave2'
                    }
                    steps{
                        echo "My name is: Ben Aroh"
                        sh 'free -m'
                    }
                }
                stage('3-check name of team memeber'){
                    steps{
                        sh 'free -g'
                    }
                }
            }
        }
                stage('4-check-group-member-name'){
                    steps{
                echo "My name is: Joyce Ngantcha" 
            }
        }
        stage('2-another parallel-jobs second'){
            parallel{
                stage('5-check operating system statistics'){
                    agent {
                        label 'slave1'
                    }
                    steps{
                        sh 'bash -x /home/jenkins/workspace/script1.sh'
                        sh 'lscpu'
                    }
                }
                stage('6-check name of team memeber'){
                    steps{
                      sh 'df -h'
                    }
                }
            }
        }
        stage('7-clossing'){
            agent{
                label 'slave2'
            }
            steps{
                echo "team5 group4 techops are done with parallel Jenkins build jobs"
            }
        }
    }
}
