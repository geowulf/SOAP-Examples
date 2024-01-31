
# Level 2 and 3 Interchange Discounts

The following **REQUIRED** fields must be included in your transaction in order to QUALIFY for interchange discounts. They will only be assessed AFTER capture request not before.




#### Level 2 fields

```http
  Tax Information Required Fields
```
| Data Field | Format   |  Example  | Notes                                       |
| :--------  | :------- | :---------| :------------------------------------------ | 
| `alternate_tax_amount_indicator` | numeric| 0.00| Must not be all zeros if a tax  exists, last two implied decimals                                          |
| `invoiceHeader_userPO` | alphanumeric| ex. POxxxx| Must not be blank/spaces or all zeros|
| `invoiceHeader_vatInvoiceReferenceNumber` | alphanumeric| ex. INVxxx| Must not be blank/spaces or all zeros|
| `item_#_invoiceNumber` | alphanumeric| ex. INVxxx| Must not be blank/spaces or all zeros|
| `item_#_nationalTax` | numeric| 0.00| Must not be all zeros if a tax  exists, last two implied decimals|
| `item_#_unitPrice` | numeric| 0.00| Must not be all zeros if a tax  exists, last two implied decimals          |
| `merchantID` | alphanumeric| ex. wfgTestMerchant| Must not be blank/spaces or all zeros|
| `merchantReferenceCode` | alphanumeric| ex. MRC65078946| Must not be blank/spaces or all zeros|
| `otherTax_alternateIndicatorntID` | alphanumeric| ex. NT65078946| Must not be blank/spaces or all zeros|
| `otherTax_alternateIndicator` | alphanumeric| ex.ALT65078946| Must not be blank/spaces or all zeros|
| `otherTax_alternateTaxAmount` |numeric| 0.00| Must not be all zeros if a tax  exists, last two implied decimals|
| `purchaseTotals_currency` |numeric| 0.00| Must not be all zeros purchase total, last two implied decimals |
| `purchaseTotals_discountAmount` |numeric| 0.00| Must not be all zeros if a discount exists, last two implied decimals|

#### Level 3 fields

```http
  Minimum Required Fields
```
| Data Field | Format   |  Example  | Notes                                       |
| :--------  | :------- | :---------| :------------------------------------------ | 
| `purchaseTotals_dutyAmount`| numeric| 0.00| Must not be all zeros if a duty amount exists|
| `invoiceHeader_userPO`| alphanumeric| POxxxx|  Must not be blank/spaces or all zeros|
| `purchaseTotals_freightAmount`| numeric| 0.00| Must not be blank but zeros okay|
| `purchaseTotals_discountAmount`| numeric| 0.00| Must not be all zeros if a discount amount exists and last two implied decimal|
| `item_0_unitPrice`| numeric| 1 or 1.00| Must not be blank/spaces or all zeros|
| `item_0_discountAmount`| numeric| 0.00| Must not be all zeros if a discount amount exists and last two implied decimal|
| `item_0_productName`| alphanumeric| ex. Book| Must not be blank/spaces or all zeros|
| `item_0_taxAmount`| numeric| 0.00| Must not be blank but zeros okay|
| `item_0_unitOfMeasure`| alphanumeric| ex. Box, ea, pr| Must not be blank/spaces or all zeros|
| `item_0_commodityCode`|alphanumeric| ex. 65078946| Must not be blank/spaces or all zeros|
| `item_0_productCode`| numeric| ex. PPR458| Must not be blank/spaces or all zeros|
| `item_0_quantity`| numeric| 1 or higher| The last for digits are implied decimal places|
| `item_0_totalAmount`| numeric| ex. $50.00| Must not be blank/spaces or all zeros|


#### Interchange Analysis

During integration, it is recommended that you ask your Relationship Manager to perform an Interchange Analysis to see what kind of interchange discounts you may be eligible to receive.


## Documentation

[Documentation](https://docs.cybersource.com/content/dam/new-documentation/documentation/en/level-2-3/fdiglobal/so/level-2-3-so-fdiglobal.pdf)

### Introduction to Level II and Level III Processing (for WFPG)

This information mainly focuses on the settings within the Virtual Terminal in the WFPG, but the required fields would be the same regardless of the application type.

- Level II and Level III is for both card present and card not present transactions.

- Processing Platform - FD Nashville Global

- AMEX & Discover does not allow Level III

- If Level III is passed on an Amex, it will give you Reason Code 102 – ‘The field is invalid: Invalid card type for Level III data’, this will still dial out to *American Express* and obtain an authorization.

- If Level III is passed on a Discover card, the transaction will decline and give Reason Code 102 – ‘The field is invalid: Invalid card type for Level III data’. The transaction is still authorized and the merchant should process a reversal.

- When coding, API merchants must include field “ccCaptureService_purchasingLevel”. The actual API field name may differ based on application method.

- Subscriptions – On-Demand, Recurring and Installments – discussed further in this document

- Only U.S. issued Corporate and Purchase cards can qualify at both Level 2 & Level 3 and large ticket.

- Mastercard fleet at fuel cannot receive Level III

- U.S. issued Business cards can only get Level II

Before you can use Level II processing with *American Express*, you must contact *American Express* and obtain approval to process Level II transactions. 

Level III processing includes line-item data for each transaction. 

This document provides guidelines that indicate which fields are required to obtain the best interchange rates. These guidelines are based on industry information available at the time of publication. Cybersource recommends that you contact your acquirer for the most current information requirements, as these requirements can change at any time.


