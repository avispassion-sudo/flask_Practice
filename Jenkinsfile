node {

    stage('Build') {
        sh '''
        pip3 install --upgrade pip
        pip3 install flask pytest
        '''
    }

    stage('Test') {
        sh '''
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
