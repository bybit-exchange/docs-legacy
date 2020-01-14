---
title: Bybit API Docs

logo:
  link: https://www.bybit.com/
  target: _blank


language_tabs: # must be one of https://git.io/vQNgJ
  - console

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - api_auth  # Authentication
  - market_data  # Market Data Endpoints
  - account_data  # Account Data Endpoints
  - wallet_data  # Wallet Data Endpoints
  - api_data  # API Data Endpoints
  - rate_limits  # Rate Limits
  - websockets  # Websocket data
  - errors  # Errors
  - enums  # ENUM Definitions


search: true
---

<!---
Clipboard script
-->

<script src="../dist/clipboard.min.js"></script>

<script>
var clipboard = new ClipboardJS('.clipboard_button');

clipboard.on('success', function(e) {
    console.log(e);
});

clipboard.on('error', function(e) {
    console.log(e);
});
</script>



# Introduction

Welcome to the official documentation for the [Bybit](https://www.bybit.com/) APIs and Websocket! Here you can find details on how to access all of our endpoints, their respective expected outputs, and possible errors you may encounter.

If you encounter an issue you need help with, have a suggestions for us, or just want to have a chat with fellow developers then please head on over to our [API Telegram chat](https://t.me/Bybitapi)!


### Bybit API Resources
<ul>
  <li><a href="https://github.com/bybit-exchange/bybit-official-api-docs">bybit-official-api-docs <img src="images/github_logo_icon.png" height="14", width="14"></a> - report issues here!
  <li><a href="https://github.com/bybit-exchange/api-connectors/">Bybit's api-connectors <img src="images/github_logo_icon.png" height="14", width="14"></a> - find a repo of prebuilt libraries here!
  <li><a href="https://t.me/Bybitapi">API Discussion Group <img src="images/telegram_logo_icon.png" height="14", width="14"></a> - get help here!
  <li><a href="https://t.me/Bybit_API_Announcements">API Announcements Channel <img src="images/telegram_logo_icon.png" height="14", width="14"></a> - subscribe for changes to the API!
</ul>
