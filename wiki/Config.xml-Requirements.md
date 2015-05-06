To properly use the functionality of bbUI in your application, you will need to properly configure your application's 
[config.xml file](http://developer.blackberry.com/html5/documentation/ww_developing/working_with_config_xml_file_1866970_11.html).  The bare minimum for your desired platform is outlined below.

## BlackBerry 10
```xml
<widget xmlns:rim="http://www.blackberry.com/ns/widgets" version="1.0.0" xmlns="http://www.w3.org/ns/widgets">  
    <name>My App Name</name>
    <content src="mystartpage.htm" />
</widget>
```
For full functionality you should also include the following BlackBerry 10 plug-ins for WebWorks 2.X
* com.blackberry.bbui
* com.blackberry.app
* com.blackberry.ui.contextmenu

## BlackBerry Playbook
```xml
<widget xmlns:rim="http://www.blackberry.com/ns/widgets" version="1.0.0" xmlns="http://www.w3.org/ns/widgets">  
    <name>My App Name</name>
    <content src="mystartpage.htm" />
    <rim:navigation mode="focus" /> <!-- Only applies for BB5/6/7 -->
    <feature id="blackberry.system.event" />
    <feature id="blackberry.app" />
    <feature id="blackberry.app.event"/>
</widget>
```

## BlackBerry BlackBerry 5/6/7
```xml
<widget xmlns:rim="http://www.blackberry.com/ns/widgets" version="1.0.0" xmlns="http://www.w3.org/ns/widgets">  
    <name>My App Name</name>
    <content src="mystartpage.htm" />
    <rim:navigation mode="focus" /> 
    <feature id="blackberry.system.event" />
    <feature id="blackberry.app" />
    <feature id="blackberry.app.event"/>
    <feature id="blackberry.ui.dialog" />
    <feature id="blackberry.ui.menu"/>
</widget>
```
