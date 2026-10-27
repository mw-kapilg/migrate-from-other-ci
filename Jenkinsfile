pipeline {
    agent { label 'linux-matlab' }

    environment {
        PATH = "/usr/local/MATLAB/R2026a/bin:${env.PATH}"
    }

    triggers {
        githubPush()
    }

    stages {
        stage('Run MATLAB Tests') {
            steps {
                runMATLABTests(
                    sourceFolder: ['src'],
                    selectByFolder: ['tests'],
                    testResultsJUnit: 'results/test-results.xml',
                    codeCoverageCobertura: 'results/coverage.xml'
                )
            }
        }
    }

    post {
        always {
            junit 'results/test-results.xml'
            recordCoverage(tools: [[parser: 'COBERTURA', pattern: 'results/coverage.xml']])
            archiveArtifacts artifacts: 'results/**', allowEmptyArchive: true
        }
    }
}
