SocialTeddy
===========

Sample kinoma application that leverages Apstrata's social network integration capabilities. 
This application is inspired from the Teddy Twinckle project. Its purpose is to simulate a set of sensors
and a control device hidden in a teddy bear. By pressing (touch/click on the screen) the bear’s cheeks or belly, 
the user posts a predefined message on his Facebook wall (sending a kiss to x /sending a hug to x). 

How to use
==========

* First step is to deploy some of the [Apstrata Facebook integration scripts](http://wiki.apstrata.com/pages/viewpageattachments.action?pageId=1213691&metadataLink=true) 
that are downloadable form the Apstrata wiki, to your Apstrata application account (easiest way is to use the Apstrata workbench)
  * social.api.facebookLogin
  * social.fb.facebookManager
  * social.fb.userManager
  * social.api.facebookPost
  * social.fb.common

**Note** Apstrata provides native objects API for connecting to social medias, as well as utility scripts that provide higher
level of abstraction. [Read more about the Apstrata Facebook scripts](http://wiki.apstrata.com/display/doc/Facebook+integration)

* Once the scripts are copied to your Apstrata application account, you need to configure
  
  
