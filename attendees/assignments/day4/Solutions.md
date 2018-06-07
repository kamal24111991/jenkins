freeStyleJob('helloworld Job') {
  parameters {
        stringParam('Salutation', 'my default stringParam value', 'my description')
    stringParam('Name', 'my default stringParam value', 'my description')
}

scm {
  git('https://github.com/kamal24111991/jenkins.git')

   }

   triggers {

   cron('*/5 * * * * ')

   }

   steps {

   shell('ls -al')

   } 


}
