# Giphy Core SDK for JS

The **Giphy Core SDK** is a wrapper around [Giphy API](https://github.com/Giphy/GiphyAPI).

![Build Status](https://travis-ci.com/Giphy/giphy-web-sdk-core.svg?token=ytpQbMSuy8sydsqZwbwp&branch=master&style=flat-square)   [![Version][version-svg]][package-url] [![License][license-image]][license-url] [![Downloads][downloads-image]][downloads-url]


[license-image]: https://img.shields.io/badge/license-MIT-green.svg?style=flat-square
[license-url]: LICENSE.md
[downloads-image]: https://img.shields.io/npm/dm/giphycore.svg?style=flat-square
[downloads-url]: http://npm-stat.com/charts.html?package=giphy-web-sdk-core
[version-svg]: https://img.shields.io/npm/v/giphycore.svg?style=flat-square
[package-url]: https://npmjs.org/package/giphy-web-sdk-core

[Giphy](https://www.giphy.com) is the best way to search, share, and discover GIFs on the Internet. Similar to the way other search engines work, the majority of our content comes from indexing based on the best and most popular GIFs and search terms across the web. We organize all those GIFs so you can find the good content easier and share it out through your social channels. We also feature some of our favorite GIF artists and work with brands to create and promote their original GIF content.

[![](https://media.giphy.com/media/5xaOcLOqNmWHaLeB14I/giphy.gif)]()

# Getting Started

### Supported End-points

* Search Gifs/Stickers
* Trending Gifs/Stickers
* Translate Gifs/Stickers
* Random Gifs/Stickers
* GIF by ID(s)
* Categories for Gifs
* Subcategories for Gifs
* GIFs by Category
* Query Suggestions


# Setup

### Require Module


npm
```shell
npm install --save giphy-web-sdk-core
```
In a browser 
```html
<script src="GphApiClient.js"></script>
```
### Initialize Giphy SDK

```javascript
var GphApiClient = require('giphy-web-sdk-core')
client = GphApiClient("YOUR_API_KEY")
```

### Search Endpoint
Search all Giphy GIFs for a word or phrase. Punctuation will be stripped and ignored.

```javascript
/// Gif Search
client.search('gifs', {"q": "cats", "limit": int, "offset": int, "rating": string, "lang": string}).then((response) => {

}).catch((err) => {

})

/// Sticker Search
client.search('stickers', {"q": "cats", "limit": int, "offset": int, "rating": string, "lang": string}).then((response) => {

}).catch((err) => {

})
```
### Trending Endpoint
Fetch GIFs currently trending online. Hand curated by the Giphy editorial team. The data returned mirrors the GIFs showcased on the [Giphy](https://www.giphy.com) homepage.

```javascript
/// Trending Gifs
client.trending("gifs", {"limit": int, "offset": int, "rating": string}).then((response) => {

}).catch((err) => {

})

/// Trending Stickers
client.trending("stickers", {"limit": int, "offset": int, "rating": string}).then((response) => {

}).catch((err) => {

})
```

### Translate Endpoint
The translate API draws on search, but uses the Giphy "special sauce" to handle translating from one vocabulary to another. In this case, words and phrases to GIFs. Example implementations of translate can be found in the Giphy Slack, Hipchat, Wire, or Dasher integrations. Use a plus or url encode for phrases.

```javascript
/// Translate to a Gif
client.translate('gifs', {"s": 'cool', "rating": string, "lang": string}).then((response) => {

}).catch((err) => {

})

/// Translate to a Sticker
client.translate('stickers', {"s": 'cool', "rating": string, "lang": string}).then((response) => {

}).catch((err) => {

})
```

### Random Endpoint
Returns a random GIF, limited by tag. Excluding the tag parameter will return a random GIF from the Giphy catalog.

```javascript
/// Random Gif
client.random('gifs', {"tag": string, "rating": string}).then((response) => {

}).catch((err) => {

})

/// Random Sticker
client.random('stickers', {"tag": string, "rating": string}).then((response) => {

}).catch((err) => {

})
```

### Get GIF by ID Endpoint
Returns meta data about a GIF, by GIF id. In the below example, the GIF ID is "feqkVgjJpYtjy"

```javascript
/// Gif by Id
client.gifById("feqkVgjJpYtjy").then((response) => {

}).catch((err) => {

})
```

### Get GIFs by IDs Endpoint
A multiget version of the get GIF by ID endpoint. In this case the IDs are feqkVgjJpYtjy and 7rzbxdu0ZEXLy.

```javascript
/// Gifs by Ids

client.gifsByIds({"ids": ["feqkVgjJpYtjy", "7rzbxdu0ZEXLy"]}).then((response) => {

}).catch((err) => {

})
```

# CONTRIBUTING

Managing git repositories can be hard, so we've laid out a few simple guidelines to help keep things organized.

## Guidelines

1. Create a **Pull Request**; instead of pushing directly to `master`.

2. Give your branch a **descriptive name** like `dh-network-fix` instead of something ambiguous like `my-branch`.

3. Write a **descriptive summary** in the comment section on Github.

4. **Don't merge your own Pull Request**; send it to your teammate for review.

5. If you think something could be improved: **write a comment on the Pull Request** and send it to the author.

6. Make sure your branch is based off `master`, and not some other outdated branch.

7. **Don't reuse branches.** Once they're merged to `master` you should consider deleting them.

8. Prefer **squash** when doing a **Pull Request**, as it simplifies the commit history.
