// Powered by Infostretch 

timestamps {

node () {

	stage ('Dev Compile - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '96360fdc-7326-4a73-905b-941ad7c667a6', url: 'https://github.com/sulimusa/DevOpsClassCodes.git']]]) 
	}
	stage ('Dev Compile - Build') {
 			// Maven build step
	withMaven(maven: 'my_maven') { 
 			if(isUnix()) {
 				sh "mvn compile " 
			} else { 
 				bat "mvn compile " 
			} 
 		} 
	}
	stage ('Dev CodeReview - Build') {
 			// Maven build step
	withMaven(maven: 'my_maven') { 
 			if(isUnix()) {
 				sh "mvn -P metrics pmd:pmd " 
			} else { 
 				bat "mvn -P metrics pmd:pmd " 
			} 
 		} 
	}
}
}