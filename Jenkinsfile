pipeline{
    agent any {
        stages{
            stage ('one'){
                steps {
                    echo 'Hi, This is Khagesh'
                }
            }
            stage ('two'){
                steps{
                    input('do you want to proceed?')
                }
            }
            stage ('three'){
                when {
                    not{
                        branch 'master'
                    }
                }
                steps {
                    echo 'Run on the master'
                }
            }
            stage ('four'){
                parallel{
                    stage('unit test'){
                        steps{
                            echo 'Running Unit Test..'
                        }
                    }
                    stage ('Intergration Test'){
                        agen{
                            docker{
                                reusable false
                                image 'ubuntu'
                            }
                        }
                    steps{
                        echo 'runnin the intergration test'
                    }
                }
                }
            }
        }
    }
}