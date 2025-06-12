pipeline {
agent any
tools {
maven 'Maven 3.9.10'
jdk 'JDK17'
}
stages {
stage('Clonar') {
steps {
git branch: 'main', url: "${params.URL}"
}
}
stage('Compilar') {
steps {
sh 'mvn clean compile'
}
}
stage('Probar') {
steps {
sh 'mvn test'
}
}
stage('Empaquetar') {
steps {
sh 'mvn package'
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
