node {
    stage 'Checkout'
    checkout scm

    stage 'Compilar'
    sh "./gradlew compileJava"

    stage 'Pruebas'
    sh "./gradlew test"

    stage 'Build'
    sh "./gradlew build"

    stage 'Liberar'
    archiveArtifacts artifacts: 'build/**/*.jar', fingerprint: true
}