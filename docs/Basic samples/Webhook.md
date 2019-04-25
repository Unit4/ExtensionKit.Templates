# Creating a flow with a ‘Webhook’ trigger

The Webhook trigger allows a HTTP request to initiate a Flow defined in the Unit4 Extensions Kit (U4EK). In a typical scenario this trigger would be utilized to allow a workflow defined somewhere else to continue execution in a U4EK Flow.

![broken image](images/Webhook_1.jpg)

Start configuration by selecting the trigger type: Webhook and filling Name and Authentication fields, Input Schema field is not mandatory but you can use it to include a valid Json Schema.

![broken image](images/Webhook_2.jpg)

![broken image](images/Webhook_3.jpg)

Select an action to be executed in combination with your trigger, in this case, the action selected is 'HTTP Request' that allows a flow to perform an HTTP action on a REST endpoint.

This action could be used for example to POST or DELETE to an endpoint, in order to create, update or delete a REST resource.

It can also be used to GET HTTP request method to retrieve data to pass to the next action.

![broken image](images/Webhook_4.jpg)

You must complete the information for mandatory fields.

Authentication type:
* _None_ -> No authentication needed
* _Basic_ -> Username and Password must be specified
* _Bearer_ -> Token endpoint, Client (Id and Secret) and Scope must be provided

Method: Indicates the desired action to be performed

Url: 

And optionally, include information for the rest of fields.

Content Type: Used to indicate the media type

Content: Here you can provide the Json Schema

![broken image](images/Webhook_5.jpg)

In the ‘Overview’ section the user will see a summary of the configuration during the creation process, also you can see an Extra data section where the system will generate 2 URI's. The first one, Address is the URI to which the data needs to be pushed by the external application. The second one, Metadata Address provides an endpoint that returns the metadata.

![broken image](images/Webhook_6.jpg)

In the ‘History’ section the flow will register every execution and the related data.

![broken image](images/Webhook_7.jpg)

Remember to add a name to your Flow and Save it.