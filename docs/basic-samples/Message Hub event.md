# Creating a flow with a ‘Message Hub event’ trigger

The Message Hub Event trigger allows a flow to be initiated when a particular event is published on the Unit4 Message Hub by a specified source system.

Start configuration by selecting the trigger type: Message Hub Event
 
 ![broken image](images/Message_Hub_Event_1.jpg)

Then, add the Source System, Message Type, Name and Version. Every field counts with a dropdown to select the values, except Version field that will be filled according to the value set in Name field.
Source System: system in charge of publish messages regarding events occurring in others or to notify others about changes on itself.
Message Type: supported messages options that can be published by a source system.
Name: name of the event published by the source system.
Version: most recent version of the event.

*Take into account that if there is no event created for the selected Source System, in Name and Version fields wouldn’t be anything to show (fields are writable and you can fill them manually, but it doesn't mean that your flow will be well-configured and works).

![broken image](images/Message_Hub_Event_2.jpg)

![broken image](images/Message_Hub_Event_3.jpg)
 
![broken image](images/Message_Hub_Event_4.jpg)

![broken image](images/Message_Hub_Event_5.jpg)

Select an action to be executed in combination with your trigger, in this case, the action selected is HTTP Request, that allows to the new flow to perform an HTTP action on a REST endpoint.
Additional configuration can be passed like Headers, ContentType (list of most important MIME types) and Content.
After executing the request it will return the HTTP response status code and the response content as string.
 
![broken image](images/Message_Hub_Event_6.jpg)

![broken image](images/Message_Hub_Event_7.jpg)

Remember to add a name to your Flow and Save it.