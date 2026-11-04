pipeline {
    agent any
    options {timestamps()}
    stages {
        stage('Cloner le dépôt'){
            steps {
                git url: 'https://github.com/Wiem-kb/projetJenkins.git', branch: 'main'
            }
        }
        stage('Étape 1 : Vérification du dépôt'){
            steps {
                bat 'echo === Étape 1 : Vérification du dépôt ==='
                bat 'git status'
            }
        }
        stage('Étape 2 : Afficher le contenu du projet') {
            steps {
                bat 'echo === Étape 2 : Afficher le contenu du projet ==='
                bat 'dir'
            }
        }
        stage('Étape 3 : Vérifier l\'existence de la balise h1') {
            steps {
                bat 'echo === Étape 3 : Vérification de la balise h1 dans text.html ==='
                bat 'findstr /i "<h1" text.html'
            }
        }
        stage('Étape 4 : Simuler un déploiement local') {
            steps {
                bat 'echo === Étape 4 : Simuler un déploiement local ==='
                bat 'echo Le fichier index.html est prêt à être affiché'
            }
        }
        stage('Étape 5 : Fin du build'){
            steps {
                bat 'echo === Étape 5 : Fin du build ==='
                bat 'echo SUCCESS'
            }
        }
    }
    post {
        success { 
            echo ' Build OK'
        }
        failure { 
            echo ' Build KO : La balise h1 est introuvable ou le fichier text.html est absent.' 
        }  
    }
}
