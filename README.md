JavaScript Dynamic Content shim for Windows Store apps
=====
Use all your favorite JavaScript libraries to create Windows Store apps on Windows 8

Developers can use a wide variety of JavaScript APIs to leverage the power and broad capabilities of Windows in Windows Store apps. In order to prevent unwanted access to the [Windows Runtime](http://msdn.microsoft.com/en-us/library/windows/desktop/br211377.aspx), [restrictions and measures](http://msdn.microsoft.com/en-us/library/windows/apps/hh849625.aspx) restrictions and measures are set in place so that malicious script will not compromise an app's integrity. In some cases, however, this security model may prevent some JavaScript libraries to run as intended. A handful of popular, third-party libraries happen to use code which is flagged as unsafe, and therefore will not work as expected in Windows Store apps. These libraries include but are not limited to [AngularJS](https://angularjs.org/), [Ember.js](http://emberjs.com/), [KnockoutJS](http://knockoutjs.com/).

Today, running a Windows Store app using AngularJS in Visual Studio might return the following error: "JavaScript runtime error: Unable to add dynamic content. A script attempted to inject dynamic content, or elements previously modified dynamically, that might be unsafe."

![](https://raw.githubusercontent.com/MSOpenTech/winstore-jscompat/master/error.PNG?token=3019602__eyJzY29wZSI6IlJhd0Jsb2I6TVNPcGVuVGVjaC93aW5zdG9yZS1qc2NvbXBhdC9tYXN0ZXIvZXJyb3IuUE5HIiwiZXhwaXJlcyI6MTQwNjU3OTYyOX0%3D--101970399d1c4e94bbe251e71e78f8be6af6d7ba)

Properties such as innerHTML and outerHTML are filtered in order to avoid the common security issues that can result from the unsafe handling of untrusted data.

In order to unblock these setbacks, Microsoft Open Technologies (MS Open Tech) has released the JavaScript Dynamic Content shim for Windows Store apps. This mitigation relaxes the manner in which checks are performed, yet still achieves the fundamental goal set by the security model.

# Instructions
Simply reference the `winstore-jscompat.js` file towards the beginning of your app, before any other scripts are run.

**Note:** You do not need to include this file for Windows 10 apps.

Please note that there may be a minor impact on your app's performance, the extent of which depends upon the specific usage, timing, and frequency of the three property calls listed above.
