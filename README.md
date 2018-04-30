# Rakuten Linkshare API

[![npm package](https://nodei.co/npm/rakuten-api.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/rakuten-api/)

API integration with Rakuten Linkshare

## Install

```bash
$ npm install rakuten-api
```

## Get Affiliate ID, Auth Basic and Report ID

* Create account - https://signup.linkshare.com/publishers/registration/landing?ls-locale=us&host=linkshare
* Get Affiliate ID - https://pubhelp.rakutenmarketing.com/hc/en-us/articles/201848138-What-is-my-Affiliate-ID-?flash_digest=0d0d41fd46a159b4bb54f690a64edd333414c369
* Auth Basic - https://developers.rakutenmarketing.com/console/registry/resource/_system/governance/apimgt/applicationdata/provider/RakutenMarketing/artifacts/API_Developer_Portal-Acquiring_Your_Access_Token_Guide.pdf
* Custom Report - http://affiliatetip.com/custom-reporting-for-advertisers-from-rakuten-linkshare/

## Usage

```js
"use strict";

let Rakuten = require("rakuten-api"),
    rakuten = new Rakuten("user", "pass", "affid", "auth basic");

rakuten.programs({}, function(err, result){
    console.log(result);
});

rakuten.coupons({}, function(err, result){
    console.log(result);
});

rakuten.report("report name", "token", "2016-01-01", "2016-07-16", function(err, result){
    console.log(result);
});

rakuten.deeplink("http://www.zattini.com.br/", "h5aPSz1vA84", 41254, function(err, url){
    console.log(url);//http://click.linksynergy.com/deeplink?id=h5aPSz1vA84&mid=41254&murl=http%3A%2F%2Fwww.zattini.com.br%2F
});
```

## License

  MIT

  Copyright (C) 2016 André Ferreira

  Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

  The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

  THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
