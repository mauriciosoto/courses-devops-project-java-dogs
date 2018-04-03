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
}