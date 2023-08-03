@Library('mylib')_

pipeline
{
    agent any
    stages
    {
        stage('ContDownload_Master')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("maven")
                }
            }
        }
        stage('ContBuild_Master')
        {
            steps
            {
                script
                {
                    cicd.mavenBuild()
                }
            }
        }
        stage('ContDeployment_Master')
        {
            steps
            {
                script
                {
                    cicd.tomcatDeploy("DeclarativePipleinewithSharedLibraries","172.31.16.88","testapp")
                }
            }
        }
        stage('ContTesting_Master')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("FunctionalTesting")
                    cicd.runSelenium("DeclarativePipleinewithSharedLibraries")
                }
            }
        }
        stage('ContDelivery_Master')
        {
            steps
            {
                script
                {
                    cicd.tomcatDeploy("DeclarativePipleinewithSharedLibraries","172.31.22.249","prodapp")
                }
                
            }
        }
        
        
        
        
    }
}
