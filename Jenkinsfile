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
	}
}
