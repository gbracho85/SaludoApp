pipeline {
agent any
tools {
maven 'Maven'
jdk 'JDK17'
}
stages {
stage('Clonar') {
steps {
git branch: 'main', url: "https://github.com/gbracho85/SaludoApp.git"
}
}
stage('Compilar') {
steps {
bat 'mvn clean compile'
}
}
stage('Probar') {
steps {
bat 'mvn test'
}
}
stage('Empaquetar') {
steps {
bat 'mvn package'
}
}
}
post {
success {
echo "🎉 El build fue exitoso"
}
failure {
echo "💥 El build falló"
}
}
}
