# com-chilipeppr-widget-pickandplace
This widget it's a part of eagle import and can place components on your milled PCB.

![alt text](screenshot.png "Screenshot")

## ChiliPeppr Widget / Pick&Place

All ChiliPeppr widgets/elements are defined using cpdefine() which is a method
that mimics require.js. Each defined object must have a unique ID so it does
not conflict with other ChiliPeppr widgets.

| Item                  | Value           |
| -------------         | ------------- | 
| ID                    | com-chilipeppr-widget-pickandplace |
| Name                  | Widget / Pick&Place |
| Description           | This widget it's a part of eagle import and can place components on your milled PCB. |
| chilipeppr.load() URL | http://raw.githubusercontent.com/xpix/chilipeppr-widget-eagle-dispenser/master/auto-generated-widget.html |
| Edit URL              | http://ide.c9.io/xpix/chilipeppr-eagle-plugandplay |
| Github URL            | http://github.com/xpix/chilipeppr-widget-eagle-dispenser |
| Test URL              | http://chilipeppr-eagle-plugandplay-xpix.c9users.io/widget.html |

## Example Code for chilipeppr.load() Statement

You can use the code below as a starting point for instantiating this widget 
inside a workspace or from another widget. The key is that you need to load 
your widget inlined into a div so the DOM can parse your HTML, CSS, and 
Javascript. Then you use cprequire() to find your widget's Javascript and get 
back the instance of it.

```javascript
chilipeppr.load(
  "#myDivWidgetInsertedInto",
  "http://raw.githubusercontent.com/xpix/chilipeppr-widget-eagle-dispenser/master/auto-generated-widget.html",
  function() {
    // Callback after widget loaded into #myDivWidgetInsertedInto
    cprequire(
      "inline:com-chilipeppr-widget-pickandplace", // the id you gave your widget
      function(mywidget) {
        // Callback that is passed reference to your newly loaded widget
        console.log("My widget just got loaded.", mywidget);
        mywidget.init();
      }
    );
  }
);

```

## Publish

This widget/element publishes the following signals. These signals are owned by this widget/element and are published to all objects inside the ChiliPeppr environment that listen to them via the 
chilipeppr.subscribe(signal, callback) method. 
To better understand how ChiliPeppr's subscribe() method works see amplify.js's documentation at http://amplifyjs.com/api/pubsub/

| Signal | Description |
| ------ | ----------- |
| (No signals defined in this widget/element) |

## Subscribe

This widget/element subscribes to the following signals. These signals are owned by this widget/element. Other objects inside the ChiliPeppr environment can publish to these signals via the chilipeppr.publish(signal, data) method. 
To better understand how ChiliPeppr's publish() method works see amplify.js's documentation at http://amplifyjs.com/api/pubsub/

| Signal | Description |
| ------ | ----------- |
| /com-chilipeppr-widget-pickandplace/com-chilipeppr-widget-eagle/beforeRender | Remove PNP Holder in 3d space. || /com-chilipeppr-widget-pickandplace/com-chilipeppr-widget-eagle/afterRender | Render PNP Holder in 3d space to inform user which tray are busy. || /com-chilipeppr-widget-pickandplace/com-chilipeppr-widget-eagle/addGcode | Produce gcode and add this to main gcode buffer. |

## Foreign Publish

This widget/element publishes to the following signals that are owned by other objects. 
To better understand how ChiliPeppr's subscribe() method works see amplify.js's documentation at http://amplifyjs.com/api/pubsub/

| Signal | Description |
| ------ | ----------- |
| (No signals defined in this widget/element) |

## Foreign Subscribe

This widget/element publishes to the following signals that are owned by other objects.
To better understand how ChiliPeppr's publish() method works see amplify.js's documentation at http://amplifyjs.com/api/pubsub/

| Signal | Description |
| ------ | ----------- |
| (No signals defined in this widget/element) |

## Methods / Properties

The table below shows, in order, the methods and properties inside the widget/element.

