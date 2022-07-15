---
layout: post
title: 2022 SW Coaching 6th Code Review
categories : Spring
---
# After I add google login function, all of test codes didn't work. 

## Problems and Solution
1.      
      - I wrote in build.gradle as below.  

       ``` compleOnly('org.springframework boot:spring-boot-starter-oauth2-client') ```  

      - Solution:  chage it to  

        ``` implementation 'org.springframework.boot:spring-boot-starter-oauth2-client' ```
2. 

      
      In intellij there is file name "External Libraries".
    Click the file then, open "\org\springframework\session\jdbc\schema-mysql.sql" 

  ![_config.yml]({{ site.baseurl }}/images/External_Libraries .jpg)    

  ![_config.yml]({{ site.baseurl }}/images/session.jpg)  

 Then, click the green one and your db name.

   ![_config.yml]({{ site.baseurl }}/images/session_sql.jpg)  
  
  ![_config.yml]({{ site.baseurl }}/images/sessiondb.jpg)  

Done!