pipeline {
    agent {
        label 'generic'
    } //agent
    stages {
        stage("Setup script") {
            steps {
                sh """
                    sudo yum install -y python-pip3
                    pip3 install --upgrade pip3
                    pip3 install pytest
                """
            } //steps
        } //stage
        stage("Run unit test") {
            steps {
                sh """
                    python3 -m pytest
                """
            } //steps
        } //stage
    } //stages
    post {
        always {
            sh """
                sudo pip3 uninstall pytest -y
            """
        } //always
    } //post
} //pipeline