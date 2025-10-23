pipeline {
    agent any                // Runs the pipeline on any available Jenkins agent (machine or node)

    stages {                 // Defines different stages (phases) in the pipeline workflow
        stage('Compile') {   // Stage 1: Compilation
            steps {          // Each stage has "steps" that define what to do
                bat 'mvn compile'   // Runs the Maven "compile" command in Windows (bat = batch)
            }
        }

        stage('Unit Test') {  // Stage 2: Unit Testing
            steps {
                bat 'mvn test'     // Runs the Maven "test" command to execute unit tests
            }
        }
    }
}
