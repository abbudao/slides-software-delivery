## Historical perspective

Note: Before trying to convey what the hell is DevOps, CI/CD, GitOps or even why you should learn docker, I will tell a tale of the past. The intent here is to point the hardships we had on deploying software and how the industry reinvented itself to tackle all these challenges.
One disclosure note: I did not worked in the industry in the early 2000s, but I've heard stories, seen some legacy systems and have done a fair amount of research to try to portrait it.


## 2000s 

Note: The early two thousands was the childhood for web systems, and most of them were deployed on the simplest way around. For some home server, the developer would simply connect to a file browser or FTP client, upload their files on the server and restart it (Apache, Tomcat or something like that). Thinking simple, for static websites, we had only html and css, or even for interpreted languages like PHP we also had something along those lines. For some compiled languages, we had some forms of artifact that represented the application to be deployed. 

One thing to note here, we still didn't have the concept of cloud or whatsoever. We had physical servers and although the concept of virtualization is very old and known, only after additional hardware support was widespread by computer makers (around 2005~) that it became an accessible thing.

If you were not working by yourself in a small company, after you finished your feature, in fact, you were not the one assigned for deploying your app. Another team, called Operation (in short Ops), was responsible for deploying it, and making sure that your application was at least as stable as the other version, and that the server environment was ready for your new version. Developers would not be concerned at all about deploying new versions and Operations would treat new releases as an event, people would do that late at night, document every single step to put that on production and when things went awry would make change after change in production in order to stabilize the current version or rollback it. The feeling is that there was a big wall between those teams, and developers would simply throw new versions to the other side of the wall and people would magically put that on production, an event that could take some weeks or even months to happen. Developers sometimes didn't even give instructions to Operations team on how to run an application, they simply needed to figure out how.

Important to notice that this situation was a direct result on how the teams were instructed to operate and what they were trying to achieve:
- Developers would be actively triyng to deploy new features and were rewarded for making them faster. They wanted to ship things more often. As they were not the ones that operated the system, they were not concerned at all on spending time instrumenting systems to be better operated.
- Operations work was measured by platform stability. The more stable the platform was the better for them, and the way they saw, new versions were ways of introducing new bugs and affect system stability. The bigger the update, the bigger was the chance of something going wrong. And everytime a deploy went wrong, Operations would try to understand why and create a process to avoid those types of errors, which in time would make deploy less often because it created more overhead on the process of deploying. 

This is a vicious cycle which both Operations and Developers are doing an innefective job. The mentallity of the developer needed to stop of being: "What is important is to write code" to "What is important is the code that is running on production".

## 2007


Note: Agile movement perspective
