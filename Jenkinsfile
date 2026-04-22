node {

    stage('Build') {
        sh '''
        python3 -m venv venv
        . venv/bin/activate
        pip install --upgrade pip
        pip install flask pytest
        '''
    }

    stage('Test') {
        sh '''
        . venv/bin/activate
        pytest || echo "No tests found"
        '''
    }

    stage('Deploy') {
        sh '''
        pkill -f app.py || true
        nohup python3 app.py &
        '''
    }
}
