# Google Analytics Custom Widget

Track pageviews and custom event with Google Analytics. If you have an e-commerce application, you can also use this widget to keep track of your transactions.

## Contributing

For more information on contributing to this repository visit [Contributing to a GitHub repository](https://world.mendix.com/display/howto50/Contributing+to+a+GitHub+repository)!

## Typical usage scenario
 
You want to know how often a product is viewed
You want a detailed overview of all transactions

## Features and limitations

Track custom events
Track pageviews
Track transactions

## Configuration

Insert the widget in a form
Configure the properties

## Properties
All widgets in this package (except for the EventTrackerButton) should be placed inside an empty table row with only one cell. To avoid empty spaces, the cell is hidden from the user.

### EventTracker

Category: The name you supply for the group of objects you want to track
Action: A string that is uniquely paired with each category, and commonly used to define the type of user interaction for the web object

Label: An optional string to provide additional dimensions to the event data.
Value: An integer that you can use to provide numerical data about the user even
Please use a proper UA-XXXX-XX code to start tracking.
 
(see http://code.google.com/apis/analytics/docs/tracking/eventTrackerGuide.html for more information)

### EventTrackerButton
This widget combines the built-in microflow trigger with the EventTracker. See these widgets for property details.

### PageTracker

Url: The url which should be shown in the Google Analytics overview
Parse url: Determines if words preceding a dollar sign '$' are replaced by the value of the corresponding attribute.
Example: if url is '/test/$name', then if the url is parsed, '$name' will be replaced by the value of current object's 'name' attribute. Warning: if 'parse url' is set to true, the widget must be inside a DataView. No consistency checks are applied to the url, so if the attribute does not exist, or its value is empty, the page will not be tracked.
Please use a proper UA-XXXX-XX code to start tracking.

### Webmaster tools

The Website Master tools allow you to focus on quality of your website / webapplicatie.
You can take a look here at what it can mean for your Mendix application:

https://www.google.com/webmasters/tools/

This widget will place a META verification tag inside the <HEAD> html tag.
So that the webmaster tools can be activated and help with SEO on Mendix applications.
