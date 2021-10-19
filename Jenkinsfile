pipeline {
    agent any

    stages {
        stage('release') {
            steps {
                echo "${build_type}"
              build job: 'release', parameters: [[$class: 'StringParameterValue', name: 'build_type', value: "${build_type}"]]
            }
        }
        stage('deploy_cloud') {
            steps {
              build job: 'deploy_cloud', parameters: [[$class: 'StringParameterValue', name: 'build_type', value: "${build_type}"], [$class: 'StringParameterValue', name: 'deploy_type', value: "QA"], [$class: 'StringParameterValue', name: 'artifact_version', value: "${artifact_version}"]]
            }
        }
    }
}
