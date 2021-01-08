## Jump hosts Access

Create a ticket on the [Engineering User Access - Issues - JIRA board](https://zendesk.atlassian.net/jira/software/c/projects/ENGACS/issues) and get approval from Manager. To expedite access, ping in [#znoc](https://zendesk.slack.com/archives/C17D0QDMY) slack channel

## DB Access

In case you don't have Read-Only access to Production Database, follow the steps here and request for access - [DB Access](https://zendesk.atlassian.net/wiki/spaces/rb/pages/250609711/Process+For+Production+Database+Access)

## SSH to the dbadmin server

Once you've access, you can SSH to the pod where we want the results e.g. `ssh pod25` and access any dbadmin host `ssh dbadmin1` and invoke rails console using `console_classic` to test the Ruby script 

Here are example Ruby scripts:

- [Returns tickets where requester has an identity in affected accounts](https://gist.github.com/dbuchi/f45e279bdc09e0d05e5d8c8bfdf951da)
- [Fetches the first public comment after chat ended](https://gist.github.com/dbuchi/d04fc7d4ec1f0b9c775551e90ebbabc0)

## Process

After invoking rails console, copy the code in the script and paste it in there. Results will be printed on the screen and also stored in `csv_string` variable

When the script finishes, in order to save the results to an external file:

- clear buffer
- do `puts csv_string` in the terminal 
- save the contents using session -> log -> save in the Terminal.
- Paste the results into a spreadsheet or new file in Sublime Text that can be exported to a spreadsheet
