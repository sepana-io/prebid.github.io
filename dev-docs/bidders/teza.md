## Teza

### Features
Bidder Code `teza`  
Prebid.org Member no  
Prebid.js Adapter yes  
Prebid Server Adapter no  
Media Types display  
Multi Format Support will-bid-on-any  
TCF-EU Support yes  
GPP Support tcfeu, usp  
USP/CCPA Support yes  
COPPA Support yes  
Supply Chain Support yes  
Demand Chain Support no  
Safeframes OK yes  
Supports Deals yes  
Floors Module Support yes  
First Party Data Support yes  
User IDs all

### Bid Params
| Name          | Scope     | Description                           | Example     | Type    |
|---------------|-----------|---------------------------------------|-------------|---------|
| `account`     | required  | Account identifier provided by Teza   | `acct123`   | string  |
| `tagid`       | required  | Placement/tag identifier              | `atagid`    | string  |
| `test`        | optional  | Enable test flow                      | `true`      | boolean |
| `bidfloor`    | optional  | Floor price                           | `0.01`      | number  |
| `bidfloorcur` | optional  | Floor currency                        | `USD`       | string  |

### Notes
- Requests are OpenRTB 2.x POSTs to Teza’s auction endpoint with `?test=1&account={account}`.  
- Adapter forwards GDPR/USP/GPP, user IDs (`user.ext.eids`), and `schain`.  
- No user syncs required for basic operation.

### Test Parameters
```js
var adUnits = [{
  code: 'div-1',
  mediaTypes: { banner: { sizes: [[300, 250]] } },
  bids: [{
    bidder: 'teza',
    params: {
      account: 'acct123',
      tagid: 'atagid',
      test: true
    }
  }]
}];
