
# SOAP-TOOLKIT Payment Request Examples
#### A repository of examples of XML payment & token requests used in the Payment Gateway (WF/CyberSource).


## Explanation of Variables 
#### These can be used as/within POSTMAN requests, but you must add the variables (enclosed in the {{ }} placeholders).

#### SOAP Envelope Security Header

```http
  <wsse:Username>{{MerchantID}}</wsse:Username>
  <wsse:Password Type="http://docs.oasis-open.org/wss/.../..#PasswordText">{{TransactionSecurityKey}}</wsse:Password>
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `{{MerchantID}}` | `string` | **Required**. The name of your Gateway (wfg_  ) |
| `{{TransactionSecurityKey}}`      | `string` | **Required**. The type of key used for SOAP messages |

#### SOAP BODY Message

```http
      <requestMessage xmlns="urn:schemas-cybersource-com:transaction-data-{{Version}}">
       <merchantID>{{MerchantID}}</merchantID>
      <merchantReferenceCode>{{MerchantReferenceCode}}</merchantReferenceCode>
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `{{Version}}` | `string` | **Required**. Choose the newest or at least the one that supports your gateway features |
| `{{MerchantID}}`      | `string` | **Required**. Use the same merchant Id of your gateway |
| `{{MerchantReferenceCode}}` | `string` | **Recommended**. The Gateway will generate but it is recommended that the merchant generate |


## Documentation

[Documentation (.pdf)](https://developer.cybersource.com/content/cybsdeveloper2021/amer/en/library/documentation/dev_guides/SOAP_Toolkits/SOAP_toolkits.pdf)

