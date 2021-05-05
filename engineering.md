Hibiscus Engineering
==================

Welcome to Hibiscus Engineering! Take a look at the documentation below to get started on setting up your development environment.

[Zengineering Handbook](https://zendesk.atlassian.net/wiki/spaces/ENG/pages/58720266/Zengineering+Handbook)
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The Zengineering Handbook contains a plethora of information. Including, but not limited to: communication, Onboarding materials, Job Architecture, general development process information, etc.

-   Be sure to check out the [New to the Team](https://zendesk.atlassian.net/wiki/spaces/ENG/pages/58720268/New+to+the+Team) section for some helpful tips like [this one](https://zendesk.atlassian.net/wiki/spaces/ENG/pages/58720268/New+to+the+Team#NewtotheTeam?-GitHub)

Initial Setup
----------------------------------------------------------------------------------------

-   Set up [Zendesk Docker Images](https://github.com/zendesk/zdi) (ZDI) & [Classic](https://github.com/zendesk/zendesk)
    -   Follow these [installation instructions](https://github.com/zendesk/zdi#installation)
    -   If you get stuck, check the #zdi Slack channel, or ask your fellow team members.
    -   After setup, you should be able to view the Zendesk Support app at [https://support.zd-dev.com](https://support.zd-dev.com/) by logging in with [these](https://github.com/zendesk/zdi#note-1) credentials
-   Set up [Lotus](https://github.com/zendesk/zendesk_console/blob/master/lotus_react/README.md#Getting-Started) (aka `zendesk_console`)
    -   Check out the #lotus Slack channel if you run into issues, or ask your fellow team members.
    -   After setup, you should be able to go to https://[your-domain].zendesk.com/agent/dashboard?sha=develop and see your local changes
[More here](https://github.com/zendesk/hibiscus/blob/master/starting-off.md)

Deploying Code
------------------------------------------------------------------------------------------

-   [Lotus](https://github.com/zendesk/zendesk_console/blob/master/Deploy.md#deployment-process) and [Classic](https://github.com/zendesk/zendesk/blob/master/DEPLOY.md#patches) each have their own `deploy.md` file to walk you through the deployment process. Read each thoroughly
-   We always deploy with a buddy
-   Make sure you know how to roll back your changes if something goes wrong.
-   Join #lotus-deploys and #classic-deploys for more information

[Arturos](https://zendesk.atlassian.net/wiki/spaces/ENG/pages/271490944/Feature+Flags+Arturo) (aka Feature Flags)
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

We generally use Arturos for any new features that we're releasing to customers, or any changes that may be risky. Aside from the information already in the [Confluence page](https://zendesk.atlassian.net/wiki/spaces/ENG/pages/271490944/Feature+Flags+Arturo), here are some general guidelines:

### Creation and Development

-   Remember to create your arturo in both [staging](https://monitor.zendesk-staging.com/features) and [production](https://monitor.zende.sk/features)
-   When creating arturos, add "<hibiscus@zendesk.com>" to the "Owner email(s)" section, in addition to your own email
-   Arturos start out in the "Closed Beta" phase. Add your test account's subdomain to the arturo. If you have a staging account, you can do the same in the Staging version of monitor
-   Instructions for using arturos in [Lotus](https://github.com/zendesk/zendesk_console/blob/master/lotus_react/docs/feature-flags.md)
-   When working in Classic, you can enable your arturos locally with `zdi classic arturo enable name_of_your_arturo`
-   Arturos in Zendesk are sometimes confused with [capabilities](https://github.com/zendesk/zendesk/blob/c3f778317ef51a5cc03e889b9c1198b74c80761e/app/models/account/capabilities.rb) which can be a combination of arturo + subscription + other requirements
    -   This [presentation](https://docs.google.com/presentation/d/1-1g05zP74Y6C_JX5z6CiaFyeEny3l808p2nOHvJTe9c/edit#slide=id.g9c4ab56ca1_2_90) might be helpful

### Rollout

-   When you're ready to roll out your arturo, consult with our PM for a rollout plan and let the team know so that we can watch out for any issues that may arise. Rollouts can last anywhere between a day (bumping up the % hour by hour for small, low-risk changes) to a week or even longer (for new, heavily used, or high-risk changes).
-   Remember to switch your arturo to General Availability (GA) in staging before rolling it out in production
-   We also use arturos for Early Access Programs (EAPs)

On-Call
----------------------------------------------------------------------------

At some point, you will be added to either Support UI On-call or Classic On-call. Be sure to get set up in PagerDuty, and read through the incident response runbooks. If you get paged, join the Slack channel that gets created for the incident.

-   [Support UI On-call](https://zendesk.atlassian.net/wiki/spaces/ENG/pages/703627632/Support+UI+Lotus+On+Call+Group+The+LOG)
    -   [Incident Response](https://github.com/zendesk/zendesk_console/tree/master/lotus_react/docs/incident-response) - Generally, steps are as follows:
        1.  Checkout #lotus-deploys to see what changes have been recently deployed
        2.  Test out an earlier version using a previously deployed version such as `https://support.zendesk.com/agent?sha=v1234`
        3.  Once you've isolated the cause to a specific version, follow the instructions in the Recovery section [here](https://github.com/zendesk/zendesk_console/blob/master/Deploy.md#recovery) to roll back to a previous version
        4.  Notify the owner of the PR that caused the incident, revert, merge, and deploy
        5.  If you can't isolate the cause to a specific version, check for any recent arturo changes
        6.  Bother the #lotus Slack channel
-   If you can't do your on-call shift, ask someone to swap with you in the relevant on-call Slack channel. You can swap with them in the Pager Duty app
-   [Severity Levels](https://zendesk.atlassian.net/wiki/spaces/IM/pages/976553831/Severity+Levels)

Testing
----------------------------------------------------------------------------

Software Engineers on the team are responsible for ensuring adequate test coverage for any new or changing functionality. In addition, we spend a portion of our time writing browser tests found in the `zendesk_browser_tests` repo

-   [Lotus Testing Documentation](https://github.com/zendesk/zendesk_console#testing)
-   [Zendesk Browser Tests (ZBT) Documentation](https://github.com/zendesk/zendesk_browser_tests)

Useful Slack Channels
--------------------------------------------------------------------------------------------------------

-   #hibiscus-alerts - Hibiscus automation alerts
-   #engineering
-   #engineering-sf
-   #classic-deploys
-   #classic-dev
-   #lotus-deploys
-   #lotus
-   #zdi

Additional Resources
------------------------------------------------------------------------------------------------------

-   [Engineering First Principles](https://zendeskdev.zendesk.com/hc/en-us/community/posts/115003903329-Zendesk-Engineering-First-Principles)
-   [Open Source at Zendesk](https://zendesk.atlassian.net/wiki/spaces/ENG/pages/32244556/Open+Source)
-   [i18n String Sweep Overview](https://zendesk.atlassian.net/wiki/spaces/globalization/pages/625345680/String+Sweep+Overview)
-   [Zendesk Garden](https://garden.zendesk.com/)
