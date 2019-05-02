# Extensions Kit Triggers
A Flow consists of a Trigger, an optional filter on the data contained in the Trigger event, and a sequence of one or more Actions.  
Below you will find a brief introduction of all the triggers that can be used when defining your flow and how to used each one in a flow.
# Scheduled Events

## Description
The *Scheduled Event* trigger allows a flow to be initiated on a regular basis based on a user configured schedule.

## Usage
*Here you will find a step by step tutorial on how to create a flow sample with a scheduled event trigger*
* [How to create a flow with a Scheduled Event trigger](../ScheduledEvent.md)



# Webhook

## Description
The *Webhook* trigger allows a HTTP request to initiate a Flow defined in the Unit4 Extensions Kit (U4EK). In a typical scenario this trigger would be utilized to allow a workflow defined somewhere else to continue execution in a U4EK Flow.

## Usage
*Here you will find a step by step tutorial on how to create a flow sample with a webhook trigger*
* [How to create a flow with a Webhook trigger](../Webhook.md)



# Message Hub Events

## Description
The *Message Hub Event* trigger allows a flow to be initiated when a particular event is published on the Unit4 Message Hub by a specified source system. The triggering event on the MessageHub can be an generic event type, or an Enterprise document.

## Usage
*Here you will find a step by step tutorial on how to create a flow sample with a message hub event trigger*
* [How to create a flow with a Message Hub Event trigger](../MessageHubEvent.md)