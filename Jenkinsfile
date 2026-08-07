@Library('jenkins-shared-lib') _


properties([
    parameters([
        string(
            name: 'APP_VERSION',
            description: 'Application version'
        ),
        choice(
            name: 'ENVIRONMENT',
            choices: ['dev', 'qa', 'prod'],
            description: 'Target environment'
        ),
        booleanParam(
            name: 'DEPLOY',
            defaultValue: false,
            description: 'Deploy to EKS after build?'
        )
    ])
])


def configMap = [
    project: "roboshop",
    component: "user",
    aws_region: "us-east-1",
    appVersion: (params.APP_VERSION),
    environment: (params.ENVIRONMENT),
    deploy: (params.DEPLOY)
]

EKSDeploy(configMap)
