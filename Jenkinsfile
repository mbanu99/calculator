pipeline {
    agent {
        label 'generic'
    } //agent
    stages {
        stage("Setup script") {
            steps {
                sh """
                    sudo yum install -y python-pip
                    pip2 install --upgrade pip2
                    pip2 install pytest
                """
            } //steps
        } //stage
        stage("Run unit test") {
            steps {
                sh """
                    python2 -m pytest
                """
            } //steps
        } //stage
    } //stages
    post {
        always {
            sh """
                sudo pip2 uninstall pytest -y
            """
        } //always
    } //post
} //pipeline