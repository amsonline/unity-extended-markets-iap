# unity-extended-markets-iap
A patch for Unity IAP which is compatible with additional markets.

Currently, Iranian markets (Cafe Bazaar, Myket, Iran Apps, Jhoobin and Avval Market) are supported.

## Features
1. Create apps for multiple markets using a single code. There is no need to change a single line of your code. Just change your permission, the library will handle the rest!
2. No RSA key is mandatory.
3. Works with all markets using Google's InAppBilling v3.
4. This patch will **NOT** change the behavior of any parts of your codes. It only changes the target intent of your market.

## Implementation
First, implement Unity Purchasing into your project through Unity Services ([How?](https://unity3d.com/learn/tutorials/topics/ads-analytics/integrating-unity-iap-your-game)).

Then, navigate to `<your-project-folder>/Assets/Plugins/UnityPurchasing/Bin/Android` and replace the `GooglePlay.aar` with the one provided in this repo.

DONE!

## Usage
The library detects the version through the permission in your manifest. You must put the following permissions in order to use the corresponding intent in your app:

**Play Store (default behavior):** `<uses-permission android:name="com.android.vending.BILLING"/>`

**Cafe Bazaar:** `<uses-permission android:name="com.farsitel.bazaar.permission.PAY_THROUGH_BAZAAR" />`

**Myket:** `<uses-permission android:name="ir.mservices.market.BILLING"/>`

**Iran Apps:** `<uses-permission android:name="ir.tgbs.iranapps.permission.BILLING "/>`

**Avval Market:** `<uses-permission android:name="com.hrm.android.market.permission.PAY_THROUGH_MARKET" />`

Whenever you implemented the IAP correctly in your project, the project will work like a charm!

## Known bugs
- In all markets except Play Store, the app will be restarted if the purchase is failed (User cancelling the purchase or anything else). I couldn't figure out the problem, so I appreciate anyone who can improve this code and fix this bug.

# Used by...
1. [FCMine - Online Football Management Game](https://play.google.com/store/apps/details?id=com.avagames.fcmine)

Send me your app after you published it in markets, and I will add it in the list!
