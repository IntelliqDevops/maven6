@Library('newlibrary')_

pipeline
{
    agent any
    stages
    {
        stage('Cont Download')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("maven")
                }
            }
        }
        stage('Cont Buold')
        {
            steps
            {
                script
                {
                    cicd.buildArtifact()
                }
            }
        }
        stage('Cont Deployment')
        {
            steps
            {
                script
                {
                    cicd.deployTomcat("DeclarativePipelinewithSharedLibraries","172.31.29.188","testapp")
                }
            }
        }
        stage('Cont Testing')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("FunctionalTesting")
                    cicd.runSelenium("DeclarativePipelinewithSharedLibraries")
                }
            }
            
        }
        stage('Cont Delivery')
        {
            steps
            {
                script
                {
                    cicd.deployTomcat("DeclarativePipelinewithSharedLibraries","172.31.17.234","prodapp")
                }
            }
        }
        
    }
}
