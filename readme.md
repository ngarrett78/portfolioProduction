## To deploy to the Staging Server, strict adherence to the following process is required.

---
####Get current copy of master branch from server
1. Merge Dev Branch into Master  
Upon completion of fully testing a new feature in your local dev environment merge the __newFeatureName Branch__ back into master.
 To do this successfully you will need to first pull the **remote master branch**, ensuring your **local master branch** is up to date.

   1. $ git checkout master

       1. Switches to the local master branch

   2. $ git pull **production** master

      1. **production** is the name of the remote repo we will use to differentiate between our other remote deployment servers

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


