// Powered by Infostretch 

timestamps {

node () {

	stage ('Developer Compile - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '4cf7e508-a3cd-43af-8bb2-f20d17c45c59', url: 'https://github.com/sulimusa/DevOpsClassCodes.git']]]) 
	}
	stage ('Developer Compile - Build') {
 			// Maven build step
	withMaven(maven: 'my_maven') { 
 			if(isUnix()) {
 				sh "mvn compile " 
			} else { 
 				bat "mvn compile " 
			} 
 		} 
	}
	stage ('Developer Code Review - Build') {
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