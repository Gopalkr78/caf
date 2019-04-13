	job('test1') {
    publishers {
        deployToWeblogic {
            mustExitOnFailure()
            forceStopOnFirstFailure()
            task {
                weblogicEnvironmentTargetedName('dev_environment')
                deploymentName('myApplicationName')
                deploymentTargets('AdminServer')

                builtResourceRegexToDeploy('test\\.war')
                taskName('Deploy myApp to DEV Server')

                jdkName('JDK_8')
                jdkHome('/usr/bin/java')

                stageMode(WeblogicDeploymentStageModes.STAGE)

                commandLine('-debug -remote -verbose -name {wl.deployment_name} -targets {wl.targets} ' +
                        '-adminurl t3://{10.5.203.135}:{7003} -user {weblogic} -password {weblogic@123} ' +
                        '-undeploy -noexit;')
				commandLine('-debug -remote -verbose -name {wl.deployment_name} -source {wl.source} ' +
                        '-targets {wl.targets}-adminurl t3://{10.5.203.135}:{7003} -user {weblogic} ' +
                        '-password {weblogic@123} -deploy -stage -upload;')
            }
        }
    }
}
