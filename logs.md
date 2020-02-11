### current log process:
1. log into the server via RDP or v-sphere
2. go to `D:\Mulesoft\3.9.3\logs`
3. find the most recent application file named <application-#> where # is the highest number.
4. open the logs in a text editor and read to find errors.

above process
  - error prone
  - requires server access
  - must log into each server (both in our prod instance) to find logs
  - text editor searching -> slow
  - no trend analysis
  - **very reactive**

### a future process
1. applications ship logs to central logging service
2. one log service hosts all application logs properly tagged with env, machine, ip, application, etc
  1. this would show one server running fine while one is being attacked
3. those tags could be used for filtering results
  1. machine 1, prod, null pointer expection -> which apps have the most.
4. trend charts could be created from logs
  1. since logs are pushed to one service, this service could show number of xyz errors in prod or highest number of occurances per error.

above process
  - simple to search/query
  - gives trend analysis out of the box
  - does not require server/application/db access to view
  - easy to find/analyze error occurances to determine priority
  - error count monitoring for proactive support ie could see trends post/pre deployment of app

[ELK](https://www.elastic.co/webinars/introduction-elk-stack) does exactly this sort of logging.  
