# hubot-analytics

[![Build Status](https://circleci.com/gh/PlanBCom/hubot-analytics/tree/master.svg?style=shield)](https://circleci.com/gh/PlanBCom/hubot-analytics)
[![Codacy Badge](https://api.codacy.com/project/badge/grade/f59fb080459140a497bd17f357147e2d)](https://www.codacy.com/app/godoy-ccp/hubot-analytics)

A hubot script to get google analytics reports

See [`src/analytics.js`](src/analytics.js) for full documentation.

## Installation

In hubot project repo, run:

`npm install hubot-analytics --save`

Then add **hubot-analytics** to your `external-scripts.json`:

```json
[
  "hubot-analytics"
]
```

### Configuration

1. Create a [`https://console.developers.google.com/project`](google project)
2. Enable "Analytics API" in your project (https://console.developers.google.com/apis/)
3. Create a service account https://console.developers.google.com/permissions/serviceaccounts and download JSON with private key
4. Configure the followings environments variables in your hubot server:
```
GOOGLE_API_PRIVATE_KEY - look for 'private_key' in JSON
GOOGLE_API_CLIENT_EMAIL - look for 'client_email' in JSON
```


## Sample Interaction

### Shows profiles to which the bot has access
```
User> analytics profiles
SpikeBot> @User:
114783908 - Project X
123511123 - Site Plan B
128210353 - Hubot Chat
```

### Shows pageviews and visits of website with id 123123123
```
User> analytics pageviews 123123123
SpikeBot> @User: SiteName: 6346 visits and 12317 pageviews.
```

### Get percentage mobile x desktop access of website with id 123456
```
User> analytics devices 123456
SpikeBot> @User: desktop - 1450 sessions (21.75%)
mobile - 4903 sessions (73.54%)
tablet - 314 sessions (4.71%)
```

### Get browsers percentage access with id 654321
```
User> analytics browser 654321
SpikeBot> @User: Chrome - 3885 sessions (75.68%)
Firefox - 290 sessions (21%)
Internet Explorer - 115 sessions (3.32%)
```
