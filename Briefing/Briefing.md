# Briefing Invoice Response implementation in Dutch Peppol community

The Netherlands Peppol Authority (NPA) will make the implementation and use
of the Invoice Response part of the Dutch Peppol scheme in Q3 2021. 
This document describes the high-level scope and strategic implications of the
implementation of the Invoice Response message and formulates questions
to the NPA Technical Working Group.

*Note: for the remainder of the text the word ‘invoice’ also includes the concept ‘credit note’.*

## Summary of the proposal

This proposal describes the NPA initiative to roll-out the Peppol Invoice Response message in the Dutch Peppol Community. This proposal includes:

* The use of the Peppol BIS Invoice response 3.1
* Staged rollout starting Q3 2021
* Mandatory support for the Invoice Response message by sending and receiving serviceproviders.
* Optional support for the Invoice Response message by sending and receiving endusers.
* An investigation by the technical workgroup of the NPA assessing the technical impact of the support for Invoice Respones.
* An advise in the form of a document on how to correctly implement the Invoice Response.
* The endresult of the advise can be found here: [Implementation Peppol invoice to payment process](../Invoice_to_Payment_Process/Invoice_to_Payment_Process.md)

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

* **Collaborative domain**: yes, the initiative stimulates the interoperability of status messages between Serviceproviders. The document does not intervene with the competitive domain, e.g. the mechanisms implemented by parties to generate or process an Invoice Response.
* **Contribution to NPA objective**: The adoption of the Invoice Response message by Serviceproviders (and software vendors) will increase the relevance of the Peppol network for Endusers, leading to increased number of Peppol Endusers (goal 1).
* **Value add for Endusers**: Endusers will receive feedback about their invoices in their ERP systems. They are better able to manage their invoicing process from their own ERP systems.
* **Functional value for Serviceproviders**: Serviceproviders can offer an additional process to their customers for managing their ‘invoice resolution’ process in the ERP system rather than out-of-bound via email.
* **Implementation impact**: Serviceproviders need to support an additional document type (ApplicationResponse). Suppliers must be registered in the SML/SMP in order to receive the Invoice Response.
* **Impact on the scheme**: Limited (existing Peppol message type). Governance policy must be added to mandate the use of the Invoice Response. Rules must be added to govern the roles and responsibilities of the Serviceproviders.
* **Dependency on other factors**: The implementation of invoice status feedback within ERP systems and the communication of this feedback from the ERP system to Serviceproviders might take a long time for ERP vendors that are not within the Peppol community. A real adoption of the functionality might therefor take a long time.

## Proposed implementation path

The NPA proposes the following implementation path:

1. Phase 1: implementation of the Invoice Response states "Message acknowledgement", "Rejected", "Accepted"
2. Make the support of Phase 1 states mandatory for Serviceproviders.
3. Phase 2: implementation of the Invoice Response states "In Process", "Under query", "Conditionally accepted", "Partially Paid", "Fully Paid"
4. Make the support of Phase 2 states mandatory for Serviceproviders.

## The question to the Technical Working Group is:

1. Assess the technical impact of supporting the mentioned mandatory Invoice States
2. Describe how the Invoice Response message is to be implemented by Dutch Serviceproviders
3. Advise on a pragmatic technical proposal for a phased roll-out of the Invoice Response in the Dutch market, with the end-result being a mandatory implementation for both sending and receiving Serviceproviders. This proposal should at least contain: which statusses are supported for which actors.
4. Describe a workable process for the scenario where a Supplier uses different Serviceproviders for sending and receiving.
