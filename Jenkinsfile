node {
    stage 'Checkout'
    checkout scm

    stage 'Compilar'
    sh "./gradlew compileJava"

    stage 'Pruebas unitarias'
    sh "./gradlew test"

    stage 'Pruebas Integradas'
    sh "./gradlew integrationTest"

    stage 'Build'
    sh "./gradlew build"

    stage 'Liberar'
    archiveArtifacts artifacts: 'build/**/*.jar', fingerprint: true

    stage 'Notificar'
    emailext attachLog: true, body: 'Se adjuntan los resultados del build', subject: 'Resultados del pipeline', to: 'msoto@optimisa.cl'

}