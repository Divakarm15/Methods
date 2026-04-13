# 2FA Bypass

* 1:- Password Reset Disable 2FA	
* 2:- No Rate limit
* 3:- Sending all alphabets instead of number
* 4:- Status Code Manipulation
* 5:- 2FA bypass by substituting part of the request from the session of another account. 
    ```
    If a parameter with a specific value is sent to verify the code in the request, try sending the value from the request of another account.
    
    For example, when sending an OTP code, the form ID/user ID or cookie is checked, which is associated with sending the code. If we apply the data from the parameters of the account on which you want to bypass code verification (Account 1) to a session of a completely different account (Account 2), receive the code and enter it on the second account, then we can bypass the protection on the first account. After reloading the page, 2FA should disappear.
    ```
 * 6:- Bypass 2FA using the “memorization” functionality.
		
    `Many sites that support 2FA, have a “remember me” functionality. It is useful when the user doesn’t want to enter a 2FA code on subsequent login windows. And it is important to identify the way in which 2FA is “remembered”. This can be a cookie, a value in session/local storage, or simply attaching 2FA to an IP address.`
 * 7:- OTP Leakage in Response
 * 8:- Bypassing 2fa Via OAuth mechanism ( Mostly not Applicable one )
		
    `Site.com requests Facebook for OAuth token > Facebook verifies user account > Facebook send callback code > Site.com logs a user in (Rare case)`
 * 9:- Bypassing 2fa using response manipulation
   ```
   Enter correct OTP -> Intercept & capture the response -> logout -> enter wrong OTP -> Intercept & change the response with successful previous response -> logged in
   ```
 * 10:- CSRF on 2FA Disable Feature.
    ```
    Signup for two account -> Login into attacker account & capture the disable 2FA request -> generate CSRF POC with .HTML extension -> Login into victim account and fire the request — — -> It disable 2FA which leads to 2FA Bypass.
    ```
 * 11:- Bypass 2FA by Adding null or 000000
 * 12:- Bypass 2FA by Batch API request
    ```
    Suppose if 2FA parameter like "code" of "OTP" is going with the request, add same parameter into the request multiple times like BATCH Mode for REST APi.
    ```

Resoponse Manipulation

-- Enter correct OTP, get the response of correct otp paste it when you entered the invalid respons
2FA code leakage in response

--- Request for 2FA and incept the request, Analyze the reponse and see if the code is leaked or not
2FA re-usability


1. log in as attacker (give otp0 save session for 1 week or 1 months (if option is there)
2. change the email into victim (it should be new account)(so you will not providing otp for it)



1.login to  a account and enable 2mfa
2.now use the cookie tool and copy the cookie paste it in a browser 
3. the acc will loggedin without asking for 2mfa

--- authenticate yourself, if the 2FA is still poped up and you got cookie/token, copy the 2FA enabled account and paste it to another user.

