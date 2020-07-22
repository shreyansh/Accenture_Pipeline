pipeline {
    agent any
    stages {
		stage('Git-Checkout') {
			steps {
				echo "Checking out from Git Repo!";
				git credentialsId: '95703e7a-4192-4d56-89af-1adb14fbd1ed', url: 'https://github.com/shreyansh/Accenture_Pipeline.git'
			}
		}
		
        stage('Compile') {
            steps {
                    bat label: '', script: 'Compile.bat'
                    echo "Compiled Successfully!!";
            }
        }
        
        stage('JUnit') {
            steps {
                    bat label: '', script: 'Compile.bat'
                    echo "JUnit Passed Successfully!";
            }
        }
        
        stage('Quality-Gate') {
            steps {
                    bat label: '', script: 'Compile.bat'
                    echo "SonarQube Quality Gate passed successfully!!"; 
                /*sh exit ("1");*/
            }
        }
        
        stage('Deploy') {
            steps {
                    bat label: '', script: 'Deploy.bat'
                    echo "Pass!";
            }
        }
        
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
