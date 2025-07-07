pipeline {
  agent {
    docker {
      image 'python:3.10'
    }
  }

  stages {
    stage('Install dependencies') {
      steps {
        sh '''
          python -m venv venv
          . venv/bin/activate
          pip install --upgrade pip
          pip install -r requirements.txt
        '''
      }
    }

    stage('Run FastAPI app') {
      steps {
        sh '''
          . venv/bin/activate
          python app/main.py
        '''
      }
    }
  }
}
