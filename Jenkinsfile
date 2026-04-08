pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: '<your-repo-url>'
            }
        }

        stage('Build') {
            steps {
                sh 'echo "Listing files"'
                sh 'ls -la'
            }
        }

        stage('Test') {
            steps {
                sh '''
                python3 - <<EOF
import calculator
assert calculator.add(2,3) == 5
assert calculator.subtract(5,3) == 2
assert calculator.multiply(2,3) == 6
assert calculator.divide(6,3) == 2
print("All tests passed")
EOF
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh 'echo "Deploy stage placeholder"'
            }
        }
    }
}
