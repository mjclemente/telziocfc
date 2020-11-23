# telziocfc

A CFML wrapper for the [Telzio API](https://developer.telzio.com/reference). Interact with Telzio's VOIP phone system to get call information, make calls, send SMS, manage your account, and more.

*This is an early stage wrapper. I've implemented the methods that I need to use, but it's by no means complete. It should provide a good starting point, if more functionality is needed. Feel free to use the issue tracker to report bugs or suggest improvements!*

## Acknowledgements

This project borrows heavily from the API frameworks built by [jcberquist](https://github.com/jcberquist). Thanks to John for all the inspiration!

## Table of Contents

- [Quick Start](#quick-start)
- [`telziocfc` Reference Manual](#reference-manual)

## Quick Start

The following is a quick example of sending an SMS via one of your Telzio phone numbers, using this wrapper.

```cfc
telzio = new path.to.telziocfc.telzio( api_key = 'xxx', api_secret = 'xxx' );

result = telzio.sendSMS( from = '+12024561111', to = '+19998765309', message = 'Jenny, Jenny, who can I turn to?' );

writeDump( var='#result#', abort='true' );
```

### Reference Manual

#### `dialExternalPhone( required string from, required string aleg, required string bleg )`

Dials an external phone number, and when answered connects it to an extension, username or another external phone number. The parameter `aleg` The E164 formatted number in your Telzio account to dial from. This call will be charged towards this number's plan For example: +18889989080. The parameter `bleg` The extension, username or E164 formatted phone number to dial when Aleg has been answered.. *[Further docs](https://developer.telzio.com/reference#dial-outbound-number)*

#### `getAccountBalance()`

Retrieve your current account balance in USD. *[Further docs](https://developer.telzio.com/reference#balance)*

#### `sendSMS( required string from, required string to )`

Send SMS from your Telzio phone number. *[Further docs](https://developer.telzio.com/reference#send-sms)*

---
