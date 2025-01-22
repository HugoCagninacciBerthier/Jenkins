pipeline {
    agent any
 
    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/<ton-utilisateur>/<ton-depot>.git'
            }
        }
 
        stage('Compile') {
            steps {
                echo 'Compilation du code source'
                sh 'javac -d out src/calculator.java'
            }
        }
 
        stage('Run Unit Tests') {
            steps {
                echo 'Exécution des tests unitaires...'
                sh 'javac -d out -cp "out:libs/*" tests/CalculatorTest.java'
                sh 'java -cp "out:libs/*" org.junit.runner.JUnitCore CalculatorTest'
            }
        }
        stage('Quality Check') {
            steps {
                echo 'Vérification de la qualité du code (facultatif si nécessaire)'
                // Intégrer ici des outils comme Checkstyle, PMD, FindBugs si tu en as besoin
            }
        }
 
        stage('Deploy') {
            steps {
                echo 'Déploiement de l\'application'
                // Ajoute ici ton code de déploiement
            }
        }
    }
 
    post {
        success {
            echo "Le pipeline a réussi!"
        }
        failure {
            echo "Le pipeline a échoué."
        }
    }
}
