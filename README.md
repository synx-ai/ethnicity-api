# Ethnicity API

Predict an ethnicity based on name and surname. The API uses a Machine Learning trained model to predict the probabilities across 20 classes.

(View demo)[https://synx-co.github.io/ethnicity-api/]

## How to use it

Authenticate to the API to get `access_token`.

```javascript
var auth_settings = {
  "url": "https://ethnicity.synx.co/api/auth",
  "method": "POST",
  "headers": {
    "content-type": "application/json"
  },
  "data": JSON.stringify({
    username: "8AS19LAS26",
    password: "c4ca4238a0b923820dcc509a6f75849b"
  })
}

$.ajax(auth_settings).done(function (response) {
  console.log(response.auth_token)
});
```

Predcit the ethnicity by posting a list of name and surname pairs.

```javascript
var predict_settings = {
  "url": "https://ethnicity.synx.co/api/predict",
  "method": "POST",
  "headers": {
    "content-type": "application/json",
    "authorization": "JWT " + access_token
  },
  "data": JSON.stringify({
    payload: [
      { name: input_name, surname: input_surname }
    ]
  })
}

$.ajax(auth_settings).done(function (response) {
  console.log(response)
});
```

## License

MIT License

Copyright (c) 2017 synx.co

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
