## Checklist

Omnicomposer is evaluated for accessibility based on the following criteria.

- Can I navigate via keyboard? 
- Is the contrast sufficient?
- Do images have the correct alt tags?
- Do the input fields have labels?

### What to Ask Yourself When Validating a Page
**Can I Navigate Via Keyboard?**

This is crucial for those who can't use a mouse. Many with motor or visual impairments rely on alternative means to navigate a page. You should be able to Tab to toolbar and able to apply any of RTE plugins.

- There should be an obvious focus when the item is highlighted:

![GitHub Logo](/images/tUDHU7vvFA.gif)

- Pressing Enter on an interactive item should give the same result as a mouse.

**Is the Contrast Sufficient?**

In order to meet the WCAG AA standard, the page needs to have a contrast ratio of :

- 4.5:1 for normal text 
- 3:1 for large text

This is an area where aXe (see below) is very helpful.

**Do Images Have the Correct alt Tags?**

Images `(<img>)` should always have an alt attribute. If not, the image path will be read out from the screenreader.

Decorative images should have a alt="" attribute. This will hide them from the screenreader.  Otherwise, the screen reader would say “Bold Bold.”

SVGs don’t have alt, so you should provide hidden text for the screen reader or use the aria-label attribute instead. Example PR: https://github.com/zendesk/zendesk_console/pull/25454

**Do the Input Fields Have Labels?**

Placeholder tags are not sufficient:

- They are not read out by screenreaders. 
- Having the field description disappear when clicked can make it difficult for users when revisiting an element or form.

aXe (see below) automates a lot of this.

## Useful Tools
**Lighthouse**

Google Chrome comes bundled with a tool that gives pages a quick once over for accessibility.

It can't help you with the more subjective parts of a11y validation, but it can check the page source for things like bad contrast and missing element attributes.

To access it, click on the Lighthouse tab of the Chrome Developer tools and then click Generate report:

![GitHub Logo](/images/chrome_lighthouse.png)

Here's how the ticket page fared:

![GitHub Logo](/images/lighthouse_results.png)

**aXe (Browser Plugin)**

aXe is a useful plugin to check for a pages accessibility. It's available for Chrome and Firefox.

To access it, install the plugin and click on the axe tab of the Chrome Developre tools:

Here's how a sample scan of ticket page looks like:

![GitHub Logo](/images/axe_results.png)

You can select `highlight` and it'll point to the element in the page

**Voiceover**

![GitHub Logo](/images/voiceover.jpeg)

MacOS comes with Voiceover (a screen reader) built in. This can be useful for validating forms, or for pages where the element focus has been hidden. It works best with Safari.

You can activate it with Command-F5. 
