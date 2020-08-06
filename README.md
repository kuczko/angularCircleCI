# 2nd task

Please optimise the pipeline to follow the Continuous Deployment approach.

Things to consider are:
- how would you optimize the build for speed?
  - Added workspace saving to not clone and apply git diff at each job step
  - Added npm modules caching
  - Added docker cache (commented out as plan does not support it)
  - Added example of running parallel tests scenario packs for e2e tests - this can be used for each type of tests which are too long to be accepted.
 
- how would you notify the team if something went wrong?
  - Added slack notification for each job. Better version would be to create custom job, which would notify person merging change/making commit - it would limit spam on the 
    notification channel.

- how would you implement feature flags?
- how do feature flags affect testing?
- what is your roll back strategy?
- please take adventage of smoke tests
  - Added smoke tests after each deployment 
- please add a job for acceptance tests
- assuming that acceptance test can run 1 hour but developers can push multiple times a day, how do you solve a problem of running these tests?
- What is your zero down time deployment strategy?
