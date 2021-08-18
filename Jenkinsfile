pipeline{
    agent {label'GOL'}
    stages{
        stage('scm'){
            steps{
                git branch: 'master', url: 'https://github.com/Pruthviraj-Panda/openmrs-core.git'
            }
        }
        stage('build'){
            steps{
                sh 'mvn clean package'
            }
        }
    }
    post{
        success{
            archive '**/*.war'
            junit '**/TEST-*.xml'
        }
    }
}