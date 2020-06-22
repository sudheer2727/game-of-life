pipeline {
    agent any
    parameters {
        gitParameter name: 'PULL_REQUESTS', 
                     type: 'PT_PULL_REQUEST',
                     defaultValue: '1',
                     sortMode: 'DESCENDING_SMART'
    }
    stages {
        stage('Example') {
            steps {
                checkout([$class: 'GitSCM', 
                branches: [[name: "pr/${params.PULL_REQUESTS}/head"]], 
                doGenerateSubmoduleConfigurations: false, 
                extensions: [], 
                gitTool: 'Default', 
                submoduleCfg: [], 
                userRemoteConfigs: [[refspec: '+refs/pull/*:refs/remotes/origin/pr/*', url: 'https://github.com/jenkinsci/git-parameter-plugin.git']]])
            }
        }
        
        stage('Build') {
            steps {
                echo 'Hello, Maven'
                sh 'mvn clean install'
            }
        }
    }
}
