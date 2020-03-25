# Writing Good Code (on a Deadline)

Since a lot of the code we will be writing here on Hibiscus will become the basis for future work at the company, we have to give a lot of thought to the standards we want to uphold (and the example we want to set!) for future developers who will be working within the codebase.

## Naming and Commenting

This is the first step to writing good code, it's important to keep in mind that comments are no replacement for strong naming and code organization. As a general rule of thumb, try to push your variable, function, and class names to be as descriptive as possible on their own, then use commenting to clarify areas where the code is ambiguous in spite of naming, for example where a decision appears initially questionable but is justified by requirements elsewhere (perhaps because of legacy or other factors).

Done correctly, this is a fairly low-cost way of greatly enhancing the readability of your code without even having to resort to full documentation.

## Making the Most of Code Review

When asking for code review, the teams who own the code you have worked on will be added automatically as reviewers (as specified in Lotus's CODEOWNERS file). In spite of this being an automatic process, you should always think critically about who else may need to take a look at your code (people who have contributed a substantial amount of code to that file in the past, for example).

This way, you may gain insights into why certain decisions were made as well as other use cases you might not have considered, causing you to tweak your code accordingly (or alternatively, you will find that your changes work just fine with the intentions of the original author. Either way, it's best to check!)

## When You Have to Write Suboptimal Code

Ideally this never happens to you, but let's be realistic, projects have deadlines, we have to work to meet them, and sometimes it's 2am the night before release and a regression happens and you need to fix it asap so that customers can see the product they were promised in the morning (Never actually do this by the way :-) )

Anyway, you get the point. Whatever the circumstances (legacy constraints, a tight deadline, poor planning, simple urgency) you have been forced to write code that is sub-optimal. What to do?

### 1. Leave a comment

The first thing you should do is comment the code snippet in question, explaining the reasons for the ugly code and explicitly stating an intention to follow-up on refactoring it.

### 2. Create a JIRA

Next, create a JIRA issue to follow up on this bad code snippet. Keep in mind that product and other non-technical teams will need to prioritize this issue, so make sure to explain as simply as you can what the impact is of having this bad code in Lotus's codebase. Link the JIRA from your comment in the code.

### 3. Respectfully discuss feedback with those who review your code

Even given all of this, an engineer may review your code and decide it is simply too bad or risky to be pushed out to production. Generally, they will have a suggestion on how to improve it. Reviews should be respectfully considered and discussed, but they should not be blindly accepted, even if you are embarrassed with the bad code you wrote, and even if the need to merge is urgent.

Code quality always comes first. Even seasoned developers can fall into the trap of falling back on conventions (which aren't always bad but should not be blindly accepted). You should always be prepared to think critically and see if there is any room for new ideas, especially in a project such as this one.

So all in all, we should respect the reviews, consider them, and have discussion with the reviewer if we disagree. Feel free to bring other people into the discussion to facilitate if needed.

## But what if there is a deadline?

Generally pushing risky code before a deadline is not a good idea. Especially if your code is suboptimal, it can be hard to predict whether merging won't cause even more issues you have to fix, causing you to miss the deadline altogether anyway.

**If anything, quality, stable code becomes even more important the closer to release you are.**

If the issue is a deadline and you do not believe that you have a reasonable amount of time to write the code in a way that is stable and performant, you should communicate this to your team as well as management and/or product, explain why it is unrealistic and work with them to either mitigate the issues or change the deadline, rather than shipping bad code. Ideally you should communicate these issues as early as possible, to prevent issues like this happening as you close in on release.
