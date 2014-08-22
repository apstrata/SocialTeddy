SocialTeddy
===========

Sample kinoma application that leverages Apstrata's social network integration capabilities. 
This application is inspired from the Teddy Twinckle project. Its purpose is to simulate a set of sensors
and a control device hidden in a teddy bear. By pressing (touch/click on the screen) the bear’s cheeks or belly, 
the user posts a predefined message on his Facebook wall (sending a kiss to x /sending a hug to x). 

How to install
==============

* Import the SocialTeddy application as a Kinoma project in Kinoma Studio

* Deploy some of the [Apstrata Facebook integration scripts](http://wiki.apstrata.com/pages/viewpageattachments.action?pageId=1213691&metadataLink=true) 
that are downloadable form the Apstrata wiki, to your Apstrata application account (easiest way is to use the Apstrata workbench)
  * social.api.facebookLogin
  * social.fb.facebookManager
  * social.fb.userManager
  * social.api.facebookPost
  * social.fb.common

**Note** Apstrata provides [native objects and APIs](http://wiki.apstrata.com/display/doc/Social+Networking+APIs) for connecting to social medias, as well as utility scripts that provide higher
level of abstraction. [Read more about the Apstrata Facebook scripts](http://wiki.apstrata.com/display/doc/Facebook+integration)

How to configure
================

* Once the scripts are copied to your Apstrata application account, you need to modify the "social.fb.common" file:
  * Verify that the value of the "storeName" variable is set to the name of your Apstrata store ("DefaultStore" by default)
  * Set the value of the "defaultAccountKey" variable to the value of your Apstrata account key
  * Change the value of the "appKey" variable to "535472373248192" (social teddy facebook app key)
  * Change the value of the "secret" variable to "62b492d864dd667481336277125452f6" (social teddy facebook app secret)
  * Make sure that the value of the "apstrataUrl" variable points to your Apstrata cluster endpoint

* You then need to create a user in Apstrata that will be associated to Facebook credentials granting access to the
facebook version of the social teddy application (needed to post of the user's wall). This is done by signing in to Apstrata through Facebook. 
**Note** This step is usually implemented in the application itself but we will do it manually for simplicity:
  * Sign it to the [Apstrata workbench](https://workbench.wot.apstrata.com)
  * Select the "social.api.facebookLogin" script and execute it by passing the following parameter "command" with value
  "getRequestToken"
  * Copy the value of the "authorizationUrl" result field and paste it into a browser. You are redirected to a Facebook login page where you will be asked to enter your credentials and grant some permissions. Once you do this, you are redirected to the "social.api.facebookLogin" script, which will automatically add a new user to Apstrata, or, if the user already existed, add a Facebook access token to the user's profile.

* Copy the Facebook access token (either from the user's profile in the Apstrata workbench or from the browser window)
* Open the main.xml file of the SocialTeddy project in Kinoma Studio:
  * Paste the token as a value of the "usersFacebookToken" field
  * Verify that the value of the "apstrataAuthKey" field is set to your Apstrata auth key
  * Verify the the value of the "postUrl" variable in the "postMessage" method points to your Apstrata cluster endpoint

How to use
==========

* Run the SocialTeddy application. A teddy bear is displayed on the screen. The “name” of the recipient of the messages that will be posted on the Facebook wall is displayed in the upper left corner.
* Tap/click on the right hand of the teddy bear to shift to another recipient (person to who you will send a message on your Facebook wall)
* Tap/click on one of the bear’s cheeks. The device sends a request to an Apstrata social script to post a message to the user’s wall (e.g. “sending a kiss to dad”)
* /click on one the bear’s belly. The device sends a request to an Apstrata social script to post a message to the user’s wall (e.g. “sending a big hug to dad”)



  
  
