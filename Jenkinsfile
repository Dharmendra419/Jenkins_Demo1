pipeline {
      agent any 
             stage('Test-1') {
                    steps {
                             echo 'Hi, This is a test'
                    }
             }
             stage('Test-2') {
                    steps {
                             echo 'This is a input test'
                             input('Do you want to proceed')
                    }
             }
             stage('Test-3') {
                     when {
                             not {
                                  branch 'main'
                             }
                     }
                     steps { 
                           echo 'Helloo this works'
                     }
             }
             stage('Test-4') {
                               parallel {
                                     stage('Unit Test') {
                                                       steps {
                                                             echo 'Running the unit test'
                                                       }
                                     }
                                     stage('Integration test') {
                                                        agent {
                                                              docker {
                                                                       reuseNode false
                                                                       image 'ubuntu'
                                                              }
                                                        }
                                                        steps {
                                                            echo 'Running  the Integration test'
                                                        }
                                     }
                               }
             }
}

