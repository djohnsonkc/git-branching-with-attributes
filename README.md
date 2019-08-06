# git-branching-with-attributes
This is a sample project of how to use .gitattributes to ensure production releases do not point to a staging or dev environment

  // this file should be "locked" in the master branch and not honor any merge requests from other branches
  // create a new "staging" or "qa" branch and change DOMAIN to my-staging-domain.com
  