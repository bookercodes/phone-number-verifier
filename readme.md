# Node Phone Number Verifier

Minimal Node module to verify phone numbers using [Twilio Verify](https://www.twilio.com/verify).

## Use-cases
* Make sure your user actually has access to a phone number before sending messages and inuring $

## Install

```
npm install @bookercodes/phone-number-verifier
```

## Usage

Import then instantiate `@bookercodes/phone-number-verifier` with your Twilio Verify key.

```js
const NumberVerifier = require('@bookercodes/phone-number-verifier')
const numberVerifier = new NumberVerifier({ apiKey: '1eM91xy4Wkqy0vYSy2wEUqS8HDpAAG2' })
```


Send verification token:

```js
try {
  await numberVerifier.sendCode({
    countryCode: '44',
    phoneNumber: ''
  })
} catch (error) {
  console.error('error', error)
}
```

Check the verification token:

```js
try {
  const response = await numberVerifier.checkCode({
    countryCode: '44',
    phoneNumber: '',
    verificationCode: '123'
  })
} catch (error) {
  console.error('error', error)
}
```

**Remember to `catch` errors**.
