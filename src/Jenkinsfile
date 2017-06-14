node {
	stage ('scm'){
		checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'Myfirstjob', url: 'https://github.com/Gimpleton/romannumerals.git']]])

	}
	stage('test'){
	sh 'mvn test'
	}
}