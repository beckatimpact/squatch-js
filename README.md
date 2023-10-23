# squatch-js
 
 > This repo is a barebones reference for the squatch.JS key scripts, displaying a working hardcoded loop with code examples including commentary.

## squatch.JS Key Scripts
- **Reference Guide:** https://docs.saasquatch.com/developer/squatchjs/v2

## Sample Referral Loop

1. **Load the Verified Access In-App Widget as a test Referrer:** https://beckatimpact.github.io/squatch-js/verified-widget.html
    - This page displays a widget for a user, which includes their share & referral information.
2. **Grab the sharelink from the widget and open it in an incognito window:** http://ssqt.co/mzxLQfw
    - This link (taken from the Referrer Widget) redirects you to the landing page (`index.html`), & drops a referral cookie.
    - Both the referral code from the cookie & the cookie value are exposed by use of the autofill method.
3. **Click on the "Example User Event" to trigger a new reward for the Referrer:** https://beckatimpact.github.io/squatch-js/user-event.html
    - This page uses the track user event script to send a purchase event along on the Referred User created on the landing page above.
4. **Return to/reload the "Verified Access In-App Widget" to see an additional reward appear:** https://beckatimpact.github.io/squatch-js/verified-widget.html
    - Each time `user-event.html` is loaded, another purchase event is tracked resulting in an additional reward.
5. **Create your own anonymous user by using the "Instant Access In-App Widget":** https://beckatimpact.github.io/squatch-js/instant-widget.html 
    - Use this page to test the instant access widget for an anonymous user; this user will not be referred.
    - Keep in mind that following the sharelink from your instant access widget will also not result in a referral as the landing page is hardcoded for the referred user in the flow above.

## Page Breakdown

- **index.html:** 
    - `squatch.api().upsertUser()` method (Create & update user)
    - `squatch.api().squatchReferralCookie()` method (Autofill from cookie)
- **verified-widget.html:**
    - Embedded "Verified Access Widget"
- **user-event.html:**
    - `squatch.events().track()` method (Track user event)
- **instant-widget.html:**
    - Embedded "Instant Acess Widget"
