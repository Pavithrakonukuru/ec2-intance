pipeline {
    agent any

    environment {
        AWS_DEFAULT_REGION = 'us-west-2' // Replace with your AWS region
        STACK_NAME = 'MyEC2Stack' // Replace with your desired CloudFormation stack name
        TEMPLATE_FILE = 'ec2.yaml' // Replace with the path to your CloudFormation template file
    }

    stages {
        stage('Deploy CloudFormation Stack') {
            steps {
                script {
                    withAWS(region: AWS_DEFAULT_REGION, credentials: 'aws-credentials-id') {
                        sh "aws cloudformation deploy --stack-name ${STACK_NAME} --template-file ${TEMPLATE_FILE} --capabilities CAPABILITY_NAMED_IAM"
                    }
                }
            }
        }
    }
}
