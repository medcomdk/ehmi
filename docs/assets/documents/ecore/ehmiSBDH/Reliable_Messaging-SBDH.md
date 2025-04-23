# Reliable Messaging using ehmiSBDH-envelope

**Table of contents**
* [1 Different Reliable Messaging scenarios using ehmiSBDH-envelope](#1-different-reliable-messaging-scenarios-using-vansenvelope)
    * [1.1 Scenario #1 - Normally successful unsolicited ehmiSBDH-envelope or request ehmiSBDH-envelope flow with ehmiSBDH-envelopeAcknowledgement request ](#11-scenario-1---normally-successful-unsolicited-vansenvelope-or-request-vansenvelope-flow-with-vansenvelopeacknowledgement-request)
    * [1.2 Scenario #2 - Duplicate of an unchanged ehmiSBDH-envelope with a positive ehmiSBDH-envelopeAcknowledgement request ](#12-scenario-2---duplicate-of-an-unchanged-vansenvelope-with-a-positive-vansenvelopeacknowledgement-request)
    * [1.3 Scenario #3 - (Re) Sending Unchanged ehmiSBDH-envelope ](#13-scenario-3---re-sending-unchanged-vansenvelope)
    * [1.4 Scenario #4 - ehmiSBDH-envelope is sent normally, but ehmiSBDH-envelopeAcknowledgement is lost along the way](#14-scenario-4---vansenvelope-is-sent-normally-but-vansenvelopeacknowledgement-is-lost-along-the-way)
    * [1.5 Scenario #5 - (Re-) Sending Modified Message ](#15-scenario-5---re--sending-modified-message)
* [2 VansEnvelope Reliable Messaging Elements](#2-vansenvelope-reliable-messaging-elements)
    * [2.2 VansEnvelope Reliable Messaging Message Elements](#22-vansenvelope-reliable-messaging-message-elements)
    * [2.3 VansEnvelope ehmiSBDH-envelopeAcknowledgement Reliable Messaging Elements](#23-vansenvelope-vansenvelopeacknowledgement-reliable-messaging-elements)
<br><br>




Reliable Messaging in ehmiSBDH-envelope follows the principles laid out in <a href="https://medcomdk.github.io/MedCom-FHIR-Communication/assets/documents/020_Governance-for-Reliable-Messaging-in-general.html" target="_blank"> Reliable Messaging in general (opens on a new page)</a>

The Reliable Messaging Model and how the flow is laid out using ehmiSBDH-envelope is shown in <a href="#Fig1">Figure 1</a>. 

<figure style="margin-left: 0px; margin-right: 0px; width: 100%;">
<a href="https://ehmi.dk/assets/images/reliable-messaging-ehmiSBDH" target="_blank"> <img src="https://ehmi.dk/assets/images/reliable-messaging-ehmiSBDH.png" alt="reliable messaging principle" style="width:auto; margin-left:0px; margin-right:0px;" id="Fig1"></a>
<figcaption text-align="left"><b>Figure 1: Reliable Messaging - ehmiSBDH-envelope </b></figcaption>
</figure>
<br>

When Reliable Messaging is implemented, the Receiver **SHALL** check the incoming StandardBusinessDocumentHeader/DocumentIdentification/InstanceIdentifier (hereafter EnvelopeIdentifier) and the StandardBusinessDocumentHeader/BusinessScope/Scope/Type[MESSAGEIDENTIFIER] (hereafter MessageIdentifier) against a cache of previously received ehmiSBDH-envelopes. The correct action to take depends on what is received:

| Case                                                            | Description                |
|:----------------------------------------------------------------|:---------------------------|
| Both EnvelopeIdentifier and MessageIdentifier have not been received       | This is the normal case, and the message **SHALL** be processed            |
| Both EnvelopeIdentifier and MessageIdentifier have already been received   | The original ehmiSBDH-envelope server may either reprocess the message, or reject the message|
| MessageIdentifier has already been received, but EnvelopeIdentifier is new | The original ehmiSBDH-envelopeAcknowledgement has been lost (failed to return to the request issuer) and thus the previously received Message in a ehmiSBDH-envelope has been resubmitted with a new EnvelopeIdentifier for processing again. The original content of the ehmiSBDH-envelopeAcknowledgement **SHALL** be resent though with new identifier and timestamp|
| The EnvelopeIdentifier has already been received, but the MessageIdentifier is new | This is an error - EnvelopeIdentifier values **SHALL** never be reused. Receiver **MAY** return a Negative ehmiSBDH-envelopeAcknowledgement|

## 1 Different Reliable Messaging scenarios using ehmiSBDH-envelope

This section provides a description of the different types of Reliable Messaging scenarios.

- Scenario #1 - Normally successful unsolicited  ehmiSBDH-envelope or request message flow with ehmiSBDH-envelopeAcknowledgement request
- Scenario #2 - Duplicate of an unchanged ehmiSBDH-envelope with a positive ehmiSBDH-envelopeAcknowledgement request
- Scenario #3 - (Re-)Sending Unchanged ehmiSBDH-envelope
- Scenario #4 - ehmiSBDH-envelope is sent normally, ehmiSBDH-envelopeAcknowledgement is lost along the way
- Scenario #5 - (Re-)Sending Modified ehmiSBDH-envelope

### 1.1 Scenario #1 - Normally successful unsolicited ehmiSBDH-envelope or request ehmiSBDH-envelope flow with ehmiSBDH-envelopeAcknowledgement request 

An unsolicited  ehmiSBDH-envelope is sent with a new request for a positive ehmiSBDH-envelopeAcknowledgement from the Sending System to a Receiving System.

The Receiving System **SHALL** always send a positive ehmiSBDH-envelopeAcknowledgement to the Sending System.

### 1.2 Scenario #2 - Duplicate of an unchanged ehmiSBDH-envelope with a positive ehmiSBDH-envelopeAcknowledgement request 

Duplication of an unchanged ehmiSBDH-envelope can be done in one of the following ways:

- An error may have occurred in the flow from the Sending System to the Receiving System with subsequent duplication of a ehmiSBDH-envelope in scenario 1.
- The Sending System may inadvertently send a duplicate of ehmiSBDH-envelope

The ehmiSBDH-envelopes are completely identical and as a consequence, the ehmiSBDH-envelope with request for positive ehmiSBDH-envelopeAcknowledgement arrives at the Receiving System more than once.

The Receiving System **SHALL** ignore the contents of the duplicate instances of the ehmiSBDH-envelope but **SHALL** acknowledge a duplicate ehmiSBDH-envelope in the same way as the original ehmiSBDH-envelope.

A positive ehmiSBDH-envelopeAcknowledgement may not be sent first and then a negative ehmiSBDH-envelopeAcknowledgement or vice versa.

The Receiving System **SHALL** never display several instances of a ehmiSBDH-envelope in a ehmiSBDH-envelope overview, but **SHALL** log in a system log that reception of a duplicate ehmiSBDH-envelope has taken place.

If the Sending System of the ehmiSBDH-envelope has received ehmiSBDH-envelopeAcknowledgement already after the Receiving System's ehmiSBDH-envelopeAcknowledgement of a ehmiSBDH-envelope's first instance, the Sending System **SHALL** similarly ignore the duplicate instances of the ehmiSBDH-envelopeAcknowledgement.

The Sending System **SHALL** never display multiple instances of the same ehmiSBDH-envelopeAcknowledgement in a ehmiSBDH-envelope summary but **SHALL** log in a system log that ehmiSBDH-envelopeAcknowledgement of a duplicate has taken place.

### 1.3 Scenario #3 - (Re) Sending Unchanged ehmiSBDH-envelope 

Correct retransmission of message A.

The Sending System **SHALL** form a new ehmiSBDH-envelope with a new ID and time of dispatch.

Since there has been no change in the Message content section, the rest of the ehmiSBDH-envelope **SHALL** remain identical.

The ehmiSBDH-envelope **SHALL** be sent and ehmiSBDH-envelopeAcknowledged as a completely new ehmiSBDH-envelope according to Scenario #1.

Re-dispatches **SHALL** always be done manually and **SHOULD** be in accordance with the normal response time for the specific ehmiSBDH-envelope flow.

### 1.4 Scenario #4 - ehmiSBDH-envelope is sent normally, but ehmiSBDH-envelopeAcknowledgement is lost along the way 

Like in Scenario #1, but where ehmiSBDH-envelopeAcknowledgement is lost along the way from the Sending System to the Receiving System.

The shipping pattern is like Scenario #3.

### 1.5 Scenario #5 - (Re-) Sending Modified Message 

If the content of the Message content part is changed, the ehmiSBDH-envelope is considered a completely new ehmiSBDH-envelope and consequently change of both EnvelopeIdentifier, MessageIdentifier and timestamp **SHALL** be made.

Re-Sending calls  **SHALL** always be done manually.

