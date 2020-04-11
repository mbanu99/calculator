pipeline {
    agent {
        label 'generic'
    } //agent
    stages {
        stage("Setup script") {
            steps {
                sh """
                    sudo yum install -y python-pip
                    pip install --upgrade pip
                    pip install pytest
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
                pip uninstall pytest -y
            """
        } //always
    } //post
} //pipeline