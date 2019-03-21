pipeline {
    agent none
    stages {
        stage('Sequential 1') {
            agent {
                label 'test' }
            steps {
                echo ' In Sequential 1'
                git branch: 'master', url: 'https://github.com/agrsonal/febdemo.git'
            }
        }
        stage('Sequential 2') {
            agent {
                node {
                    label 'test'
                    customWorkspace 'C:\\CLASSROOM\\jenkins\\seq2'
                }
            }
            steps {
                echo 'In Sequential 2'
                git branch: 'master', url: 'https://github.com/agrsonal/febdemo.git'
            }
        }
        stage('Parallel in Sequential') {
            parallel {
                stage('Parallel 1') {
                    agent {
                        node {
                            label 'test'
                            customWorkspace 'C:\\CLASSROOM\\jenkins\\parallel1'
                        }
                    }
                    steps {
                        echo 'In Parallel 1'
                        git branch: 'master', url: 'https://github.com/agrsonal/febdemo.git'
                    }
                }
                 stage('Parallel 2') {
                    agent {
                        node {
                            label 'test'
                            customWorkspace 'C:\\CLASSROOM\\jenkins\\parallel2'
                        }
                    }
                    steps {
                        echo 'In Parallel 2'
                        git branch: 'master', url: 'https://github.com/agrsonal/febdemo.git'
                    }
                }
            }
        }
    }
}
