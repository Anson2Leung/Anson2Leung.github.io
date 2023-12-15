---
layout: essay
type: essay
title: "Software Engineering and ICS 314"
# All dates must be YYYY-MM-DD format!
date: 2023-12-11
published: true
labels:
  - Software Engineering
  - Learning
---

![](../img/software-engineering-and-ics314/reflect-on-software-development.jpeg)

## Software Engineering I
Within Software Engineering I (ICS 314), we learned many concepts related to software development, including but not limited to:

* Open Source Software Development
* Configuration Management
* Functional Programming
* Development Environments
* Coding Standards
* User Interface Frameworks
* Agile Project Management
* Design Patterns
* Ethics in Software Engineering

I have previously talked about Coding Standards ([Thoughts on Coding Standards](https://anson2leung.github.io/essays/Thoughts-on-Coding-Standards.html)) and Design Patterns ([Baking Design Patterns](https://anson2leung.github.io/essays/baking-design-patterns.html)) in previous essays. I will elaborate on these two topics alongside Ethics in Software Engineering in regard to what I have learned from taking ICS 314.

### Coding Standards

Within my “Thoughts on Coding Standards” essay, I had relatively mixed feelings about code styling. I believed that it was beneficial to not only those learning, but those who are also more experienced. By following a coding standard those who are either contributing to your code or building off of it can properly understand the purpose of each part. In an educational setting, other people will be able to properly critique your code for things other than readability. For professionals who are usually working in teams, being able to understand each other's code is necessary to work together. If you are not knowledgeable in computer science, it will be like not explaining where the “Arts & Crafts” supplies are supposed to go. It will become a complete mess if you had to search around to find a single thing that is necessary to continue working.

### Project Management

Going hand in hand with software development is project management, the main approach we learned was Agile Project Management. I briefly learned about it from [Kevin Costa From Business Solution Technologies](https://anson2leung.github.io/essays/Industry-Talk-Kevin-Costa.html). Where it was the repetitive process of “gather requirements -> design -> prototype -> refine requirements -> refine design-> prototype 2 -> repeat.” The main idea is that the software will continue to be updated and refined as time passes. The specific approach we learned within the Agile Project Management umbrella was Issue Driven Project Management (IDPM). IDPM chunks up a project into notable “Milestones”, which is further broken down into smaller “Issues.” These issues should not take more than a few days of time each and that they can proceed independently of each other. Although this approach can assist in dividing up tasks among team members, I take issue with how it names the GitHub branches “Issue-XX” (XX being the issue number). The reason is that it is uninformative of what the branch was for, when asking another team member to check over what you have written, for a certain feature it is a lot easier to say “Can you check the front page?” instead of  “Can you check out Issue-22?” I do appreciate the way it divides large tasks into smaller ones, and I can definitely see myself using something similar, just without the issue naming process.

### Ethics in Software Engineering

Ethics in Software Engineering is a topic that must be factored into software development. In class, we read and discussed Bill Sourour’s article “[The code I’m still ashamed of](https://www.freecodecamp.org/news/the-code-im-still-ashamed-of-e4c021dff55e/),” which delves into an early part of his coding career in which he developed a website marketing a drug with adverse (non mentioned) side effects which were severe depression and suicidal thoughts. A young girl on the drug would end up killing herself, in which Sourour feels partially responsible for. While reading his article we also checked out the [Association for Computing Machinery’s Code of Ethics](https://www.acm.org/code-of-ethics) as reference. I find that the Code of Ethics is similar to the Hippocratic Oath that medical professionals take where it is sworn that they shall do no harm. If I was in his position I would not have made the correct decision, probably opting for the same straightforward outcome he made. I feel like that there should have been more room for objection to the ethics of the desired product, but from reading Sourour's story there seems to have not been many options aside from asking to turn down the request. I also believe that Sourour was not given the full details of the drug, so he would not have known the side effects of the drug, but within the Code of Ethics there is a clause for honesty and the act of misleading the quiz-taker to their drug is highly manipulative and is probably illegal now. Although ensuring people’s safety is not completely possible, we as software developers must make a full-fledged effort to reduce that probability of harm being caused to others' livelihoods and well-being.