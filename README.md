InterVision Amazon Connect Contact Center Setup
This repository provides all resources, configurations, and setup instructions necessary for building an Amazon Connect-based contact center tailored for InterVision. The setup includes integration with Lex bots, DynamoDB, and Lambda functions for a dynamic, efficient, and secure contact center.

Folder Structure
The repository is organized into the following folders:
ArchitectureDesign: Contains the architectural diagram illustrating the end-to-end setup for the contact center. The diagram shows the flow from an incoming call through to survey completion and entire customer experience 
Lex: Contains Lex bot configurations, including intents, slots, and prompts. These bots are set up to handle support for customer interactions.

Lambda: Houses AWS Lambda function scripts used for:

Dynamic prompt management for both English and Spanish.
Holiday management functions.
Survey management
Integration with Amazon Connect contact flows for real-time response.
DynamoDB: Holds configurations for DynamoDB tables:

Prompt Management: Stores language-based prompts.
Holiday Schedules: Maintains records for holiday operations.

Error Handling Modules: Designed for smooth customer experience in error situations for both language in english and french
Callback Queue Flow: Provides callback functionality for customers waiting in queues.
estimated functionality to let customer thier time in queue prior get connected
Users: Defines user profiles, initial setup details, and routing profiles. Contains encrypted passwords for the initial set of users.

ContactFlows: Includes predefined contact flows, such as:

Main inbound flows ( that has all the subflows)
SUB FLOW;
InterVision-TechnicalServiceSubFlow
InterVision-AccountGeneralInquirySubFlow.
InterVision-TechnicalServiceSpanishSubFlow
InterVision-AccountGeneralInquirySpanishSubFlow.
InterVision-AgentWhisperFlow
InterVision-Customerwhisperflows.
InterVision-CustomerQueueFlow
InterVision-DisconnectFlow
InterVision-TransferTOAgentFlow
InterVision-TransferToQueueFlow
InterVision-OutBoundWhisperFlow
InterVision-CustomerHoldFlow
InterVision-AgentHoldFlow
Module for out of hour Selfservice and voicemail handling


Key Implementation Components
enable set logging behaviour so every expirence within the contact centre can be capture in cloudwatch
Secure handling of customer data with PII redaction through contact lens enable in the set recording and analystic behaviour
Integration of Lex bots and Lambda for an intelligent IVR experience.
Modular contact flows for seamless call routing and response.
Queues and Routing Profiles
To enable smooth call routing, the following profiles and queues are created:

Queues:
Technical Services:( Disaster Recovery & Backup, Cloud Services, Servers & Storage, Cybersecurity, Infrastructure, and Tech Support).
Account & General Services: (Billing, General Inquiry, Sales, Helpdesk, Communication.)
Routing Profiles:
Profile 1: Helpdesk, Communication, General Inquiry.
Profile 2: Tech Support, Cybersecurity, Disaster Recovery & Backup.
Profile 3: Cloud Services, Servers & Storage, Infrastructure.
Profile 4: Sales, Account Billing.
Quick Connects
Quick Connects are set up for 4 users and linked to specific queues for immediate access, enabling efficient call handling and transfer between departments.

Implementation Phases
1. Design and Setup
Instance Setup: Amazon Connect instance configuration.
Hours of Operation (HOOPs): Mon - Fri 8:00am to 5pm and Sat from 8am-3pm  for Techical Services and 8am-5pm for Account & General Services
Prompt Management & Multilingual Support: Configured with DynamoDB and Lambda for English and Spanish responses.
Holiday Management: DynamoDB and Lambda used to dynamically handle holiday schedules.
2. Integration
Integrate Lex bots TO automate customer response.
Lambda functions are integrated to support dynamic IVR and handle prompt and holiday functions.
All prompts witin the contact centre is dynamically play from a dynamoDB table using a lambda function
4. Testing
Comprehensive testing of all contact flows, IVR, bots, and Lambda integrations.
5. Deployment
Go Live: Launch the contact center with monitoring for performance feedback.
Optimization: Periodic updates based on KPIs.
Key Performance Indicators (KPIs)
Average Handling Time (AHT): Measures the time agents take to resolve inquiries.
Call Abandonment Rate: Monitors calls dropped before reaching an agent.
Risk Management
Scalability: Lambda and Lex bots are configured to scale automatically during high call volumes.
Data Security: Encrypted passwords and regular security audits ensure compliance and data protection.
This repository serves as a comprehensive guide for setting up a fully functional and optimized Amazon Connect contact center for InterVision.

