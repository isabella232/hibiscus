
## Development Environment Setup

1) Clone the [ZDI repo](https://github.com/zendesk/zdi) and install/configure ZDI according to the README.
2) Clone [zendesk_console](https://github.com/zendesk/zendesk_console) and read the [Lotus React documentation](https://github.com/zendesk/zendesk_console/blob/production/lotus_react/README.md) for tips about code style and running your environment locally.

## How To Create Your Own Support Website To Test

### Creating your account
1) Create an Zendesk Support account that starts with `z3n-`.
2) Sign up for a [Suite trial](https://www.zendesk.com/suite/) on the Zendesk website.
3) Email `financeops@zendesk.com` to request Enterprise access for your Zendesk Support url. It should have the format `https://z3n<your-url>.zendesk.com`

[z3n can still be used](https://zendesk.slack.com/archives/C1DPE0UVC/p1559154366019600?thread_ts=1559091165.015400&cid=C1DPE0UVC)

### How to Enable Help Center
1) Go to your Zendesk Support account
2) Navigate to your Guide account:

![Guide](images/starting-off/00-guide.png)

3) Click on the button that enables the help center. Refresh the page if it's taking too long.
5) In the yellow bar at the top, click `General Settings`. If the yellow bar is not there, you can click on `Guide Admin` in the top right corner in the nav bar.
6) If you clicked `Guide Admin`, click on the setting cog on the left nav bar.
7) Click on the big blue `Activate` button to enable help center for visitors to your Support instance.
8) Scroll down and find the checkbox labelled `Chat: Enables users to initiate a chat session with an agent from within Help Center.`
9) Check that box.
10) Click the Update button at the top of the page to save your settings.

### How to Start Testing Chat
0) You need to enable the help center first! Look above
1) Open your Zendesk Support url on one tab. We will call this the `agent view`
2) In an incognito tab, open your help center url (https://<your-url>.zendesk.com/hc/en-us). We will call this the `customer view`
3) In the `agent view`, click on the chat bubble found here and set yourself to `online`:

![find-chat-bubble](images/starting-off/01-start-chat.png)

4) In the `customer view`, look at the lower left hand corner. There should be a chat message box that pops up. Start typing away!
5) In the `agent view`, to the left of the chat bubble we clicked on earlier, click on `Serve Chat`.
6) Tada! Start messaging your agent self with the customer self!