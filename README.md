# git-branching-with-attributes
This is a sample project of how to use .gitattributes to ensure production releases do not point to a staging or dev environment

Good reference:
https://medium.com/@porteneuve/how-to-make-git-preserve-specific-files-while-merging-18c92343826b

In this example, config.json is a file that should be "locked" in the master branch and not honor any merge requests from other branches
To test, create a new "staging" or "qa" branch and change DOMAIN to my-staging-domain.com. You should see that config.json, in master, is unchanged by any merges from other branches.


Configuration:
-----------------------------------------------------

1) Start in the master branch

2) Create a custom driver called "ours": git config --global merge.ours.driver true

3) Create a .gitattributes file in the root of the project with the following contents: config.json merge=ours

4) Commit and push these changes to master


Testing
-----------------------------------------------------

1) Still in master, create a new feature branch from master: git checkout -b my-feature master

2) Make a change to config.json and commit the change:  
git add .  
git commit -m "my-feature change to config.json"  
git push  

3) Switch back to master and merge my-feature into master:  
git checkout master  
git merge my-feature  

4) Confirm that config.json is unchanged by the merge from my-feature









  