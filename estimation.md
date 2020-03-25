# Hibiscus estimation guidelines

We use the Fibonacci scale to represent general project sizing when grooming/estimating tasks in the backlog. This helps keep us from quibbling over too granular a scale.


The following table can be used a reference for estimation

 Points     | Example
------------|--------------
 1 point    | - adding translations or simple style fixes
 2 points   | - adding a simple UI component that's fairly isolated<br> - bugs with easy/known fixes
 3 points   | - adding UI that may involve a couple moving parts
 5 points   | - writing new graphQL schemas/types to hook up new UI components <br>- bugs that are fundamentally hard to fix, or may require multiple PRs to fix correctly
 8 points   | Consider breaking up into smaller stories

### Below are the very rough expectations that we share for each number on the scale

#### 1:
    up to 30 minutes

    This is a trivial change that requires no investigation nor coordination,
    like flipping a switch or a setting.


#### 2:
    ~1 hour

    Similar to a 1, but may require a code review, deploy, etc.


#### 3:
    1-2 days

    Requires minor amount of investigation, if any,
    and is a small change or addition.


#### 5:
    3-4 days

    Moderate amount of work. May be adding something new, including a test.
    Small to no uncertainty about what needs to be done, may require trivial amount of investigation.


#### 8:
    ~1 week

    Substantial change or addition, where there may be some unknowns or needed investigation.
    This is often used when the task requires the gathering of context.


#### 13:
    Equal to one dev's time for a full sprint

    These are uncommon and usually indicate that a task should be broken down into smaller pieces.
    However, sometimes a large investigation or rearchitecting can be captured by a 13.
    Typically a lot of unknowns.

We also frequently use the numbers above to timebox investigation stories. So if the entire outcome of the task is information or a plan, then we may label it a 5 to indicate that you should spend no more than a day on coming to a conclusion (or any of the other approximate durations).

