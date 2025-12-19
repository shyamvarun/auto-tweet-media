This project is a small automation bot that posts images with captions about Nidhhi Agerwal to three different X (Twitter) accounts using GitHub Actions and Python.

The GitHub Actions workflow runs on a schedule (three times per day) and can also be triggered manually from the Actions tab.

How it works
image_poster.py:

Loads 3 sets of API credentials (keys, secrets, access tokens, bearer tokens) from environment variables.

Maintains a list of captions and image filenames.

Uses used_captions.json to ensure each account gets unique captions over time.

For each account:

Picks an unused caption and random image.

Uploads the image via Tweepy (v1.1 API).

Creates a tweet with the selected caption and image.

.github/workflows/countdown-bot.yml:

Installs Python 3.11 and dependencies from requirements.txt.

Exposes all required Twitter/X secrets to the script via env.

Runs python image_poster.py on schedule and on workflow_dispatch.

Required secrets (per repo → Settings → Secrets and variables → Actions)
For each of the three accounts:

TWITTER_API_KEY_1, TWITTER_API_SECRET_KEY_1

TWITTER_ACCESS_TOKEN_1, TWITTER_ACCESS_TOKEN_SECRET_1

TWITTER_BEARER_TOKEN_1

…and similarly for account 2 and 3 (*_2, *_3). These values come from the X Developer Portal (Project → App → Keys and tokens, and User authentication settings).
​
