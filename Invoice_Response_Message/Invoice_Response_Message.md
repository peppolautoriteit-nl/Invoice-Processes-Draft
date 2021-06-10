# Overview of the proposed solution

## Scope & principles

The purpose of the Invoice Response is to communicate the ‘business status’ of an invoice between a Buyer and a Supplier via their respective Access Points in a standardised way.
The scope of the term ‘business status’ is defined as the result of the business rules executed at the Buyer side. Some of these business rules validations may be outsourced to the Buyer Access Point.

The Invoice Response is NOT used to communicate the ‘transport status’ of an invoice between a Buyer AP and a Supplier AP. For ‘transport status’ a Message Level Response is used.

The scope of the Invoice Response is:

1. The Invoice Response Message uses PEPPOL BIS Invoice Response 3.1 (https://docs.peppol.eu/poacc/upgrade-3/profiles/63-invoiceresponse/) and the Dutch implementation is fully compatible with the PEPPOL implementation. The technical UBL message used is ApplicationResponse. See PEPPOL documentation for message specifications
2. The Invoice Response Message is sent by the Buyer AP to the Supplier AP conform standard PEPPOL exchange mechanisms (including use of SML and SMP) and always refers to a message send by the Supplier AP. 
3. The actual invoice status lives in the Buyer ERP system and should go to the Seller ERP system. Buyer AP and Seller AP choose their own channel and format to exchange the invoice status to these systems. However, the business meaning of this invoice status remains the same through the entire chain (e.g. the definition of the status ‘Accepted’ is the same in the entire chain).
4. An invoice may result in multiple invoice messages.

## Process

The process for the exchange of the Invoice Response is shown in picture 1.

1. Supplier sends an invoice to the Supplier AP (via his own channels) addressed to the PEPPOL identifier of the Buyer.
2. Supplier AP resolves the PEPPOL identifier of the Buyer to the Buyer AP 
3. Supplier AP sends the invoice to the Buyer AP via PEPPOL mechanism (including signed MDN process).
4. Buyer AP validates the invoice according to the PEPPOL Validation Artefacts and (if processable) delivers the invoice to the Buyer (via his own channels)
5. Buyer processes the Invoice. As a result of the processing the invoice gets a specific status. The Buyer buyer software has it’s own mechanism for processing invoices and determining invoice states.
6. Buyer sends the Invoice status to the Buyer AP (via his own channels) addressed to the PEPPOL identifier of the Supplier, provided as endpointID.
7. Buyer AP resolves the PEPPOL identifier of the Supplier to the Supplier AP
8. Buyer AP sends the Invoice Response Message to the Supplier AP as ApplicationResponse message.
9. Supplier AP forwards the Invoice status to the Supplier (via his own channels).

![Overview](Overview.png)

## Supported business states

The PEPPOL BIS for Invoice Response supports a number of optional and mandatory status codes. In order to have a proper understanding of the status of invoices in the process there is a strict order in which the status codes can occur. This order is shown in the table below. Note that individual ERP vendors may have different process flow implementations of if and how the invoice status is generated. The gray states are optional in BIS3 Invoice Response profile.

| Status Code | UNECE name | BIS usage | Clarification on requirements | Mandatory | Final |
|--|----|----------|--|--|--|
| AB | Message acknowledgement | Status is used when Buyer has received a readable invoice message that can be understood and submitted for processing by the Buyer. | NO | YES | NO |
| IP | In Process | Status is used when the processing of the Invoice has started in Buyers system. | NO | NO | NO |
| UQ | Under query | Status is used when Buyer will not proceed to accept the Invoice without receiving additional information from the Seller. | YES | NO | NO |
| CA | Conditionally accepted | Status is used when Buyer is accepting the Invoice under conditions stated in ‘Status Reason’ and proceed to pay accordingly unless disputed by Seller. | YES | NO | NO |
| RE | Rejected | Status is used only when the Buyer will not process the referenced Invoice any further.Buyer is rejecting this invoice but not necessarily the commercial transaction. Although it can be used also for rejection for commercial reasons (invoice not corresponding to delivery). | YES | YES | YES |
| AP | Accepted | Status is used only when the Buyer has given a final approval of the invoice and the next step is payment | NO | YES | YES |
| PD | Fully Paid | Status is used only when the Buyer has initiated the payment of the invoice. | NO | NO | NO |
