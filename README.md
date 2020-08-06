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
  - It might be setting in database, which application will query. Best if it can query it in some intervals/on-request to update application behavior without restarting.

- how do feature flags affect testing?
  - We should test application with features switched on and off and validate results

- what is your roll back strategy?
  - This is difficult question for me, for unknown application/company. In order to fix problem we can either rollback application version or change feature flag on failing 
    functionality. If we would have Continous Deployment, then also we need to ensure that next version which will get deployed will have problem causing rollback fixed. Application
    should be stored as docker container in some docker registry with version/date information available. We should have also history of versions deployed and have a process to
    revert to 'safe enough' version (as if we have    Continous Deployment, we might have many versions deployed same day. And often we will not know which version introduced a bug.
    This process should be probably built using experience with issues from past. This can be also impacted by "backward compatibilty" of database - "how much" compatible it is going
    back.

- please take adventage of smoke tests
  - Added smoke tests after each deployment 

- please add a job for acceptance tests

- assuming that acceptance test can run 1 hour but developers can push multiple times a day, how do you solve a problem of running these tests?

- What is your zero down time deployment strategy?
  - Assuming that application can run in parallel and database updates are non-blocking, then we can just bring new application, check if it runs(smoke tests?) and replace target on
    load balancer (blue/green deployment). This can be also improved by using canary deployment strategy - redirecting only part of traffic to new version, while still running old 
    version for another part of traffic. Out of the box solution for this is for example CodeDeployment with ECS on AWS, but it can be also implemented as part of deployment process 
    in pipeline which can improve customization possibilities. 

