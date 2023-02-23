## Historical perspective

Note: Before trying to convey what the hell is DevOps, CI/CD, GitOps or even why you should learn docker, I will tell a tale of the past. The intent here is to point the hardships we had on deploying software and how the industry reinvented itself to tackle all these challenges.
One disclosure note: I did not worked in the industry in the early 2000s, but I've heard stories, seen some legacy systems and have done a fair amount of research to try to portrait it.


## Early 2000s 

Note: The early two thousands was the childhood for web systems, and most of them were deployed on the simplest way around. For some home server, the developer would simply connect to a file browser or FTP client, upload their files on the server and restart it (Apache, Tomcat or something like that). Thinking simple, for static websites, we had only html and css, or even for interpreted languages like PHP we also had something along those lines. For some compiled languages, we had some forms of artifact that represented the application to be deployed. 

One thing to note here, we still didn't have the concept of cloud or whatsoever. We had physical servers and although the concept of virtualization is very old and known, only after additional hardware support was widespread by computer makers (around 2005~) that it became an accessible thing.

If you were not working by yourself in a small company, after you finished your feature, in fact, you were not the one assigned for deploying your app. Another team, called Operation (in short Ops), was responsible for deploying it, and making sure that your application was at least as stable as the other version, and that the server environment was ready for your new version. Developers would not be concerned at all about deploying new versions and Operations would treat new releases as an event, people would do that late at night, document every single step to put that on production and when things went awry would make change after change in production in order to stabilize the current version or rollback it. The feeling is that there was a big wall between those teams, and developers would simply throw new versions to the other side of the wall and people would magically put that on production, an event that could take some weeks or even months to happen. Developers sometimes didn't even give instructions to Operations team on how to run an application, they simply needed to figure out how.

Important to notice that this situation was a direct result on how the teams were instructed to operate and what they were trying to achieve. Often they were actually competing teams:
- Developers would be actively triyng to deploy new features and were rewarded for making them faster. They wanted to ship things more often. As they were not the ones that operated the system, they were not concerned at all on spending time instrumenting systems to be better operated.
- Operations work was measured by platform stability. The more stable the platform was the better for them, and the way they saw, new versions were ways of introducing new bugs and affect system stability. The bigger the update, the bigger was the chance of something going wrong. And everytime a deploy went wrong, Operations would try to understand why and create a process to avoid those types of errors, which in time would make deploy less often because it created more overhead on the process of deploying. 
As they were praised for stability, sometimes they didn't want to touch older systems that no one knew how to operate (if it's not broken don't touch it)

This is a vicious cycle which both IT Operations and Developers are doing an innefective job. The mentallity of the developer needed to stop of being: "What is important is to write code" to "What is important is the code that is running on production".


## 2007-Today

<div style="display: flex;">


![](https://cdn.ttgtmedia.com/rms/onlineImages/whatis-devops_over_time-f.png)

</div>
Note: As I'm telling a tale here, I might tell you more about the Agile movement perspective on this. Agile had taken the world by storm at that point, with extreme programming being one of the first successful agile frameworks implemented. 
At that time, Agile movement brought people that used to work on different steps of software development together. One of those once siloed teams were QA (tests) and Developers. Unsurprisingly, they had problems in a similar fashion that Ops and Developers. Once together testers taught developers on how to test more effectively and developers taught testers on how to automate more efficiently. Agile Philosophy was to optimize on an end to end perspective. 

To start our story on how it all began to change, we can speak of Patrick Debois, a software developer on Belgium. He was a contractor that was especially interested in working with all the possible perspectives of the IT world, thus picking jobs that helped him on that. He was working on a large data center migration, and his job was to make sure everything was tested and working right. Essentially, whis daily life was dealing with both Developers and Operations, on one day he was doing the Agile way with developers in other day he was firefighting with the Operations people. He knew that there must be a better way to do things.

Fastforward to 2008 where Andrew Schaefer posted on the wal of BoF (explain BOF here) called "Agile Infrastructure". The only person to ever show up to the session was Patrick Debois. Even Andrew didn't show up. But Patrick was so energized to have found someone with the same frustrations about the gaps between Dev and Ops that he tracked down him on the conference and started talking about it. They then found Google Group called "Agile System Administration"

Then there was another conference called "Velocity" which there was a now famous talk "10+ Deploys per DAy: Dev and Ops cooperation at Flickr". Patrick was watching the stream and thought that's it, that's exactly the topics that I'm passionate about, and he was salty he couldn't attend velocity. Other developer tweeted something like, why don't we start our own conference in Belgium so that we all can attend. And that stuck in Patrick head and he ended creating a conference. He wasn't very creative on the naming thought: he knew it was about Dev, it was about Ops, and well it was two days of conference, so he ended up with DevOpsDays.

For some reason, probably because of other conferences, but they had a great attendance of some outstading leaders on both communities from around the globe. After the conference everyone went back to home, and continued the conversation on Twitter, and as DevOpsDays was a hashtag that was too long, it was shortened to just DevOps. And an avalanche of blog posts, discussions and other editions of DevOpsDays were held, becoming a movement.

Practitioners would then started creating tools that helped those pain points we had talked about, and most of them were OSS.  Some of them had fun names like Puppet, Chef, Juju, Hudson (know known as Jenkins), Logstash, Capistrano.

And not long after that, some cosultants were aware and recommending "DevOps" tooling, and not long after that we had enterprise vendors picking it up and putting them on their portfolio. Turning it more and more mainstream.
