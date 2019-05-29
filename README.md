# google-link-checker
A slackbot that notifies you if you share a Google Drive link that is non-editable or private.

Don't you hate it when you share a Google Drive link for a project, only to find out a few minutes later that nobody can edit it because it wasn't set to editable? With `google-link-checker`, just @cc the bot, and it will tell you if it is private. No Google API key needed.

![](https://i.imgur.com/pqoXqkS.png)

## How to run

- clone this repository
- in the root, run `npm install`
- update the `.env` file with your Slack API key
- run `npm start` in the root

## Roadmap

- automatically invoke the bot on every Google Drive link that is posted to the chat, and then send a message if it is locked or not editable
- periodically go through historical messages and add or remove the padlock icon to previous google links
- add different icons for view only, no access, and comment-only
- convert to a docker container for easy deployment

## Potential bugs

- this is somewhat brittle because it relies on scraping the HTML page, looking for the "View Only" toolbar. However, the no-access functionality is reliable as it detects if there is a redirect.
