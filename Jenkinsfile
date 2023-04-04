pipeline{
    agent{
        label 'slave1'
    } 
    stages{
        stage('1-check-group-member-name'){
            steps{
                echo "My name is: Ben Aroh" 
            }
        }
        stage('2-parallel-jobs first'){
            parallel{
                stage('2-check operating system statistics'){
                    agent {
                        label 'slave2'
                    }
                    steps{
                        sh 'lscpu'
                        echo "My name is: Ben Aroh"
                    }
                }
                stage('3-check the status of Jenkins'){
                    steps{
                        sh 'sudo systemctl status jenkins'
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
                        sh 'lscpu'
                    }
                }
                stage('6-check the status of Jenkins'){
                    steps{
                        sh 'sudo systemctl status jenkins'
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