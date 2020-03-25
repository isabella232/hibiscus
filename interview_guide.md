# interview guide

Hiring is hard. We've spent some time coming up with a consistent process - if everyone looks for the same indicators and uses the same process, we have a better shot at reasoning intelligently about one candidate or another.

This is always a WIP - our interviewing happens in bursts and as circumstances and our understanding evolve, so should our methods.

## prep reading

This is a selection of relevant articles that help explain the basis of our interview process.

* https://medium.com/swlh/how-to-hire-34f4ded5f176
* https://medium.com/airbnb-engineering/beginning-with-ourselves-48c5ed46a703
* http://engineering.foursquare.com/2016/04/04/improving-our-engineering-interview-process
* https://slack.engineering/a-walkthrough-guide-to-finding-an-engineering-job-at-slack-dc07dd7b0144
* http://www.fastcompany.com/3056351/the-future-of-work/why-diversity-in-hiring-is-only-one-part-of-the-puzzle
* http://sockpuppet.org/blog/2015/03/06/the-hiring-post/#warmup

I've written up some recommendations for healthier hiring practices here:

* https://docs.google.com/document/d/1EtbeNIvNBIfYVT3u5VEJg02KqO6s3zp2i9hHYNADflw/edit

## indicators

We should look for candidates whose breadth of skill overlaps our team's primary competencies. The work we do tends more on the frontend (rich UI with js), though we need good coverage of the full stack.

Loosely, here are things we look for in candidates:

* web development fundamentals (HTML, CSS, JavaScript, client/server app logic)
* real-world experience with software development (working with PMs, QA, customers etc, knows about sprints and such)
* balancing technical and product-driven work
* plays well with others, not a d-bag

More experienced candidates should have expectations adjusted accordingly. In general, look for strengths, not a lack of weaknesses - strengths are what drive us forward.

## process

The hiring process should generally follow the same pattern; we realize that the interview panel is not always consistent (people may be subbed in, etc), so it's important to stick to the same format.

Candidates will have a phone screen and a work-sample exercise to complete, then an onsite panel of 5 45-minute slots if we feel comfortable proceeding with hiring.

### phone screen

The goal of the phone screen is to short-circuit red flags. We should be fairly permissive here - it's hard to get a high-confidence reading of a candidate's technical depth, but we should be getting measurable and comparable data about their ability to ship quality code as part of a team.

Here's a basic script for a 45min screen -

00 ~ 15m

* introduce yourself - your role, what you work on, the role being hired for
* briefly explain the structure of the phone screen (background, code exercise, questions)
* talk about projects, background - ask about specific responsibilities, challenges, tradeoffs
* there are some other questions you can ask that tell you how the candidate gets stuff done:
 * have you worked closely with Product & UX?
 * have you worked on externally facing software?
 * what is something you've had to teach yourself?
 * what was a technical decision you've had to make? how did you reason about it? what were the tradeoffs?

15 ~ 35m

* Complete the 'run length encoding' exercise in coderpad.io, there should be a link to one in the interview invite email. If not, you can create a guest coderpad. You can describe the problem as below, with some extensions if you have extra time:
  * RLE is a made-up encoding algorithm that compresses runs of characters together - the character being encoded followed by the number of times it occurs in a row. We should always be able to reproduce the input from the output string. Try 'aaabb' -> 'a3b2' and 'aaba' -> 'a2b1a1'. Ask the candidate to talk through problem solving, and to use whatever language they are most comfortable with.

    > A sample solution is here: http://jsbin.com/yoyemoloza/edit?js,console

  * Ask the candidate to modify the function to cache previous calculations.
  * A good JavaScript one: ask them to take that caching and make it a generic `memoize` function that returns a memoized version of an input function.
  * Try '111111111122222222222', or ten 1s and eleven 2s -> '110211' -> how do you handle when runs of characters are too long and the output becomes ambiguous? (add a delimiter)


35 ~ 45m

* Leave some room at the end for the candidate to ask you questions. What they ask here is relevant too.

### work-sample exercise

The goal of the work-sample exercise is to have candidates show that they can build a tiny app that expresses some knowledge of DOM, CSS, HTML, and JavaScript. The recruiter will send a link to the instructions to the candidate at the same time the developer phone screen is scheduled.

We give 5 days to complete the exercise, which should take about an hour or two. The instructions are below:

https://gist.github.com/kencheeto/53fbc3b1906e77012824

> I'd like us to move away from drag-n-drop as one of the features, since it will bias people towards using a blackbox solution for drag & drop DOM events, which are awful to work with manually.

### onsite (wip)

The onsite panel looks generally like this:

1. Pair interview

  * intro both interviewers
  * questions to probe experience
    * ask for details about ownership, accountability, leadership
    * ask about technical decisionmaking, tradeoffs
  * questions to probe skill
    * what are some ways a website might be slow?
    * what is a negative user experience on the web that you've had? why was it negative?
  * questions for us

1. Solo, pairing on something at Hibiscus desks

  * This can be pairing on anything. If the candidate has a project lying around, you could try talking about and adding a feature. It could also be pairing on something you're currently working on, if there's something immediately accessible.

1. Solo interview - JavaScript deep dive

  * if it wasn't done during the phone screen, can work on run length encoding here
  * write a memoize function that returns a memoized version of the input function
  > https://github.com/zendesk/zendesk/wiki/Info%3A-Javascript-Interview-Questions#memoizing-a-function
  > interesting things: what's the cache key for function calls, colliding property names with object prototype
  * https://github.com/zendesk/zendesk/wiki/Info%3A-Javascript-Interview-Questions#lexical-scoping

1. Solo, pairing on something at Hibiscus desks

1. Pair (PM & UX) - assess the candidate's product thinking, communication skills

#### some other ideas we'd like to try, but haven't

* web security (xss, cors, csrf)
* iterate on the take-home exercise onsite
* present a mockup - in a room with a pm and designer, what do you ask, what's your next step
