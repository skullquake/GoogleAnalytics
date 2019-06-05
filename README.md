# Google Analytics Custom Widget

Track pageviews and custom event with Google Analytics. If you have an e-commerce application, you can also use this widget to keep track of your transactions.

## Contributing

For more information on contributing to this repository visit [Contributing to a GitHub repository](https://world.mendix.com/display/howto50/Contributing+to+a+GitHub+repository)!

## Typical usage scenario
 
You want to track how often a product is viewed and inspect it in Google Analytics.
You want a detailed overview of all transactions

## Features and limitations

* Track custom events
* Track pageviews
* Track transactions

## Configuration

Insert the widget in a form. Configure the properties of the widget you have added to your page.
Please use a valid UA-XXXX-XX code in order to track traffic on your web application.

## Properties
All widgets in this package (except for the EventTrackerButton) should be placed inside an empty table row with only one cell. To avoid empty spaces, the cell is hidden from the user.

### EventTracker

* *Category*: The name you supply for the group of objects you want to track.
* * *Action*: A string that is uniquely paired with each category, and commonly used to define the type of user interaction for the web object.
* *Label*: An optional string to provide additional dimensions to the event data.
* *Value*: An integer that you can use to provide numerical data about the user even
 
(see http://code.google.com/apis/analytics/docs/tracking/eventTrackerGuide.html for more information)

### EventTrackerButton

This widget combines the built-in microflow trigger with the EventTracker. Inspect widget properties for details.

### MasterPageTracker

Typically you would want to start by using the MasterPageTracker by adding this widget to your master layout. By doing this, all pages in your Mendix application will be tracked by Google Analytics. You will need to provide the widget with the tracker ID (UA-XXX-XX) that you should receive when configuring your Google Analytics account. The Master Page Tracker widget will use the combination of module name and page name in Mendix as url to be reported to Google Analytics (e.g. a page in X module which is named Y will be registered as /X/Y in Google Analytics. Note: you can also define a prefix for the url).

By having a MasterPageTracker widget in the master layout, you don't need to define the tracker ID (UA-XXX-XX) in each of the (Advanced)PageTracker anymore since they will use the one from MasterPageTracker.

Note: MasterPageTracker should only be used one in your Mendix application.

### AdvancedPageTracker

* *Url*: The url which should be shown in the Google Analytics overview.
* *Title*: The title which should be shown in the Google Analytics overview.
* *Example*: if url is '/test/${name}', then if the url is parsed, '${name}' will be replaced by the value of current object's attribute which is defined in the Data source tab. Warning: The widget must be inside a DataView.

### PageTracker

It is exactly the same as AdvancedPageTracker but without the ability to use object's attribute value to build url/title. Consequently there is no need to have the widget inside a DataView.

### Webmaster tools

The Website Master tools allow you to focus on quality of your website / webapplicatie.
You can take a look here at what it can mean for your Mendix application:

https://www.google.com/webmasters/tools/

This widget will place a META verification tag inside the <HEAD> html tag.
So that the webmaster tools can be activated and help with SEO on Mendix applications.


## Upgrading from 1.1 to 2.0
- You can remove the following line from your index.html
```html 
<script type="text/javascript" src="widgets/analytics/lib/Tracker.js" uanumber="UA-XXXXXXXX-X"></script>
```
- Remove Analytics.mpk from your [%projectdir%]/widgets directory.


>>>>>>> b2964df6e963f3a4c797cc280f9111a37e8ebce5
