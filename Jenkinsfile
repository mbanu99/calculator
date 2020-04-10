pipeline {
    agent {
        label 'generic'
    } //agent
    stages {
        stage("Setup script") {
            steps {
                sh """
                    yum install pytest
                """
            } //steps
        } //stage
        stage("Run unit test") {
            steps {
                sh """
                    python -m pytest
                """
            } //steps
        } //stage
    } //stages
    post {
        always {
            sh """
                yum uninstall pytest -y
            """
        } //always
    } //post
} //pipeline