pipeline {
  agent any

  environment {
    NEW_VERSION = '1.3.0'
  }

  stages {

    stage("build") {
      steps {
        echo 'building the application...'
        echo "building new version ${NEW_VERSION}"
      }
    }

    stage("test") {
      when {
				expression {
					BRANCH_NAME == 'dev' || BRANCH_NAME == 'main'
				}
			}
      steps {
        echo 'testing the application...'
      }
    }

    stage("deploy") {

      steps {
        echo 'deploying the application...'
        echo "deploying with ${SERVER_CREDENTIALS}"
      }
    }

  }

}
