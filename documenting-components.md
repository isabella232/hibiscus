# Documenting and Testing your Components

_You should absolutely be documenting and testing your components as you write them_ (or at least, before they are merged). Taking an extra half-day of legwork to write good tests and a solid README file will go a long way towards helping not only the team, but any future engineers who will want to work with your code.

## README files

Readmes can be intimidating. It's tempting to look at the blank document, throw some props on there (if even that) and call it a day. _Please do not do this, if you can help it. There are lots of resources you can take advantage of that will expedite your README writing process._

#### Design docs

Design actually presents us with extremely detailed design requirements. Their documents include the expected use cases of the component, the dependencies and Garden assets that make up said component, and even detailed screenshots of component functionality. **Capitalize on this!!** You essentially get all of those things for free if you copypaste them into your README file and tweak the descriptions to suit your final version of the component.

There is nothing wrong with opypasting this information because it will only be used internally and provides valuable information to your fellow engineers about the requirements the component was built around at virtually no extra cost to you in terms of development time. Not to mention it's a whole lot better than nothing :-)

If you are time-constrained and genuinely do not have time to document your code properly, please create a JIRA issue to follow up on your component with proper documentation.

#### Add engineering-specific information

Once the design aspects are copied, you can list props, codeowners, quirks of behavior, and other specifics that a programmer should know about your component. This should be much easier now that the README is no longer blank!

[Here is an example of a README written using these guidelines.](https://github.com/zendesk/zendesk_console/tree/master/lotus_react/src/Ticket/ConversationPane/components/ConversationHeader) You may even be able to copy aspects of this and use it as a template (team contact information, arturo section, etc.)