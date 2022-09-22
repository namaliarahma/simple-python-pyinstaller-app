node {
    //git branch: 'react-app', url:'https://github.com/namaliarahma/a428-cicd-labs'
    stage('Build') {
           docker.image("node:python:2-alpine").inside{
                sh 'python -m py_compile sources/add2vals.py sources/calc.py' 
           
           }
    }
    stage('Test') { 
           docker.image("node:qnib/pytest").inside{
                sh "chmod +x -R ${env.WORKSPACE}"
                sh 'py.test --verbose --junit-xml test-reports/results.xml sources/test_calc.py' 
           }
           always {
                    junit 'test-reports/results.xml'
                }
    }
}
