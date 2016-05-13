<<<<<<< HEAD
### To deploy to the Staging Server Strict adherence to the following process is required.

***


1. Merge Dev Branch into Master

*1. Upon completion of fully testing a new feature in

2. your local dev environment merge the newFeatureName Branch back into master. To do this successfully you will need to first pull the remote master branch, ensuring your local master branch is up to date.
$ git checkout master
Switches to the local master branch
$ git pull github master
github is the name of the remote repo we will use to differentiate between our other remote deployment servers
Resolve any conflicts
Visit each conflicted file and resolve any conflicts. This will require a saving.
Once conflicts are resolved and saved, they need committed and another pull of remote is required.
$ git add -A
$ git commit -am ‘Relevant detailed commit message.’
$ git pull github master
$ git merge newFeatureName
Resolve any conflicts (see 1.2.2)
Test 
You have just altered the code base since you last tested your new feature, additionally you might have broken someone else’s recent addition, congratulations! Take some time to work through and test out every aspect of your new feature.
Staged hubot addressed by a different name, Derpbot .
Derpbot only runs in the #staging_dwp channel on Slack.
If any of your tests fail the master branch is flawed, and not ready to be pushed to remote. Resolve the issues prior to pushing to the remote in the next step.
$ git push github master
Push your changes up to the shared repo so that other dev’s can react to the latest changes to the project codebase.
Tag Your Release
Not every commit is equal. Through the dev process many commits will take place, but when releasing a new feature the commit that is merged and promoted live is more significant than others. By tagging this fully merged commit we are able to diagnose issues or discuss a specific version of the project.
$ git tag -a vX.X.X -m ‘Release Code or Feature Name ’
X.X.X should be an incriminated according to the Versions Numbering Development Policy.
$ git push github --tags
Tags are not automatically pushed in a normal push, they must be manually pushed to the remote repo.
Communicate with your Team
Announce to your team that you are about to change the staging server. If someone else is currently testing on the staging server you will need to coordinate for when you can promote your code in the next step.
Verify the testing of the last feature to be promoted has completed.
Promote to Staging
Promote your tested code to the staging environment to ensure stability within the overall system.
$ git push staging master
staging is linked to the --remote staging heroku server
Test Again!
If anything fails, try to replicate the issue within your Local Dev Environment. Should the issue not be replicable there identify why it isn’t working in Staging and attempt to solve the problem. Sounds like a great reason to make a new local dev branch and start all over!
Communicate Successful Promotion of New Feature
Brag a little about how sweet your new feature is! Ideally this will promote other users to try it out thereby testing it further prior to going live in production.
Use the hastag #newFeatureStaged in the #staging_dwp channel. Identify the name of your feature, that it has been completed, and any info on how to use it not provided in Derpbot’s help command.
When the scheduled promotion of Staging to Production occurs you will need to test every feature that has been recently staged to make sure that your co-workers have not accidentally, or intentionally =P, modified the feature.
=======
## To deploy to the Staging Server, strict adherence to the following process is required.

---
####Get current copy of master branch from server
1. Merge Dev Branch into Master  
Upon completion of fully testing a new feature in your local dev environment merge the __newFeatureName Branch__ back into master.
 To do this successfully you will need to first pull the **remote master branch**, ensuring your **local master branch** is up to date.

   1. $ git checkout master

       1. Switches to the local master branch

   2. $ git pull **staging** master

      1. **staging** is the name of the remote repo we will use to differentiate between our other remote deployment servers

      2. Resolve any conflicts

         1. Visit each conflicted file and resolve any conflicts. This will require a saving.

            1. Once conflicts are resolved and saved, they need to be committed and another pull of remote is required.

               1. `$ git add -A`
               2. `$ git commit -am 'Relevant detailed commit message.'`  
                  * -a  = automatically stage all tracked, modified files before the commit  
                  * -m = leave a descriptive message for your committ
               3. `$ git pull staging master`


  3. $ git merge **newFeatureName**

     1. Resolve any conflicts (see 1.2.2)

1. **Test**  
You have just altered the code base since you last tested your new feature. Test out every aspect of your new feature.
   1. If any of your tests fail the master branch is flawed, and not ready to be pushed to remote. Resolve the issues prior to pushing to the remote in the next step.

3. **Promote to Staging**  
Promote your tested code by pushing the changes to the staging repo on to the staging environment to ensure stability within the overall system.

    1. $ git push staging master
       1. staging is linked to the --remote staging server

4. **Test Again!**  
If anything fails, try to replicate the issue within your Local Dev Environment. Should the issue not be replicable there identify why it isn’t working in Staging and attempt to solve the problem. Sounds like a great reason to make a new local dev branch and start all over!
>>>>>>> f00cf4d99d435af582eae924b6d998b97166c0f4
