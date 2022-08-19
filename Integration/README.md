## Integration
---
###  [#1 Azure Service Bus CheatSheet](./1.AzureSeviceBusCheatSheet.png)

<a href="https://github.com/chenjd/Microsoft-Azure-Cloud-CheatSheets/blob/main/Integration/1.AzureSeviceBusCheatSheet.png"><img src="https://github.com/chenjd/Microsoft-Azure-Cloud-CheatSheets/blob/main/Integration/1.AzureSeviceBusCheatSheet.png"  height="256px" align="right"></a>


#### What’s Azure Service Bus?
Azure Service Bus is a fully managed enterprise message broker with message queues and publish-subscribe topics

Service Bus queues service is one of the message queue solutions in Azure, and the other is Azure Storage queues.

[Ref - Discover Azure message queues](https://docs.microsoft.com/en-nz/learn/modules/discover-azure-message-queue/1-introduction?WT.mc_id=DT-MVP-5001664)

#### Common messagin scenarios
- **Messaging**: Transfer business data.
- **Decouple applications**: Improve reliability and scalability of applications and services. Client and service don't have to be online at the same time.
- **Topics and subscriptions**: Enable 1:n relationships between publishers and subscribers.
- **Message sessions**: Implement workflows that require message ordering (FIFO) or message deferral.
  
[Ref - Azure Service Bus Overview](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview?WT.mc_id=DT-MVP-5001664#overview)

#### Service Bus tiers
- Baisc
- Standard 
  - Message size up to 256 KB
  - Pay-as-you-go pricing
  - Dev/Test environments or low throughput.
- Premium
  - Message size up to 1 MB
  - Fixed pricing
  - Production environments or high throughput.
  - Only Premium tier Service Bus namespace supports event integration. (Event Grid)

[Ref - Service Bus Premium and Standard messaging tiers](https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-premium-messaging?WT.mc_id=DT-MVP-5001664)

[Ref - Azure Service Bus to Event Grid integration overview](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-to-event-grid-integration-concept?tabs=event-grid-event-schema&WT.mc_id=DT-MVP-5001664)


#### Entities
- Queues
  - Queues offer First In, First Out (FIFO) message delivery to one or more competing consumers. (Enable Message sessions)
  - Only one message consumer receives and processes each message.
  - Messages are stored durably in the queue, so the senders and receivers don't have to send and receive messages at the same time.
- Topics and Subscriptions
  - In contrast to queues, topics and subscriptions provide a one-to-many form of communication in a publish and subscribe pattern.
  - Each published message is made available to each subscription registered with the topic.
  - A topic subscription resembles a virtual queue that receives copies of the messages that are sent to the topic.
  
[Ref - Service Bus queues, topics, and subscriptions](https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-queues-topics-subscriptions?WT.mc_id=DT-MVP-5001664)

#### Architecture Example
- Service Bus has two delivery modes, pull or push. 
In the pull model, the receiver continuously polls for new messages. Polling can be inefficient.
In the push model, Service Bus sends an event through Event Grid when there are new messages. The receiver subscribes to the event. 
- When creating a Logic App to consume Service Bus messages, it is recommended to use the push model with Event Grid integration. It's usually more cost-effective because the Logic App doesn't need to poll the Service Bus.

[Ref - Enterprise integration using message broker and events](https://docs.microsoft.com/azure/architecture/reference-architectures/enterprise-integration/queues-events?WT.mc_id=DT-MVP-5001664)
