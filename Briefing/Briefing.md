# Briefing Invoice Response implementation in Dutch AP community

The Netherlands Peppol Authority (NPa) will make the implementation and use
of the Invoice Response part of the Dutch PEPPOL scheme in Q3 2021. This
document describes the high-level scope and strategic implications of the
implementation of the Invoice Response message and formulates the questions
to the NPA Technical Working Group.

*Note: for the remainder of the text the word ‘invoice’ also includes the concept ‘credit note’.*

## Summary of the proposal

This proposal describes the NPa initiative to roll-out the PEPPOL Invoice Response Message in the Dutch PEPPOL Community. This proposal includes:

* The use of the PEPPOL BIS Invoice response 3.1
* Staged rollout starting Q3 2021, starting with a subset of status messages
* Mandatory document support for sending and receiving AP’s for the InvoiceResponse message.

See [Proposed Solution for Invoice Response Messages](../Invoice_Response_Message/Invoice_Response_Message.md)

## Business rationale for supporting the Invoice Response Message

In order to assess the feasibility and viability of the IRM proposal, the following aspects are evaluated:

* **Collaborative domain**: yes, the initiative stimulates the interoperability of status messages between Access Points.
* **Contribution to NPA objective**: the use of IRM will increase the relevance of the PEPPOL network for Access Points (goal 1), potentially leading to more AP members. In addition, the IRM will increase relevance for end-users, leading to increased number of PEPPOL Trading Entities (goal 2).
* **Value add for end-users**: End-users will receive feedback about their invoices in their ERP systems. They are better able to manage their invoicing process from their own ERP systems.
* **Functional value for participants**: Participants can offer an additional process to their customers for managing their ‘invoice resolution’ process in the ERP system rather than out-of-bound via email.
* **Implementation impact**: Participants need to support an additional document type (ApplicationResponse). All suppliers must now be registered in the SML/SMP.
* **Impact on the scheme**: None (existing PEPPOL message type). Governance policy must be added to mandate the use of the IRM. Rules must be added to govern the roles and responsibilities of the APs.
* **Dependency on other factors**: None.


## Proposed implementation path

The NPa proposes the following implementation path:

1. Start with the implementation of the Acknowledgement, Accepted, Rejected and optionally Paid.
2. Make the support for these states mandatory for PEPPOL Access Points.

The question to the Technical Working Group is:
1. Assess the technical impact of supporting the mentioned mandatory Invoice States on the implementation
2. Describe a workable process for the scenario where a Supplier uses different AP’s for sending and receiving
