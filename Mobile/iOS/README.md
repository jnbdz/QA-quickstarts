# iOS | Mobile | QA Quickstarts

## Use Inspect Elements for the browser in the iOS simulation
1. Open Safari
2. Click on the **Develop** in the top menu
    - Simulator - iPhone... (whatever the deice name your testing on) > Safari > localhost - ...(the page you are testing)
3. You should see the the Safari "**Web Inspector**" window open

## Certificate Error
When you are testing locally or you are using custom certificates you might run into these errors: 
```
[Error] Failed to load resource: The certificate for this server is invalid. You might be connecting to a server that is pretending to be "fonts.googleapis.com" which could put your confidential information at risk.
[Error] Failed to load resource: The certificate for this server is invalid. You might be connecting to a server that is pretending to be "www.google.com" which could put your confidential information at risk.
[Error] postscribe error recaptcha implementation - {msg: "remote script failed https://www.google.com/recaptcha/api.js?onload=recaptchaCallback&hl=en"}
```

The list of iOS supported certificate providers: https://support.apple.com/en-us/HT209143

> NOTE: Some companies used their own certificates so you will need to added them to your iOS.

### Solution
1. Open `Keychain Access` in `Utilities`
2. On the left side manu click on **System Keychains > System** then on top click on the tab **Certificates**
3. Right-click on the certificates that you want to add support for in your iOS (simulation)
    - Click **Export "..."**
    - In the popup window change the **File Format** to "**Privacy Enhance Mail (.pem)**"
    - Select a destination
    - Click **Save**
4. From the directory where the `.pem` was saved, drag-and-drop it in the simulation
5. Enable the certification in the simulation you go to the **Settings** App (in the simulation)
    - **General > About > Certificate Trust Settings**
6. You can now test everything
