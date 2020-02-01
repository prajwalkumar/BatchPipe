pipeline{
agent any
	stages{
		stage('Git-Checkout'){
			steps{
				echo 'checking out from git repo'
				git 'https://github.com/prajwalkumar/BatchPipe.git'
			}
		}
		stage('Build Test'){
			steps{
				echo 'Build Test'
				bat 'Build.bat'
			}
		}
		stage('Commit Test'){
			steps{
				echo 'Commit Test'
				bat label: '', script: 'Commit.bat'
			}
		}
		stage(‘Deploy’){
			steps{
				echo 'PASS'
			}
		}
	}
	post{
		always{
			echo 'This will always run'
		}
		success{
			echo 'This will only if successfull'
		}
		failure{
			echo 'This will only if failed'
		}
		unstable{
			echo 'This will always run'
		}
		changed{
			echo 'This will only if the state of the pipeline has changed'
			echo 'For example, if the pipeline was previously failing but is now successfull'
		}
	}
}


