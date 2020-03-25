# Using JIRA to communicate with Product

While it is true that JIRA is a valuable tool for sprint management and issue tracking, you are doing yourself and your team a disservice if you are only using it as a tool for reporting bugs. In reality, JIRA is the generally the primary tool that product, your team lead, design, and QA uses to prioritize, understand, and aggregate the critical issues your team needs to work on. In other words, JIRA is the single best tool you have as an engineer to communicate your thoughts to other departments about what should be important to your team's future roadmap.

## Advocating for Non-Obvious Technical Needs

It's common for engineers to feel that other departments (in particular Product) have a tendency to prioritize feature work at the cost of maintenance and infrastructure work that has less visible impact or less-obvious short-term benefit. While to some extent this is true due to the pressures exerted on product managers (for example, Product probably won't ever tell you to stop all feature work for a year and focus on code refactoring or React migration) for the most part there is actually a lot more room to make a case for technical needs than most engineers assume. Product hates it just as much as you do when technical debt comes to a head and customers begin complaining about performance chugging and slow response time to bug reports.

As a developer, you will have a better understanding of the minute needs of the codebase than pretty much any other role on your team. Communicating that expertise through JIRA is among the best ways you can enhance your team's overall effectiveness, and it is something that only you can do.

Here are a set of best practices that Hibiscus's engineers have found useful in accomplishing this goal:

### Step 1: Report it!

Whether you need to refactor old or ineffective code, or you implement a short-term solution that must be revisited later to ensure it doesn't blow up, or you see an opportunity to improve your product's architecture and make it easier to manage, report it! Create an issue in JIRA! It sounds obvious, but often engineers forget to take this simple step when they see an opportunity like this. They either don't want the hassle of creating the issue, or they don't think anyone will care. However, this step is _critical_ because product and your team lead will have no awareness about needs that have not been reported.

This has the added benefit of leaving a record of your intent to refactor/improve said code and makes it much less likely for the issue to fall through the cracks or be forgotten as you dive into other work.

Even if the issue seems trivial to you (e.g. you left a comment in the code to revisit this line later or something), you should still report it in JIRA. Your manager or product will handle prioritizing the issue based on the perceived need, and with more visibility of the issue there will be more accountability on both sides for eventually getting it done.

### Step 2: Communicate Impact

One common mistake a developer might make would be to focus too heavily on how this technical need benefits you personally as a developer, e.g:

- "xyz is really annoying"
- "this would make things much cleaner"
- "this is really gross code and we can't just leave it like this"
- and so on.

That isn't to say that you shouldn't include these benefits in your proposal, but they (on their own) do not make a compelling case to Product about why this work should be prioritized over more pressing feature work (that has deadlines), especially if the refactor seems expensive.

Product primarily cares about four things:
1. **Customer impact** (this includes feature work as well as stability and performance)
2. **Velocity impact** (future development time, response time to customer feedback, etc)
3. **Cost of implementation** (in terms of developer time)
4. **Short and long-term consequences** of choosing not to implement.

As much as you can, frame your proposal in terms of these concerns, e.g:

- "xyz causes development to take twice as long _and_ is really annoying"
- "cleaner code will make us quicker in adding features in the future, and increase stability in such-and-such ways"
- "this solution will not scale to many customers and will break if we leave it alone too long"
- and so forth.

Your PM is basically going to weigh these benefits (and potential future impacts) against the amount of time you tell them this is going to take. It's a very straightforward cost assessment. Because they do not have time to go over the code as in-depth as you do, it's on you to communicate the pros and cons clearly so that they can make an informed decision based on an accurate picture of the current state of the codebase (or as accurate as you are capable of communicating).

### Step 3: Keep it Brief (as you can)

One thing to keep in mind is that PMs and Team Leads are often juggling dozens of issues at once. When writing your JIRA story, try to get to the point as quickly as possible. Ideally, write it so that it is easy to skim and get a clear idea of the main points. Bullet points are great for this!

A good JIRA issue would make sure to hit on these main points in quick and clear succession:
- problem statement
- proposed solution
- impact
- time cost
- consequences of not implementing
- clear next steps for an engineer taking on the issue

The better you are able to summarize this information in a way that is easily digestible, the more likely it is that your PM will get around to reading and prioritizing your issue in the first place!

#### Step 3.5: If you can't keep it brief, break it up!

If you find you are having trouble keeping things brief without feeling like you are leaving out important information, that may be a sign that you should break the issue down into subtasks, and possibly even consider creating an epic. Doing so will make it much easier for your manager and PM to track progress of this issue over time, in addition to making it easier for everyone on your team to understand how the work needs to be broken down.

### Step 4: Shop it around to other engineers!

If your proposed refactor is something that would benefit other teams besides your own, shop it around to them! They can provide valuable feedback about how your proposal could be improved to better address needs across the organization, and may even help make your case to Product when the time comes to prioritize said work.

Product will be much more convinced of the importance of a technical need if many engineers across the organization are pushing for it. So get feedback!

## Conclusion: JIRA is a communication tool!

With all that being said, it should be clear now that you're really only going to get the most out of JIRA if you think of it as a _communication_ tool first and foremost. Not everyone on your team is going to be able to understand the intricacies of your product's codebase (that's the entire reason you have a job) so it's on you as an engineer to communicate technical concepts and needs in a way that is easily digestible to those who don't spend the majority of their days immersed in code. One could argue that is just as much a part of the job as writing maintainable, clean code.