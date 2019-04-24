# Creating a flow with a ‘Webhook’ trigger

The Webhook trigger allows a HTTP request to initiate a Flow defined in the Unit4 Extensions Kit (U4EK). In a typical scenario this trigger would be utilized to allow a workflow defined somewhere else to continue execution in a U4EK Flow.

![broken image](images/Webhook_1.jpg)

Start configuration by selecting the trigger type: Webhook and filling Name and Authentication fields (Input Schema is not mandatory, but optionally you can provide a JSon schema).

![broken image](images/Webhook_2.jpg)

![broken image](images/Webhook_3.jpg)

Select an action to be executed in combination with your trigger, in this case, the action selected is ‘HTTP Request’ that allows a flow to perform an http action on a REST endpoint.

![broken image](images/Webhook_4.jpg)

Complete information in mandatory fields, and optionally include information in the rest of fields.

Authentication type: Optionally the endpoint can be secured, using one of the following authentication methods

- _None_ -> No authentication needed

- _Basic_ -> An Username and a Password needs to be specified

- _Bearer_ -> Token endpoint, client (id and secret) and scope must be provided

Method: This action could be used for example to POST or DELETE to an endpoint, in order to create, update or delete a REST resource.
It can also be used to GET HTTP request method to retrieve data to pass to the next action.

Url: Endpoint to be called

Content Type: Used to indicate the media type of the resource

Content: Used to provide the Json schema
 

![broken image](images/Webhook_5.jpg)

In the ‘Overview’ section the user will see a summary of the configuration during the creation process. Also, an Extra Data will be automatically generated after saving a flow. The system will generate 2 URI's: the first one, 'Address' is the URI to which the data needs to be pushed by the external application. The second one, 'Metadata Address' provides an endpoint that returns the metadata in Swagger / OpenAPI format. This metadata address can be provided for example when using the Logic App's Http + Swagger connector.

![broken image](images/Webhook_6.jpg)

In the ‘History’ section the flow will register every execution and the related data.

![broken image](images/Webhook_7.jpg)

Remember to add a name to your Flow and Save it.