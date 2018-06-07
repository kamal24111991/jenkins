

Assignment 1

Create Job DSL for

helloworld Job
hellotoperson Job (Take SALUTATION as choice parameter & NAME as string parameter)
Gitclone and list content of cloned directory
buildperiodically Job (This job will run by every 5 min)
pollscm Job (This job will have a poll interval of 2 min)

Solution :

freeStyleJob('helloworld Job') {

parameters { stringParam('Salutation', 'my default stringParam value', 'my description') stringParam('Name', 'my default stringParam value', 'my description') }

scm { git('https://github.com/kamal24111991/jenkins.git')

}

triggers {

cron('*/5 * * * * ')

}

steps {

shell('ls')

}

}
