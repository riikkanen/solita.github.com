---
layout: post
title: Why a developer should know OWASP?
author: riikkanen
excerpt: 
tags:
 - 
---

OWASP stands for Open Web Application Security Project. Why should I be interested in OWASP as a developer? If I'm not a hacker or cyber security specialist, and we don't even handle any sensitive information in our project, can I just skip the OWASP? Well, the answer is "nope".

# Different projects, different requirements

If you think about a big patient information system used in hospitals, it is obvious that information security has to be concerned in every phase of building such a system: in planning, implementation, and testing. The system contains sensitive data, e.g. social security numbers and personal medical reports. In addition to the valuable content, the system might interest hackers because it most likely has integrations to other critical information systems. The patient information system must have rescricted access, strong authentication, audit logging and what not. You might rightfully presume that the project team includes also hard-boiled information security professionals.

How about a web store? It differs from a patient information system because it's by default avaible to everyone. However, also the web store contains information that must be protected: the customer information, accounts, credit card information, purchase history, and so on. It would also be nice if the purchase event is secure and reliable. If one thinks about big web stores like Amazon, one can predict that information security is tightly entwined in building the whole system. On the contrary, we cannot be so sure about smaller web stores. Are the building blocks of the store something which are widely used and acknowledged or has someone coded, for example, authentication by themselves?

Last but not least let's think about implementing a simple feedback form to an existing web site. Well, implementing a simple feedback form sounds quite easy and straight-forwards task and it might look like we don't need to consider information security at all. However, a simple feedback form can provide a way for a hacker to harm other parts of the system, for example, by using an SQL injection. The form can also tempt spam bots, either filling your database (and site) with numerous falsy feedbacks or misusing the form to relay email spam messages to others. Furthermore, if we collect the user names, phone number and hometown, it quickly becomes a person registry, where the data must be protected.

# All software projects are also information security projects

As we can see, the information security must be considered in software projects of any size. Also, the information security is something you can't just add on the top of the software afterwards. It has to be taken into account from the beginning, already in the planning phase. The baseline of information security should be something you can just rely on. Just as you expect to get the software with good quality, you should get a secure software.

Of course there are software projects where the baseline of the information security must be higher and achieving that level costs more money. However, I like to think that implementing basic things in a secure way does not increase costs. If you decide to do, for example, SQL queries in a way where SQL injection is impossible from the beginning, it takes as much time as making them in a less secure way. The costs increase only if you first make them in a less secure way, and then in more secure way afterwards.

![Bobby Tables we call him](/img/why-owasp/exploits_of_a_mom.png)
Bobby Tables we call him, classic from [https://xkcd.com/327/](https://xkcd.com/327/)

In a software project the possible risks must be examined carefully and sufficient security level needs to be decided. If the information system is going to be used in restricted network by a certain amount of users, you might not need the same amount of security as in open banking systems. However, it is a desicion which need to be done knowingly. 

# Where the information security comes from?

The information security in a project comes from people. Depending of the project there might be some security specialists but all the people involved in the project need to aware of security issues.

One security aspect are the practises used in the project. Do people behave in a secure way? When working on a project, you can't tell everyone about it, at least not in detailed level. You must not keep your passwords on post-its, you should use always good passwords, perhaps utilize a password manager, and enable multifactor authentication whenever it's possible. Do not push sensitive data, such as database passwords, to version control. Use VPN instead of unprotected WLANs. Recognize if the risk is bareable before pasting project specific things into third party services, like pastebin, xml validator or some language translator. After all that the other aspect is being aware of different security threats which exists in a digital environment. 

The developers are basically problem solvers. We need to solve a problem which is given to us. Sometimes the problem is easy and simple to solve. However, just solving the problem might not be enough. For example, a testing specialist might find a bug from the implementation in seconds. They have a different point of view, and typically try all the nasty corner cases. Does this work with empty input? Or with negative numbers? If the developer is experienced they have been already taken care of all those corner cases. Also the hackers have a different point of view. They are used to finding vulnerabilities from the software. To be able to secure the software, also the developers must be aware of the threats. 

# This is where OWASP comes in

The developers should be aware of the threats, but how. One way is to familiarize with the OWASP material. OWASP stands for Open Web Application Security Project, and it has produced a significant amount of material of most common information security vulnerabilites and published in the internet. There are several detailed examples and also a web store for trying vulnerabilites in action by yourself. If you are aware of OWASP top 10 vulnerabilities, understand those and know how to prevent them from happening, the software you're building is already quite secure. Besides OWASP there are also other lists or sources, for example, CWE (Common Weakness Enumeration) provides the top 25 most dangerous software weaknesses.

Of course, you don't have to have all the knowledge by yourself. The main point is to recognize that there might be some spots in your software where the information security issues should be thought more carefully. You can collect information by yourself, ask team mates or an information security specialist. The implementations concerning high-isk spots should at least be reviewed by someone with more experience on security issues. Developing your compentence in information security helps to notice the possible pitfalls.

Test automation can also be utilized here. There are several commercial and open-source vulnerability scanning tools available. These tools can be integrated to the CI/CD pipeline and with the help of those, you can actively monitor the information security level of your software. The vulnerability scanners point out the places where some hardening is needed. Also, the tools can be used to list outdated and vulnerable third-party libraries used in the project, so they can be updated to more secure versions if available.

# Tighten your foil hats

Being a information security oriented developer requires a suspicious mind. Never trust anyone is a good advice for a software developer. Always assume that the user might have something bad in mind. Don't trust any data coming directly from user.

Information security is about layers. Do not trust only validation on the user interface, validate data also in the server level. It is quite usual that a quite harmful looking vulnerability is enough for a hacker to provide a backdoor to the system. When in the system, it is easier to find more vulnerabilites and dig deeper. Onions have layers, ogres have layers and also information security should have layers to protect the valuable system and its contests.

![Onions have layers](/img/why-owasp/layers.jpg)

Tighten your foil hats, fellows, and read your OWASP!


Pointers to more detailed information:

- [OWASP](https://owasp.org/)
- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [OWASP Juice Shop for trying out](https://owasp.org/www-project-juice-shop/)
- [CWE Top 25 Most Dangerous Software Weaknesses](https://cwe.mitre.org/top25/archive/2020/2020_cwe_top25.html)