pipeline{
    agent{
        label "node"
    }
    stages{
        stage('Run scripts'){
            sh '''
                    newman run --disable-unicode topdm_api_investigate.postman_test_run.json -e QA_ENV_Practice.postman_environment.json
                     -r html myreport --reporter-html-export "./report.html" exit 1
                '''
        }
    }
}