pipeline {
    agent any
	tools {
        maven 'Maven 3.5.2'
        jdk 'jdk8'
		}
	
    stages {
		stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }
        stage ('Clone') {
            steps {
                git branch: 'master', url: "https://github.com/pushpendrad/emsdockerhub/ps://github.com/jfrog/project-examples.git"
            }
        }

        

        stage ('Exec Maven') {
            steps {
                rtMavenRun (
                    tool: MAVEN, // Tool name from Jenkins configuration
                    pom: 'emsdockerhub/pom.xml',
                    goals: 'clean install compile',
                    deployerId: "MAVEN_DEPLOYER",
                    resolverId: "MAVEN_RESOLVER"
                )
            }
        }

        stage ('Publish build info') {
            steps {
				sh '''
                    echo "Sucessfull!!"
                   
                '''
                
            }
        }
    }
}