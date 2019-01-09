pipeline {
    agent any
	
	
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
                git branch: 'master', url: "https://github.com/aakankshi/emsdockerhub.git"
            }
        }

        

        stage ('Exec Maven') {
            steps {
                //rtMavenRun (
                    //tool: MAVEN, // Tool name from Jenkins configuration
                    //pom: 'emsdockerhub/pom.xml',
                    //goals: 'clean install',
		    sh 'mvn clean install complie'
                    //deployerId: "MAVEN_DEPLOYER",
                    //resolverId: "MAVEN_RESOLVER"
                //)
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