| Item                  | Type          | Description |
| -------------         | ------------- | ----------- |
| id | string | "com-chilipeppr-widget-pickandplace"<br><br>The ID of the widget. You must define this and make it unique. |
| name | string | "Widget / Pick&Place" |
| desc | string | "This widget it's a part of eagle import and can place components on your milled PCB." |
| url | string | "http://raw.githubusercontent.com/xpix/chilipeppr-widget-eagle-dispenser/master/auto-generated-widget.html" |
| fiddleurl | string | "http://ide.c9.io/xpix/chilipeppr-eagle-plugandplay" |
| githuburl | string | "http://github.com/xpix/chilipeppr-widget-eagle-dispenser" |
| testurl | string | "http://chilipeppr-eagle-plugandplay-xpix.c9users.io/widget.html" |
| pnpholders | object | PICK AND PLACE VARIABLES. |
| holderCoordinates | object |  |
| components | object |  |
| packagesTrays | object |  |
| publish | object | Please see docs above.<br><br>Define the publish signals that this widget/element owns or defines so thatother widgets know how to subscribe to them and what they do. |
| subscribe | object | Please see docs above.<br><br>Define the subscribe signals that this widget/element owns or defines so thatother widgets know how to subscribe to them and what they do. |
| foreignPublish | object | Please see docs above.<br><br>Document the foreign publish signals, i.e. signals owned by other widgetsor elements, that this widget/element publishes to. |
| foreignSubscribe | object | Please see docs above.<br><br>Document the foreign subscribe signals, i.e. signals owned by other widgetsor elements, that this widget/element subscribes to. |
| init | function | function () <br><br>All widgets should have an init method. It should be run by theinstantiating code like a workspace or a different widget. |
| onBeforeRender | function | function (that) |
| onAfterRender | function | function (that) |
| onAddGcode | function | function (that) |
| registerEagleComponents | function | function (self) |
| sortTrayComponents | function | function () |
| selectbox | function | function (id, hash, outcallback)<br><br>empty and fill select box |
| table | function | function (id, array)<br><br>empty and fill table |
| options | object | User options are available in this property for reference by yourmethods. If any change is made on these options, please callsaveOptionsLocalStorage() |
| setupUiFromLocalStorage | function | function () <br><br>Call this method on init to setup the UI by reading the user'sstored settings from localStorage and then adjust the UI to reflectwhat the user wants. |
| saveOptionsLocalStorage | function | function () <br><br>When a user changes a value that is stored as an option setting, youshould call this method immediately so that on next load the valueis correctly set. |
| forkSetup | function | function () <br><br>This method loads the pubsubviewer widget which attaches to our upper right corner triangle menu and generates 3 menu items likePubsub Viewer, View Standalone, and Fork Widget. It also enablesthe modal dialog that shows the documentation for this widget.<br><br>By using chilipeppr.load() we can ensure that the pubsubviewer widgetis only loaded and inlined once into the final ChiliPeppr workspace.We are given back a reference to the instantiated singleton so itsnot instantiated more than once. Then we call it's attachTo methodwhich creates the full pulldown menu for us and attaches the clickevents. |


## About ChiliPeppr

[ChiliPeppr](http://chilipeppr.com) is a hardware fiddle, meaning it is a 
website that lets you easily
create a workspace to fiddle with your hardware from software. ChiliPeppr provides
a [Serial Port JSON Server](https://github.com/johnlauer/serial-port-json-server) 
that you run locally on your computer, or remotely on another computer, to connect to 
the serial port of your hardware like an Arduino or other microcontroller.

You then create a workspace at ChiliPeppr.com that connects to your hardware 
by starting from scratch or forking somebody else's
workspace that is close to what you are after. Then you write widgets in
Javascript that interact with your hardware by forking the base template 
widget or forking another widget that
is similar to what you are trying to build.

ChiliPeppr is massively capable such that the workspaces for 
[TinyG](http://chilipeppr.com/tinyg) and [Grbl](http://chilipeppr.com/grbl) CNC 
controllers have become full-fledged CNC machine management software used by
tens of thousands.

ChiliPeppr has inspired many people in the hardware/software world to use the
browser and Javascript as the foundation for interacting with hardware. The
Arduino team in Italy caught wind of ChiliPeppr and now
ChiliPeppr's Serial Port JSON Server is the basis for the 
[Arduino's new web IDE](https://create.arduino.cc/). If the Arduino team is excited about building on top
of ChiliPeppr, what
will you build on top of it?



