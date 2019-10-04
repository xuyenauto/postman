pipeline{
    agent{
        label "master"
    }
    stages{
        stage('Run scripts'){
            steps{
                 echo "Hello World!"
                 bat 'cd'
                 bat 'newman run --disable-unicode topdm_api_investigate.postman_test_run.json -e QA_ENV_Practice.postman_environment.json -r html myreport --reporter-html-export "./report.html" exit 1'
            }
        }
        stage('Add report'){
            steps{
                publishHTML([allowMissing: false, alwaysLinkToLastBuild: true, keepAll: false, reportDir: './', reportFiles: 'report.html', reportName: 'API test Report', reportTitles: ''])
            }
        }
    }
}