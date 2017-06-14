node {
	stage ('scm'){

		checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'Myfirstjob', url: 'https://github.com/Gimpleton/romannumerals.git']]])

	}
	stage('Build') {

		if (isUnix()) {
         sh "mvn -Dmaven.test.failure.ignore clean package"
		}

	}

	stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archive 'target/*.jar'
	}
}