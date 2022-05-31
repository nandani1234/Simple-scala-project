pipeline {
    agent {
        docker {
            image 'sbtscala/scala-sbt:8u332_1.6.2_2.12.15'
            // args '-v ~/.ivy2:/root/.ivy2 -v ~/.sbt:/root/.sbt -v $PWD:/app -w /app'
            args '-u sbtuser -w /home/sbtuser'
    }}

    stages {

        stage('Compile') {
            steps {
                echo "Compiling..."
                sh "sbt/bin/sbt compile"
            }
        }

        stage('Test') {
            steps {
                echo "Testing..."
                sh "sbt test"
            }
        }

        stage('Package') {
            steps {
                echo "Packaging..."
                sh "sbt package"
            }
        }

    }
}
