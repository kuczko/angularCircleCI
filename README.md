# 2nd task

Please optimise the pipeline to follow the Continuous Deployment approach.

Things to consider are:
- how would you optimize the build for speed?
  - Added workspace saving to not clone and apply git diff at each job step
  - Added npm modules caching
  - Added docker cache (commented out as plan does not support it)
  
- how would you notify the team if something went wrong?
- how would you implement feature flags?
- how do feature flags affect testing?
- what is your roll back strategy?
- please take adventage of smoke tests
  - Added smoke tests after each deployment 
- please add a job for acceptance tests
- assuming that acceptance test can run 1 hour but developers can push multiple times a day, how do you solve a problem of running these tests?
- What is your zero down time deployment strategy?
