# Briefing Invoice Response implementation in Dutch Peppol community

The Netherlands Peppol Authority (NPA) will make the implementation and use
of the Invoice Response part of the Dutch Peppol scheme in Q3 2021. 
This document describes the high-level scope and strategic implications of the
implementation of the Invoice Response message and formulates questions
to the NPA Technical Working Group.

*Note: for the remainder of the text the word ‘invoice’ also includes the concept ‘credit note’.*

## Summary of the proposal

This proposal describes the NPA initiative to roll-out the Peppol Message Level Response and Invoice Response Message in the Dutch Peppol Community. This proposal includes:

* The use of the Peppol BIS Invoice response 3.1
* Staged rollout starting Q3 2021
* Mandatory support for the Invoice Response message by sending and receiving serviceproviders.
* Optional support for the Invoice Response message by sending and receiving endusers.

See [Proposed Solution for Invoice Response Messages](../Invoice_Response_Message/Invoice_Response_Message.md)

## Relation to other status messages

This document is mainly about the Invoice Response Message. However, other status messages exists, and therefore the scope should be evaluated as part of the other status messages.

| Message Delivery Notification                                | Message Level Response | Invoice Response Message (Scope of this document) |
| ------------------------------------------------------------ | ---------------------- | ------------------------------------------------- |
| The message is sent to the sender of the message. For example: sender's signature incorrect: To indicate that a message does or does not meet the validation rules (XSD + Schematron). For example: XSD or Schematron validation error. |                        |                                                   |
|                                                              |                        |                                                   |
|                                                              |                        |                                                   |


| Message Delivery Notification                                 | Message Level Response                                       | Invoice Response Message (Scope of this document)            |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Status message about transport between C2 and C3.            | Status message about the technical correctness of the message between C2 and C3. | Status message about the processing of the message by C4.    |
| When: to indicate whether or not a message was received correctly. For example: signature sender incorrect. | When: To indicate that a message does or does not meet the validation rules in place (XSD + Schematron). Example: XSD or Schematron validation error. | When: To indicate that a message does or does not meet the recipient's business rules. For example: order number is missing. |
| Already in effect as part of the AS4 exchange as a synchronous response to the Invoice message. | Not yet implemented. Separate ApplicationResponse message type as per BIS3 MLR 3.0. | Not yet implemented. Separate ApplicationResponse message type according to BIS3 IRM 3.1 |

## Business rationale for supporting the Invoice Response message

In order to assess the feasibility and viability of the IR proposal, the following aspects are evaluated:

* **Collaborative domain**: yes, the initiative stimulates the interoperability of status messages between Access Points. The document does not intervene with the competitive domain, e.g. the mechanisms implemented by parties to generate or process an IRM.
* **Contribution to NPA objective**: the use of IRM will increase the relevance of the PEPPOL network for Access Points (goal 1), potentially leading to more AP members. In addition, the IRM will increase relevance for end-users, leading to increased number of PEPPOL Trading Entities (goal 2).
* **Value add for end-users**: End-users will receive feedback about their invoices in their ERP systems. They are better able to manage their invoicing process from their own ERP systems.
* **Functional value for participants**: Participants can offer an additional process to their customers for managing their ‘invoice resolution’ process in the ERP system rather than out-of-bound via email.
* **Implementation impact**: Participants need to support an additional document type (ApplicationResponse). All suppliers must now be registered in the SML/SMP.
* **Impact on the scheme**: Limited (existing PEPPOL message type). Governance policy must be added to mandate the use of the IRM. Rules must be added to govern the roles and responsibilities of the APs.
* **Dependency on other factors**: None.

## Proposed implementation path

The NPa proposes the following implementation path:

1. Start with the implementation of the Acknowledgement, Accepted, Rejected and optionally Paid.
2. Make the support for these states mandatory for PEPPOL Access Points.

## The question to the Technical Working Group is:

1. Assess the technical impact of supporting the mentioned mandatory Invoice States on the implementation
2. Describe how the Invoice Response Message is to be implemented by Dutch Access Points
3. Advise on a pragmatic technical proposal for a phased roll-out of the IRM in the Dutch market, with   as an end-result a mandatory implementation for both sending and receiving AP's. This proposal should at least contains: which statusses are supported for what actors.
4. Describe a workable process for the scenario where a Supplier uses different AP’s for sending and receiving
