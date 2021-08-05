pipeline{
 
    agent{
        docker {
            image 'ubuntu'
            label 'agent'
        }
        
    }
    environment
    {
        CITY_NAME ='menouf'
        GIT_HUB_CRE = credentials('github_cred')
    }
    triggers{ githubPush()}
    stages{
        stage('stage1-sequance')
        {
            steps{
                echo "welcome from ${CITY_NAME}"
                echo "myname is ${GIT_HUB_CRE_USR}"
                
            }
        }
        stage('stage2')
        {
            parallel{
                stage('stage2-1-parralel'){
                    steps{
                        echo 'welcome from stage2-1-parralel'
                    }
                }
                stage('stage2-2-parralel'){
                    steps{
                        echo 'welcome from stage2-2-parralel'
                    }
                }
            }
        }
    }
        post{
            failure{
                echo "from post failure"
            }
            
        }
    
}
