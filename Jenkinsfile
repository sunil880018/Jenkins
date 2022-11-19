CODE_CHANGES = getGitChanges() // check some code has pushed or changes on gitlab
pipeline{  // "pipeline" must be top level
    
    agent any // "agent" is where to execute? It can be linux,window etc

    stages{ // stages - where the work happens

        stage("build"){
           when{
                expression{
                    BRANCH_NAME == 'dev' && CODE_CHANGES == true // environment variables
                }
           }
           steps{
                 echo 'building application....'
                 sh 'npm install' // shell script
                 sh 'npm build' 
           }

        }

        stage("test"){
           when{
                expression{
                    BRANCH_NAME == 'dev' || BRANCH_NAME == 'master' // environment variables
                }
           }
           steps{
                echo 'testing application....'
           }

        }

        stage("deploy"){

           steps{
               echo 'deploying application....'
           }

        }

    }

    post{  // execute some logic after all the stages executed 
        always{  // condition

        }
        success{ // condition

        }
        failure{ // condition

        }
    }

}


node{
    // groovy script
}