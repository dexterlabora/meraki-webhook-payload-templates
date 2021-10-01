# meraki-webhook-payload-templates

This is a collection of Meraki Webhook Payload Templates. 

Each folder consists of one integration which includes a couple of key files.

- /integration/

    - `readme.md`
        Description of the template, links to the related API service and screenshots of results.

    - `body.liquid`
        The body template file

    - `headers.liquid` 
        The headers template file


## Alert Types

The template files will leverage the Liquid language and render the final results based on the `alertType` that is sent via the webhook.

- `alertTypes.json`   
    Included sample of alert types and the variables that are available to the template. 



# Using Liquid Templates

The Liquid template language provides a number of options to present and transform the data. For more information and helpful tools, checkout these resources.

[Liquid Docs](https://shopify.github.io/liquid/) 


[Liquid for Designers](https://github.com/Shopify/liquid/wiki/Liquid-for-Designers) 


# Meraki Liquid Filters 


In addition to the standard Liquid filters, Meraki has provided a few extras for helpful tasks. Use these by appending a pipe and the name of the filter 



`alertData | jsonify`



## jsonify 


Converts a JSON object into a JSON string.

Hint, if you see [Object object] try using this



`alertData | jsonify`

--- Returns ---

```
{"portNum":3,"description":"Gigabit link negotiation failed","status":"10 Gbps","prevStatus":"100 Gbps","portDesc":"Corp Access"}
```


## json_markdown 


Converts a JSON object into a markdown friendly view of the keys and values and avoids clashing when nested in other JSON.



`alertData | json_markdown`

--- Returns ---
```
portNum: 3
description: Gigabit link negotiation failed
status: 10 Gbps
prevStatus: 100 Gbps
portDesc: Corp Access
```

# REST API 

Using the Dashboard API, the templates can be uploaded, managed, tested and applied. 

## Payload Templates 

<table>
  <tr>
   <td>get
   </td>
   <td><strong>/networks/{networkId}/webhooks/payloadTemplates</strong>
   </td>
   <td>getNetworkWebhooksPayloadTemplates
   </td>
  </tr>
  <tr>
   <td>post
   </td>
   <td><strong>/networks/{networkId}/webhooks/payloadTemplates</strong>
   </td>
   <td>createNetworkWebhooksPayloadTemplate
   </td>
  </tr>
  <tr>
   <td>get
   </td>
   <td><strong>/networks/{networkId}/webhooks/payloadTemplates/{payloadTemplateId}</strong>
   </td>
   <td>getNetworkWebhooksPayloadTemplate
   </td>
  </tr>
  <tr>
   <td>delete
   </td>
   <td><strong>/networks/{networkId}/webhooks/payloadTemplates/{payloadTemplateId}</strong>
   </td>
   <td>deleteNetworkWebhooksPayloadTemplate
   </td>
  </tr>
  <tr>
   <td>put
   </td>
   <td><strong>/networks/{networkId}/webhooks/payloadTemplates/{payloadTemplateId}</strong>
   </td>
   <td>updateNetworkWebhooksPayloadTemplate
   </td>
  </tr>
</table>

## Webhook Tests 

<table>
  <tr>
   <td>post
   </td>
   <td><strong>/networks/{networkId}/webhooks/webhookTests</strong>
   </td>
   <td>createNetworkWebhooksWebhookTest
   </td>
  </tr>
  <tr>
   <td>get
   </td>
   <td><strong>/networks/{networkId}/webhooks/webhookTests/{webhookTestId}</strong>
   </td>
   <td>getNetworkWebhooksWebhookTest
   </td>
  </tr>
</table>

## Webhook HTTP Servers 

<table>
  <tr>
   <td>get
   </td>
   <td><strong>/networks/{networkId}/webhooks/httpServers</strong>
   </td>
   <td>getNetworkWebhooksHttpServers
   </td>
  </tr>
  <tr>
   <td>post
   </td>
   <td><strong>/networks/{networkId}/webhooks/httpServers</strong>
   </td>
   <td>createNetworkWebhooksHttpServer
   </td>
  </tr>
  <tr>
   <td>get
   </td>
   <td><strong>/networks/{networkId}/webhooks/httpServers/{httpServerId}</strong>
   </td>
   <td>getNetworkWebhooksHttpServer
   </td>
  </tr>
  <tr>
   <td>put
   </td>
   <td><strong>/networks/{networkId}/webhooks/httpServers/{httpServerId}</strong>
   </td>
   <td>updateNetworkWebhooksHttpServer
   </td>
  </tr>
  <tr>
   <td>delete
   </td>
   <td><strong>/networks/{networkId}/webhooks/httpServers/{httpServerId}</strong>
   </td>
   <td>deleteNetworkWebhooksHttpServer
   </td>
  </tr>
</table>

# Utilities 

## [Template Builder (beta)](https://webhook-builder-vpfmunhy6a-uc.a.run.app/) 
    

