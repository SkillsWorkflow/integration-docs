# Webhooks on Skills Workflow integration API

On Skills Workflow Integration API webhooks are setup **by tenant**.

Webhooks must be configured by the Skills Workflow team.

The following information must be provided.

* URL
* Secret

## HTTP Request

Skills Workflow API will make an HTTP POST request to the specified endpoint with an *application/json* payload containing a description of the event that triggered the webhook.

The request is always performed via HTTPS and will include a header (X-Webhook-Secret) containing the secret specified when the webhook was configured.

### Request
```
POST /skillsevent HTTP/1.1
Host: webhook.example.com
Content-Type: application/json
X-Webhook-Secret: SOME_SECRET

{
    "action": "created",
    "document": {
        "type": "SkillsWorkflow.Job",
        "id": "32a8c937-2c65-463d-a292-e4c4e13ed263",
        "url": "https://integration-api-we.skillsworkflow.com/api/jobs/32a8c937-2c65-463d-a292-e4c4e13ed263"
    }
} 
```

### Payload

```javascript
{
    "action": "created",
    "document": {
        "type": "SkillsWorkflow.Job",
        "id": "32a8c937-2c65-463d-a292-e4c4e13ed263",
        "url": "https://integration-api-we.skillsworkflow.com/api/jobs/32a8c937-2c65-463d-a292-e4c4e13ed263"
    }
}
```

| Field                 | Description                                        
| --------------        | -------------------------------------------------- 
| action                | What type of action triggered this event           
| document              | Document on which the action was performed    

#### Action values

| Action                    | Description                                        
| --------------            | -------------------------------------------------- 
| created                   | The document was created
| updated                   | The document was updated
     

#### Document fields

| Field                 | Description                                        
| --------------        | -------------------------------------------------- 
| type                  | Type of the document (eg. Job, Project, etc)
| id                    | The document unique identifier
| url                   | The URL of the document on the API. You can make a GET request to this URL to read the document

##### Type values

* SkillsWorkflow.Job
* SkillsWorkflow.Project