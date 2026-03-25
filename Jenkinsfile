pipeline
{
	agent any
	tools
	{
		maven "maven3.9"
	}
	stages
	{
		stage ('Checkout')
		{
            steps
            {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/devops-revisit/petclinic-project'
            }
		}
        stage ('Build')
        {
            steps
            {
                sh "mvn clean compile"
            }
        }
        stage ('Test')
        {
            steps
            {
                sh "mvn clean test"
            }
        }
        stage ('Sonarqube checks')
        {
            steps
            {
                sh
                """
                mvn sonar:sonar \
                -Dsonar.projectKey=${JOB_NAME} \
                -Dsonar.projectName=${JOB_NAME}
                """
            }
        }
	}
}
