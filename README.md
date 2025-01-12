
# Browser link for Port apps

Login widget creates a connection to Port app (using QR code, magnet link or simple copy-paste function).  
[View demo.](https://htmlpreview.github.io/?https://github.com/ZeroPass/browser-link-for-port-apps/blob/main/index.html)

## Installation

Browser link for Port apps is a simple HTML widget (lightweight) - no additional packages needed. It runs in browser.

## Prerequirements

Create [dynamic link ](https://firebase.google.com/docs/dynamic-links/create-links) with one of four options on the Firebase platform. You don't need to create an entire dynamic link, only a dynamic_link URL is required. Other parameters are created by script in this repository.


## How to run

1. Copy two files 'js/browser-link-for-port-apps.js' and 'css/browser-link-for-port-apps.css' to your project.

1. Include .js file into your header:
```
<script src="<path>/browser-link-for-port-apps.js"></script>
```
3. Include .css file into your header:

```
<link href="<path>/browser-link-for-port-apps.css" rel="stylesheet" type="text/css"> 
```

## Implementation on website

Create div section; where the widget will be presented:
```
<div class="divqr">
   <section id="zeropass-port-qr"></section>
</div>
```

Call the render script:
```
<script>
 var androidData = {"apn":"<apn>",
                    "afl":"<link_to_play_store>",
                "version":'<min_sdk_version>'};

 var iosData = {"ibi":"<apple_store_id>",
                "isi":"<link_to_app_store>",
                "imv":<min_ios_version_integer>}

 var shortLinkURL = "<short_link>";
 var deepLinkURL = "<deep_link>";

 ZeroPassPortWidget.render(shortLinkURL,
                           deepLinkURL,
                           androidData,
                           iosData,
                           { 
                              userID: "<user_id>",
                              requestType: "<request_type>", //only ATTESTATION_REQUEST, PERSONAL_INFORMATION_REQUEST, FAKE_PERSONAL_INFORMATION_REQUEST, LOGIN allowed
                              url: "<url>"
                           },
                           document.querySelector('#zeropass-port-qr'));
</script>
```

Check example in index.html file

## License
[MIT](https://choosealicense.com/licenses/mit/)