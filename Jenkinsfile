node {
    //git branch: 'react-app', url:'https://github.com/namaliarahma/a428-cicd-labs'
    stage('Build') {
           docker.image("node:lts-bullseye-slim").inside{
                sh 'npm install' 
           
           }
    }
    stage('Test') { 
           docker.image("node:lts-bullseye-slim").inside{
                sh "chmod +x -R ${env.WORKSPACE}"
                sh './jenkins/scripts/test.sh' 
           }
    }
}
