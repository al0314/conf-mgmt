pipeline {
    agent any
    stage("checkout source"){
        steps{
            git 'http://gitrepo.com'
        }
    }
    stage('build'){
        steps{
            sh 'docker build -t myfastapiapp'
        }
    }
    stage('test'){
        steps{
            sh 'pip install --no-cache-dir -r requirements.txt'
            sh 'pip install pytest'
            sh 'pytest ./app/tests'
        }
    }
    stage('deploy'){
        steps{
            docker start myfastapiapp
        }
    }
}