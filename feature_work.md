### Code workflow - branch, tests, PR, QA, feedback

* We do work in git branches - check out master/staging/production, pull latest, then create a new branch.
* In your first commit, make sure a JIRA issue key is in the commit title - something like `"[AI-4267] Add codespans to scribe editor"` - that will automatically link the JIRA issue to the PR in the JIRA interface.
* Mechanics of testing: https://github.com/zendesk/zendesk_console/wiki/Testing
* Be pragmatic when writing tests. A few ways to gauge test value:
  * Is the code you're writing likely to churn (new features, buggy domain, external dependencies)?
  * Consider the failure mode - if the code written breaks, what would happen?
  * Is it easy to write a valuable test?
  * If you can't decide, *write a test* - you should have a good reason for *not* doing so
  * Don't test the framework or third party code
* If you're adding new text that's visible in the UI, it needs to be translated - search this file for 'i18n'. **Merge your strings first** in a separate PR to get them going, before you get started on feature work.  
* When writing tests for a feature behind an arturo flag, make sure to stub the feature in the test _environment_ so you can be assured that existing tests do not fail with your new feature turned on.
  * For Classic, you can use `arturo: !Rails.env.test?` on features you want to test as seen in [`capabilities.rb`](https://github.com/zendesk/zendesk/blob/master/app/models/account/capabilities.rb).
* When you open a PR that corresponds to a JIRA issue, make sure you link the two together:
  * Paste a link to the JIRA issue in your GitHub PR description.
  * Add an "Issue Link" in JIRA via the "Add Link" button to reference the GitHub PR. With the GitHub PR in your clipboard and the JIRA issue selected, `. l <enter> <tab> <tab> <space> <paste> <tab> <paste> <enter>` quickly links them together.
* QA: Usually our embedded QA engineer helps us test out features, but we can do the same:
  * New features: test on Chrome (Mac & Windows), FF (Mac & Windows), Safari, and IE.
  * Existing features: test on Chome (Mac & Windows). If the bug describes a problem with a specific browser, test in that browser as well.

#### Package management and versioning
We use NPM to manage our dependencies. We don't currently publish our packages to the NPM registry, instead reference them by their GitHub url, using tags for version control.

```json
"dependencies": {
  "left-pad": "git+ssh://git@github.com/stevemao/left-pad.git#v1.1.0"
}
```

External dependencies are installed from the NPM registry and we use the following semver syntax:<br>
`x.x.x`, `1.x.x`, `1.2.x`, `1.2.3` where the `x` is the wildcard number.

```json
"dependencies": {
  "left-pad": "1.x.x"
}
```

### JIRA

* As soon as you start working on something, drag it into the 'in progress' column - that will automatically assign it to you.
* Dev, Product, and QA all rely on JIRA to stay in sync on what code is where - hygiene here is very important.
* If the code you're writing happens in a project that isn't on a deploy path (zendesk_editor, for example), do not mark it as done until it's been pulled into a project that is (zendesk_console or zendesk).

#### I18n (internationalization)

* If the feature you're working on has strings visible to users in the UI, it needs to be internationalized.
* Read this: https://zendesk.atlassian.net/wiki/display/i18n/String+Extraction+101
* The schedule for collecting strings to be translated and having them available in production is published here: https://zendesk.atlassian.net/wiki/display/i18n/Weekly+Translation+Schedule
* Translations in your Development Environment: https://zendesk.atlassian.net/wiki/x/txTPC
* Adding a new string to Lotus: https://zendesk.atlassian.net/wiki/x/IAQYBQ
* Check Translation Status: https://zendesk.atlassian.net/wiki/x/Z4K1C

#### Open source

our open source policy is here: https://zendesk.atlassian.net/wiki/pages/viewpage.action?spaceKey=ENG&title=Open+Source

### Feature lifecycle
* customer research
* problem presentation & UX kickoff
* iteration
* beta
* GA

### Locally testing features

To enable features for classic, run `script/feature enable feature_name` from the zendesk shell

To enable a feature that must be visible to lotus, such as editor-related features, you must also add this feature in your local monitor (monitor.zd-dev.com) with the name format "lotus_feature_feature_name" and make sure it a) is set to "Closed beta" or "GA," and b) includes the name of your dev account (e.g. "support")
