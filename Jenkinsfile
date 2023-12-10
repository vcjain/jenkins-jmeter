pipeline {
    agent any
    tools {
      maven 'maven3'
    }
    stages {
        stage('checkout'){
            steps{
                checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/vcjain/jenkins-jmeter.git']])
            }    
        }
        stage('Build'){
            steps{
                echo 'Building Maven project'
                sh 'mvn compile'
            }
        }
        stage('jmeter') {
            steps {
                echo 'Running jmeter test'
                
                sh '''/opt/jmeter/bin/jmeter -jjmeter.save.saveservice.output_format=xml -n -t ${WORKSPACE}/simplilearn.jmx -l ${WORKSPACE}/report.jtl'''
            }
        }
        stage('publish jmeter report'){
            steps{
                perfReport filterRegex: '', showTrendGraphs: true, sourceDataFiles: 'report.jtl'
            }
        }
    }
}
