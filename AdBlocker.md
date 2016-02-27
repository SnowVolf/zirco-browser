# Introduction #

Zirco used the WebView component provided by the Android framework to display web pages. This component does not allow direct access to elements composing a web page, and thus cannot be used to filter ads.

Zirco ad-blocker operate by injecting a piece of Java-script (provided by [AdSweep](http://adsweep.org/)) to remove ads, right after a web page has loaded. This way of operation has two major drawbacks:

  1. It can only start to operate _after_ a page has been loaded, and may take some times to perform its filtering. As a result, ads are shown for some time (up to a few seconds, depending on your device) before being hidden;
  1. It can heavily slow down pages which use a lot of Java-script (like Google Reader for instance). It may be a good idea to add them to the ad-blocker white list (see below);

# White list #

Websites can be white-listed in order to prevent the ad-blocker to operate an them.

  1. Open the main menu, and go to _Preferences_;
  1. Scroll down to the _Ad-blocker settings_ section, and select _White list_;
  1. Click on the menu button, and select _Add_;
  1. Type the website name, and click on _Ok_;