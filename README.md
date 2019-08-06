# git-branching-with-attributes
This is a sample project of how to use .gitattributes to ensure production releases do not point to a staging or dev environment

Good reference:
https://medium.com/@porteneuve/how-to-make-git-preserve-specific-files-while-merging-18c92343826b

config.json is a file that should be "locked" in the master branch and not honor any merge requests from other branches
to test, create a new "staging" or "qa" branch and change DOMAIN to my-staging-domain.com


git config --global merge.ours.driver true





  