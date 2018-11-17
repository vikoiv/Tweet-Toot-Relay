# Tweet-Toot-Relay
Tweet-Toot-Relay is a small Python3 project to convert a tweet to a toot. It's basically a Twitter relay for Mastodon.

The way it works is this: add Tweet-Toot-Relay as a cron job, and it will repost new tweets to any Mastodon account you configure. Just clone this repo, configure the script, add it to a cron job, and it will get cracking.

## How do I install this?
Getting Tweet-Toot-Relay working is pretty easy. Before you can install it, you're going to need to do the following:

- Pick a Mastodon instance of your choice. You'll need this instance's URL.
- Create an app on this Mastodon instance and generate an access token. Give write:status priviledge for the scopes.
- Get the Twitter URL of the account you want to watch.

Once you have the above, just follow these steps:

1. Clone this repository.
2. Install the Python3 libraries "requests" and "beautifulsoup4" mentioned in the "requirements.txt" file.
3. In "config.json", update the following:

- "gen.APP_NAME": The mastodon application.
- "tweets.source_account_url": The source Twitter account.
- "toots.host_instance": The HTTPS URL of your instance.
- "toots.app_secure_token": The Mastodon app access token.

For example:
- "gen.APP_NAME": "YourMastodonApp",
- "tweets.source_account_url" = https://twitter.com/YourAccount
- "toots.host_instance" = https://botsin.space
- "toots.app_secure_token" = XXXXX-XXXXX-XXXXX-XXXXX-XXXXX'


## How do I run it?
Once it's all setup, just run the main file like this:

"python3 run.py"

