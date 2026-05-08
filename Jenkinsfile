pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Stage 1: Build'
                echo 'Task: Compiling and packaging the application source code.'
                echo 'Tool: Maven - used to compile Java source files and package them into a JAR/WAR artifact.'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'Stage 2: Unit and Integration Tests'
                echo 'Task: Running unit tests to verify individual components, and integration tests to verify component interactions.'
                echo 'Tools: JUnit (unit testing), TestNG (integration testing).'
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'Stage 3: Code Analysis'
                echo 'Task: Analysing source code for code smells, bugs, and adherence to coding standards.'
                echo 'Tool: Checkstyle integrated via Jenkins plugin - enforces Java coding standards and flags violations.'
            }
        }

        stage('Security Scan') {
            steps {
                echo 'Stage 4: Security Scan'
                echo 'Task: Scanning application dependencies and source code for known CVEs and security vulnerabilities.'
                echo 'Tool: OWASP Dependency-Check - identifies vulnerable third-party libraries in the project.'
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'Stage 5: Deploy to Staging'
                echo 'Task: Deploying the packaged application artifact to a staging server for pre-production testing.'
                echo 'Tool: AWS CLI - used to deploy the application to an AWS EC2 staging instance via SCP/SSH.'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'Stage 6: Integration Tests on Staging'
                echo 'Task: Running integration tests against the staging environment to validate production-like behaviour.'
                echo 'Tool: Selenium WebDriver - automates browser-based end-to-end tests against the staged application.'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Stage 7: Deploy to Production'
                echo 'Task: Deploying the fully validated application artifact to the live production server.'
                echo 'Tool: AWS CLI - deploys the application to an AWS EC2 production instance after all tests pass.'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully. All stages passed.'
        }
        failure {
            echo 'Pipeline failed. Please review the console output.'
        }
    }
}
