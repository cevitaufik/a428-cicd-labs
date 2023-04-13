node('node:16-buster-slim') {
    docker.image('node:16-buster-slim').inside('-p 3000:3000') {
        try {
            stage('Build') {
                sh 'npm install'
            }
            stage('Test') {
                sh './jenkins/scripts/test.sh'
            }
        } catch (Exception e) {
            echo "Terjadi kesalahan: ${e.message}"
        } finally {
            echo 'selesai'
        }
    }
}