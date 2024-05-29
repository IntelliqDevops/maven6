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
        
    }
}
