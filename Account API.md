# General

| Object | Path |
| - | - |
| [Site](#site) | `/account/site` |
| [Agent](#agent) | `/account/agents` | 
| [Group](#group) | `/account/groups` |
| [Ip Restriction](#ip-restriction) | `/account/ipRestrictions` |
| [Audit Log](#audit-log) | `/livechat/auditLogs` |              

## Site
  You need `Manage Site` permission to manage site.
  - `GET /api/v2/account/site/profile` -Get profile of a single site
  - `PUT /api/v2/account/site/profile` -Update profile of a site
  - `PUT /api/v2/account/site/cancel` -Cancel the site    

### Site Profile Json Format
  Site profile is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only | Mandatory | Description |
  | - | - | :-: | :-: | - | 
  | id | integer | yes | no | id of the site
  | siteName | string | no | yes | name of the site
  | contact.firstName | string | no | yes |first name of the contact
  | contact.lastName | string | no | yes |last name of the contact
  | contact.email | string | no | yes | email of the contact
  | contact.mobileNumber | string | no | yes |mobile number of the contact
  | company | string | no | yes | company the site belongs to
  | website | string | no | yes | website of the site
  | phoneNumber | string | no | no | phone number of the site
  | title | string | no | no | title of the site
  | faxNumber | string | no | no | fax number of the site
  | mailAddress | string | no | no | mail address of the site
  | city | string | no | no | city which the site is in
  | stateOrProvince | string | no | no | state or provice which the site is in
  | postalOrZipCode | string | no | no | postal or zip code of the site
  | country | string | no | no | country which the site's company belongs to 
  | companySize | string | no | no | staff number of the site's company
  | timeZone | string | no | no | time zone which the site's company belongs to 
  | datetimeFormat | string | no | no | datatime format which the site will display

### Get profile of a single site

  `GET /api/v2/account/site/profile`
    
  - Parameters    
    No parameters    
      
  - Response   
    Site Profile Object

#### Example
     
  Sample request:
     
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" https://apptest.platform.comm100.com/accountwebapi/api/v2/account/site/profile
```
    
  Sample response:
     
```json
{
    "id": 6000000, 
    "siteName": "comm100", 
    "contact.firstName": "test", 
    "contact.lastName": "comm100", 
    "contact.mobileNumber": "", 
    "company": "comm100", 
    "website": "www.comm100.com", 
    "phoneNumber": "123456", 
    "title": "", 
    "faxNumber": "", 
    "mailAddress": "", 
    "city": "", 
    "stateOrProvince": "", 
    "postalOrZipCode": "", 
    "country": "China", 
    "companySize": "101-180", 
    "timeZone": "71", 
    "datetimeFormat": "MM/dd/yyyy HH:mm:ss"
}
```
    
### Update profile of a site  

  `PUT /api/v2/account/site/profile`
    
  - Parameters    
    Site Profile Object    
      
  - Response    
    Site Profile Object

#### Example
     
  Sample request:
     
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" -X PUT -d "sitename=sitename&timezone=71"  https://apptest.platform.comm100.com/accountwebapi/api/v2/account/site/profile
```
    
  Sample response:
     
```json
{
    "id": 6000000,
    "siteName": "sitename",
    "contact.firstName": "test",
    "contact.lastName": "comm100",
    "contact.mobileNumber": "",
    "company": "comm100",
    "website": "www.comm100.com",
    "phoneNumber": "123456",
    "title": "",
    "faxNumber": "",
    "mailAddress": "",
    "city": "",
    "stateOrProvince": "",
    "postalOrZipCode": "",
    "country": "China",
    "companySize": "101-180",
    "timeZone": "71",
    "datetimeFormat": "MM/dd/yyyy HH:mm:ss"
}
```
    
### Cancel the site
 
  `PUT /api/v2/account/site/cancel`
    
  + Parameters    
    - `reason` -the reason of canceling the site.
      
  - Response    
    Status: 200 OK

#### Example
     
  Sample request:
     
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" -X PUT -d "sitename=sitename&timezone=71"  https://apptest.platform.comm100.com/accountwebapi/api/v2/account/site/cancel
```
    
  Sample response:
     
```json
Status: 200 OK
```
    
## Agent 

  + You need `Manage Agent & Agent Groups` permission to manage agent.
    - `GET /api/v2/account/agents` - Get list of agent   
    - `GET /api/v2/account/agents/{id}` - Get a single agent
    - `POST /api/v2/account/agents` - Create a new agent
    - `PUT /api/v2/account/agents/{id}` - Update an agent  
    - `DELETE /api/v2/account/agents/{id}` - Remove an agent
    - `POST /api/v2/account/agents/{id}/password` - Admin set an agent's password
    - `PUT /api/v2/account/agents/{id}/unlock` - unlock the agent
    - `GET /api/v2/account/agents/{id}/permissions` - Get list of agent's permissions. 
    - `PUT /api/v2/account/agents/{id}/permissions` - Update permissions for a agent.
    - `GET /api/v2/account/agents/{id}/effectivePermissions` -Get list of agent's effective permissions,including the permissions of the agent and the permissions of the groups which the agent belongs to. 
    
  + You can manage your own profile
    - `GET /api/v2/account/agents/me` - Get current agent
    - `PUT /api/v2/account/agents/me` - Update own profile
    - `POST /api/v2/account/agents/me/password` - Change own password

### Agent Json Format
  Agent is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only | Mandatory | Description |
  | - | - | :-: | :-: | - | 
  | id | integer | yes | no |id of the agent.
  | email | string | no | yes |email of the agent.
  | displayName | string | no | yes |display name of the agent.
  | firstName | string | no | yes | first name of the agent
  | lastName | string | no | yes | last name of the agent
  | title | string | no | no | title of the agent
  | bio | string | no | no | bio of the agent
  | mobilePhone | string | no | no | mobile phone number of the agent
  | timeZone | string | no | no | time zone of the agent 
  | dateTimeFormat | string | no | no| datetime format which the agent want to display in the site.
  | groups | array  | no | no | an array of group which the agent belongs to.
  | isAdmin | boolean | yes | no | whether the agent is an administrator or not.
  | isActive | boolean | yes | no | whether the agent is active or not.
  | isLocked | boolean | yes | no | whether the agent is locked or not.

### Get list of agents
 
  `GET /api/v2/account/agents`
    
  - Parameters    
    Optional:   
    - `pageIndex` -the page index of query.
      
  - Response 
    - `total` -total count of the list.
    - `previousPage` -url of the previous page.
    - `nextPage` -url of the next page.
    - `agents` -An array of Agent Json Object.

#### Example
     
  Sample request:
     
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" https://apptest.platform.comm100.com/accountwebapi/api/v2/account/agents
```
    
  Sample response:
     
```json
{
    "total": 1,
    "previousPage": "",
    "nextPage": "",
    "agents": [
        {
            "id": 1,
            "email": "test@comm100.com",
            "displayName": "test comm100",
            "firstName": "test",
            "lastName": "comm100",
            "title": "",
            "bio": "",
            "mobilePhone": "",
            "timeZone": "-1",
            "dateTimeFormat": "MM/dd/yyyy HH:mm:ss",
            "groups": [],
            "isAdmin": true,
            "isActive": true,
            "isLocked": false
        }
    ]
}
```
    
### Get a single agent

  `GET /api/v2/account/agents/{id}`
    
  - Parameters     
    No parameters
      
  - Response     
    Agent Object

#### Example
     
  Sample request:
     
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" https://apptest.platform.comm100.com/accountwebapi/api/v2/account/agents/1
```
    
  Sample response:
     
```json
{
    "id": 1,
    "email": "test@comm100.com",
    "displayName": "test comm100",
    "firstName": "test",
    "lastName": "comm100",
    "title": "",
    "bio": "",
    "mobilePhone": "",
    "timeZone": "-1",
    "dateTimeFormat": "MM/dd/yyyy HH:mm:ss",
    "groups": [],
    "isAdmin": true,
    "isActive": true,
    "isLocked": false
}
```
    
### Create a new agent
  
  `POST /api/v2/account/agents`

  - Parameters     
    Agent Object
      
  - Response     
    Agent Object

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" -X POST -d "email=test@test.com&displayname=testname&firstname=first&lastname=lastname&title=title&password=123456&timezone=31&mobilephone=12345678911"  https://apptest.platform.comm100.com/accountwebapi/api/v2/account/agents
```
    
  Sample response:
     
```json
{
    "id": 3, 
    "email": "test@test.com", 
    "displayName": "testname", 1
    "firstName": "first", 
    "lastName": "lastname", 
    "title": "title", 
    "bio": "", 
    "mobilePhone": "12345678911", 
    "timeZone": "31", 
    "dateTimeFormat": "MM/dd/yyyy HH:mm:ss", 
    "groups": [], 
    "isAdmin": false, 
    "isActive": true, 
    "isLocked": false
}
```
    
### Update an agent

  `PUT /api/v2/account/agents/{id}`
    
  - Parameters     
    Agent Object
      
  - Response     
    Agent Object

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" -X PUT -d "email=test1@test.com&displayname=testname&firstname=first&lastname=lastname&title=title&password=123456&timezone=31&mobilephone=12345678911"  https://apptest.platform.comm100.com/accountwebapi/api/v2/account/agents/1
```
    
  Sample response:
     
```json
{
    "id": 1, 
    "email": "test1@test.com", 
    "displayName": "testname", 
    "firstName": "first", 
    "lastName": "lastname", 
    "title": "title", 
    "bio": "", 
    "mobilePhone": "12345678911", 
    "timeZone": "31", 
    "dateTimeFormat": "MM/dd/yyyy HH:mm:ss", 
    "groups": [ ], 
    "isAdmin": true, 
    "isActive": true, 
    "isLocked": false
}
```

### Remove an agent 
 
  `DELETE /api/v2/account/agents/{id}`
    
  - Parameters     
    No parameters.
      
  - Response     
    Status: 200 OK

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" -X DELETE https://apptest.platform.comm100.com/accountwebapi/api/v2/account/agents/2
```
    
  Sample response:
     
```json
Status: 200 OK
```
    
### Admin set an agent's password

  `POST /api/v2/account/agents/{id}/password`
    
  - Parameters     
    - `password` - the new password of the agent.   

  - Response
    Status: 200 OK

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" -X POST -d "password=234567"  https://apptest.platform.comm100.com/accountwebapi/api/v2/account/agents/4/password
```
    
  Sample response:
     
```json
Status: 200 OK
```

### Unlock The Agent 

  `PUT /api/v2/account/agents/{id}/unlock`

  - Parameters     
    No parameters.
      
  - Response     
    Status: 200 OK  

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" -X POST -d ""  https://apptest.platform.comm100.com/accountwebapi/api/v2/account/agents/4/unlock
```
    
  Sample response:
     
```json
Status: 200 OK
```

### Get an agent's permissions
     
  `GET /api/v2/account/agents/{id}/permissions`
    
  - Parameters     
    No parameters
      
  - Response     

    An map of permissions group by Products
  
```json
  {
    "liveChat": {
      "manageCampaigns" : false,
      "managePublicCannedMessages" : false,
      "manageSettings": false,
      "manageChatbot": false,
      "manageSecurity" : false,
      "manageIntegration": false,
      "manageBan" : false,
      "manageCustomMetrics" : false,
      "viewAllHistory" : true,
      "viewHistoryInMyDepartment" : false,
      "chatWithAgents" : false,
      "viewAllAgentChats": false,
      "viewAgentChatsInMyDepartment" : false,
      "deleteHistory" : false,
      "viewReports" : false,
      "acceptChats" : true,
      "refuseChats" : false,
      "inviteVisitor" : false,
      "joinChats" : true,
      "transferChats": true,
      "monitorAllChats" : false,
      "monitorChatsInMyDepartment": false,
      "captureVisitor" : false,
      "setOtherAgentToAway" : false,
      "logOtherAgentOff" : false,
      "promoteVisitor" : false,
    },
    "account": {
      "manageAgentAndGroups": true,
      "manageBillingInfo" : false,
      "managePlan": false,
      "viewBalanceHistory": false,
      "manageSite": false,
      "manageHeaderAndFooterSettings": false,
      "viewAuditLog": false,
      "viewReports": false,
      "manageSecurity" : false,  
    }
  }
```

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" https://apptest.platform.comm100.com/accountwebapi/api/v2/account/agents/1/permissions
```
    
  Sample response:
     
```json
{
    "liveChat": {
        "manageCampaigns": false, 
        "managePublicCannedMessages": false, 
        "manageSettings": false, 
        "manageSecurity": false, 
        "manageIntegration": false, 
        "manageBan": false, 
        "manageCustomMetrics": false, 
        "viewAllHistory": true, 
        "viewHistoryInMyDepartment": true, 
        "chatWithAgents": true, 
        "viewAllAgentChats": false, 
        "viewAgentChatsInMyDepartment": false, 
        "deleteHistory": false, 
        "viewReports": true, 
        "acceptChats": true, 
        "refuseChats": true, 
        "inviteVisitor": true, 
        "joinChats": true, 
        "transferChats": true, 
        "monitorAllChats": false, 
        "monitorChatsInMyDepartment": true, 
        "captureVisitor": true, 
        "setOtherAgentToAway": false, 
        "logOtherAgentOff": false, 
        "promoteVisitor": true
    }, 
    "account": {
        "manageAgentAndGroups": false, 
        "manageBillingInfo": false, 
        "managePlan": false, 
        "buyEmailMarketingCredits": false, 
        "viewBalanceHistory": false, 
        "manageSite": false, 
        "manageHeaderAndFooterSettings": false, 
        "viewAuditLog": false, 
        "viewReports": true, 
        "manageSecurity": false
    }
}
```

### Update permissions for a agent
 
  `PUT /api/v2/account/agents/{id/}/permissions`
    
- Parameters     
  An map of permissions group by Products
    
- Response     
  An map of permissions group by Products

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" -H "content-type: application/json" -X PUT -d "{"liveChat":{"manageCampaigns":true,"managePublicCannedMessages":true,"manageSettings":false,"manageSecurity":false,"manageIntegration":false,"manageBan":false,"manageCustomMetrics":false,"viewAllHistory":true,"viewHistoryInMyDepartment":true,"chatWithAgents":true,"viewAllAgentChats":false,"viewAgentChatsInMyDepartment":false,"deleteHistory":false,"viewReports":true,"acceptChats":true,"refuseChats":true,"inviteVisitor":true,"joinChats":true,"transferChats":true,"monitorAllChats":false,"monitorChatsInMyDepartment":true,"captureVisitor":true,"setOtherAgentToAway":false,"logOtherAgentOff":false,"promoteVisitor":true},"account":{"manageAgentAndGroups":false,"manageBillingInfo":false,"managePlan":false,"buyEmailMarketingCredits":false,"viewBalanceHistory":false,"manageSite":false,"manageHeaderAndFooterSettings":false,"viewAuditLog":false,"viewReports":true,"manageSecurity":true}}"  https://apptest.platform.comm100.com/accountwebapi/api/v2/account/agents/1/permissions
```
    
  Sample response:
     
```json
{
    "liveChat": {
        "manageCampaigns": true, 
        "managePublicCannedMessages": true, 
        "manageSettings": false, 
        "manageSecurity": false, 
        "manageIntegration": false, 
        "manageBan": false, 
        "manageCustomMetrics": false, 
        "viewAllHistory": true, 
        "viewHistoryInMyDepartment": true, 
        "chatWithAgents": true, 
        "viewAllAgentChats": false, 
        "viewAgentChatsInMyDepartment": false, 
        "deleteHistory": false, 
        "viewReports": true, 
        "acceptChats": true, 
        "refuseChats": true, 
        "inviteVisitor": true, 
        "joinChats": true, 
        "transferChats": true, 
        "monitorAllChats": false, 
        "monitorChatsInMyDepartment": true, 
        "captureVisitor": true, 
        "setOtherAgentToAway": false, 
        "logOtherAgentOff": false, 
        "promoteVisitor": true
    }, 
    "account": {
        "manageAgentAndGroups": false, 
        "manageBillingInfo": false, 
        "managePlan": false, 
        "buyEmailMarketingCredits": false, 
        "viewBalanceHistory": false, 
        "manageSite": false, 
        "manageHeaderAndFooterSettings": false, 
        "viewAuditLog": false, 
        "viewReports": true, 
        "manageSecurity": true
    }
}
```

### Get list of a agent's effective permissions

  `GET /api/v2/account/agents/{id}/effectivePermissions`

  - Parameters     
    No parameters
      
  - Response     
    An array of Agent Permission Object.

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" https://apptest.platform.comm100.com/accountwebapi/api/v2/account/agents/1/effectivepermissions
```
    
  Sample response:
     
```json
{
    "liveChat": {
        "manageCampaigns": false, 
        "managePublicCannedMessages": false, 
        "manageSettings": false, 
        "manageSecurity": false, 
        "manageIntegration": false, 
        "manageBan": false, 
        "manageCustomMetrics": false, 
        "viewAllHistory": true, 
        "viewHistoryInMyDepartment": true, 
        "chatWithAgents": true, 
        "viewAllAgentChats": false, 
        "viewAgentChatsInMyDepartment": false, 
        "deleteHistory": false, 
        "viewReports": true, 
        "acceptChats": true, 
        "refuseChats": true, 
        "inviteVisitor": true, 
        "joinChats": true, 
        "transferChats": true, 
        "monitorAllChats": false, 
        "monitorChatsInMyDepartment": true, 
        "captureVisitor": true, 
        "setOtherAgentToAway": false, 
        "logOtherAgentOff": false, 
        "promoteVisitor": true
    }, 
    "account": {
        "manageAgentAndGroups": false, 
        "manageBillingInfo": false, 
        "managePlan": false, 
        "buyEmailMarketingCredits": false, 
        "viewBalanceHistory": false, 
        "manageSite": false, 
        "manageHeaderAndFooterSettings": false, 
        "viewAuditLog": false, 
        "viewReports": true, 
        "manageSecurity": false
    }
}
```

### Get current agent

  `GET /api/v2/account/agents/me`

  - Parameters
    No parameters.
  
  - Response 
    Agent Object

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" https://apptest.platform.comm100.com/accountwebapi/api/v2/account/agents/me
```
    
  Sample response:
     
```json
{
    "id": 1, 
    "email": "test1@test.com", 
    "displayName": "testname", 
    "firstName": "first", 
    "lastName": "lastname", 
    "title": "title", 
    "bio": "", 
    "mobilePhone": "12345678911", 
    "timeZone": "31", 
    "dateTimeFormat": "MM/dd/yyyy HH:mm:ss", 
    "groups": [ ], 
    "isAdmin": true, 
    "isActive": true, 
    "isLocked": false
}
```

### Update own profile

  `PUT /api/v2/account/agents/me` 

  - Parameters 
    Agent Object

  - Response
    Agent Object

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" -X PUT -d "email=test4@test.com&displayname=testname&firstname=first&lastname=lastname&title=title&password=123456&timezone=31&mobilephone=12345678911"  https://apptest.platform.comm100.com/accountwebapi/api/v2/account/agents/me
```
    
  Sample response:
     
```json
{
    "id": 1, 
    "email": "test4@test.com", 
    "displayName": "testname", 
    "firstName": "first", 
    "lastName": "lastname", 
    "title": "title", 
    "bio": "", 
    "mobilePhone": "12345678911", 
    "timeZone": "31", 
    "dateTimeFormat": "MM/dd/yyyy HH:mm:ss", 
    "groups": [ ], 
    "isAdmin": true, 
    "isActive": true, 
    "isLocked": false
}
```

### Change own password

  `POST /api/v2/account/agents/me/password` 

  - Parameters
    - `currentPassword` - current password of curreng agent
    - `newPassword` - new password of current agent

  - Response
   Status: 200 OK

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" -X POST -d "currentpassword=123456&newpassword=111111"  https://apptest.platform.comm100.com/accountwebapi/api/v2/account/agents/me/password
```
    
  Sample response:
     
```json
Status: 200 OK
```
    
## Group 
  You need `Manage Agent & Agent Groups` permission to manage group.
  - `GET /api/v2/account/groups` - Get list of groups
  - `GET /api/v2/account/groups/{id}` - Get a single group
  - `POST /api/v2/account/groups` - Create a new group
  - `PUT /api/v2/account/groups/{id}` - Update a group
  - `DELETE /api/v2/account/groups/{id}` - Remove a group
  - `GET /api/v2/account/groups/{id}/permissions` - Get a group's permissions.
  - `PUT /api/v2/account/groups/{id}/permissions` - Update permissions for a group.

### Group Json Format
 Group is represented as simple flat JSON objects with the following keys:  

| Name | Type | Read-only | Mandatory | Description |
| - | - | :-: | :-: | - |
| id | integer | yes | no | id of the group. |
| isSystem | bool | yes | no | indicated that the group is maintained by the system |
| name | string | no | yes | name of the group. |
| description | string | no | no | the description of the group. |
| agents | array | no | no | an array of agents in current group. |

    
### Get list of Groups

  `GET /api/v2/account/groups`
    
  - Parameters     
    No parameters
      
  - Response     
    An array of Group Object.

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" https://apptest.platform.comm100.com/accountwebapi/api/v2/account/groups
```
    
  Sample response:
     
```json
[
    {
        "id": 7, 
        "name": "Site Administrators", 
        "description": "This group includes all site administrators in the system. ", 
        "isSystem": true, 
        "agents": [ ]
    }, 
    {
        "id": 8, 
        "name": "All Agents", 
        "description": "This group includes all agents in the system. ", 
        "isSystem": true, 
        "agents": [ ]
    }
]
```
    
### Get a single group

  `GET /api/v2/account/groups/{id}`
    
  - Parameters     
    No parameters
      
  - Response     
    Group Object

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" https://apptest.platform.comm100.com/accountwebapi/api/v2/account/groups/7
```
    
  Sample response:
     
```json
{
    "id": 7, 
    "name": "Site Administrators", 
    "description": "This group includes all site administrators in the system. ", 
    "isSystem": true, 
    "agents": [ ]
}
```
    
### Create a new group
  
  `POST /api/v2/account/groups`
    
  - Parameters     
    Group Object
    
  - Response     
    Group Object

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" -X POST -d "issystem=true&name=testaddname"  https://apptest.platform.comm100.com/accountwebapi/api/v2/account/groups```
    
  Sample response:
     
```json
{
    "id": 9, 
    "name": "testaddname", 
    "description": null, 
    "isSystem": false, 
    "agents": null
}
```
    
### Update a group

  `PUT /api/v2/account/groups/{id}`
    
  - Parameters     
    Group Object
          
  - Response     
    Group Object

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" -X PUT -d "name=testchangename"  https://apptest.platform.comm100.com/accountwebapi/api/v2/account/groups/7
```
    
  Sample response:
     
```json
{
    "id": 7, 
    "name": "testchangename", 
    "description": "This group includes all site administrators in the system. ", 
    "isSystem": true, 
    "agents": [ ]
}
```
      
### Remove a group 
 
  `DELETE /api/v2/account/groups/{id}`
    
  - Parameters     
    No parameters.
      
  - Response     
    Status: 200 OK    

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" -X DELETE  https://apptest.platform.comm100.com/accountwebapi/api/v2/account/groups/9
```
    
  Sample response:
     
```json
Status: 200 OK 
```
    
### Get a group's permissions
- End Point     
  `GET /api/v2/account/groups/{id}/permissions`
    
- Parameters     
  No parameters
    
- Response     
  An map of permissions group by Products

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" https://apptest.platform.comm100.com/accountwebapi/api/v2/account/groups/7/permissions
```
    
  Sample response:
     
```json
{
    "liveChat": {
        "manageCampaigns": false, 
        "managePublicCannedMessages": false, 
        "manageSettings": false, 
        "manageSecurity": false, 
        "manageIntegration": false, 
        "manageBan": false, 
        "manageCustomMetrics": false, 
        "viewAllHistory": false, 
        "viewHistoryInMyDepartment": false, 
        "chatWithAgents": false, 
        "viewAllAgentChats": false, 
        "viewAgentChatsInMyDepartment": false, 
        "deleteHistory": false, 
        "viewReports": false, 
        "acceptChats": false, 
        "refuseChats": false, 
        "inviteVisitor": false, 
        "joinChats": false, 
        "transferChats": false, 
        "monitorAllChats": false, 
        "monitorChatsInMyDepartment": false, 
        "captureVisitor": false, 
        "setOtherAgentToAway": false, 
        "logOtherAgentOff": false, 
        "promoteVisitor": false
    }, 
    "account": {
        "manageAgentAndGroups": false, 
        "manageBillingInfo": false, 
        "managePlan": false, 
        "buyEmailMarketingCredits": false, 
        "viewBalanceHistory": false, 
        "manageSite": false, 
        "manageHeaderAndFooterSettings": false, 
        "viewAuditLog": false, 
        "viewReports": false, 
        "manageSecurity": false
    }
}
```
    
### Update permissions for a group
- End Point     
  `PUT /api/v2/account/groups/{id/}/permissions`
    
- Parameters     
  An map of permissions group by Products
    
- Response     
  An map of permissions group by Products

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" -H "content-type: application/json" -X PUT -d "{"liveChat":{"manageCampaigns":true,"managePublicCannedMessages":true,"manageSettings":false,"manageSecurity":false,"manageIntegration":false,"manageBan":false,"manageCustomMetrics":false,"viewAllHistory":true,"viewHistoryInMyDepartment":true,"chatWithAgents":true,"viewAllAgentChats":false,"viewAgentChatsInMyDepartment":false,"deleteHistory":false,"viewReports":true,"acceptChats":true,"refuseChats":true,"inviteVisitor":true,"joinChats":true,"transferChats":true,"monitorAllChats":false,"monitorChatsInMyDepartment":true,"captureVisitor":true,"setOtherAgentToAway":false,"logOtherAgentOff":false,"promoteVisitor":true},"account":{"manageAgentAndGroups":true,"manageBillingInfo":false,"managePlan":false,"buyEmailMarketingCredits":false,"viewBalanceHistory":false,"manageSite":false,"manageHeaderAndFooterSettings":false,"viewAuditLog":true,"viewReports":true,"manageSecurity":true}}"  https://apptest.platform.comm100.com/accountwebapi/api/v2/account/groups/7/permissions
```
    
  Sample response:
     
```json
{
    "liveChat": {
        "manageCampaigns": true, 
        "managePublicCannedMessages": true, 
        "manageSettings": false, 
        "manageSecurity": false, 
        "manageIntegration": false, 
        "manageBan": false, 
        "manageCustomMetrics": false, 
        "viewAllHistory": true, 
        "viewHistoryInMyDepartment": true, 
        "chatWithAgents": true, 
        "viewAllAgentChats": false, 
        "viewAgentChatsInMyDepartment": false, 
        "deleteHistory": false, 
        "viewReports": true, 
        "acceptChats": true, 
        "refuseChats": true, 
        "inviteVisitor": true, 
        "joinChats": true, 
        "transferChats": true, 
        "monitorAllChats": false, 
        "monitorChatsInMyDepartment": true, 
        "captureVisitor": true, 
        "setOtherAgentToAway": false, 
        "logOtherAgentOff": false, 
        "promoteVisitor": true
    }, 
    "account": {
        "manageAgentAndGroups": true, 
        "manageBillingInfo": false, 
        "managePlan": false, 
        "buyEmailMarketingCredits": false, 
        "viewBalanceHistory": false, 
        "manageSite": false, 
        "manageHeaderAndFooterSettings": false, 
        "viewAuditLog": true, 
        "viewReports": true, 
        "manageSecurity": true
    }
}
```
    
## IP Restriction
  You need `Manage Security` permission to manage ip restrictions.
  - `GET /api/v2/account/ipRestriction` - Get configuration of ip restrictions 
  - `PUT /api/v2/account/ipRestriction` - Update configuration of ip restrictions 
  - `GET /api/v2/account/ipRestriction/ipRanges` - Get authorized ip range list of ip restriction
  - `PUT /api/v2/account/ipRestriction/ipRanges` - Update an authorized ip range
  - `POST /api/v2/account/ipRestriction/ipRanges/{id} ` - Create a new ip range of ip restriction
  - `DELETE /api/v2/account/ipRestriction/ipRanges/{id} ` - Remove a ip range of ip restriction

### IP Restriction Config Json Format
 Ip Restrictions is represented as simple flat JSON objects with the following keys:  

| Name | Type | Read-only | Mandatory |  Description |         
| - | - | - | - | - | 
| isEnable | boolean | no | no | whether IP Restrictions is enable or not. |
| isEnableForMobile | boolean | no | no | whether IP Restrictions is enable or not for mobile app access. |
    
### Get configuration of ip restriction

  `Get /api/v2/account/ipRestriction`

  - Parameters     
    No parameters.

  - Response     
    IP Restriction Config Object.

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" https://apptest.platform.comm100.com/accountwebapi/api/v2/account/iprestriction
```
    
  Sample response:
     
```json
{
    "isEnable": true, 
    "isEnableForMobile": false
}
```

### Update configuration of ip restriction

  `PUT /api/v2/account/ipRestriction`

  - Parameters     
    IP Restriction Config Object.

  - Response     
    IP Restriction Config Object.

#### Example
    
  Sample request:
 
```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" -H "content-type: application/json" -X PUT -d "{"isEnable":false,"isEnableForMobile":false}"  https://apptest.platform.comm100.com/accountwebapi/api/v2/account/iprestriction
```
    
  Sample response:
     
```json
{
    "isEnable": false, 
    "isEnableForMobile": false
}
```

### Ip Range Json Format
  Ip Range is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only | Mandatory | Description |                    
  | - | - | :-: | :-: | - | 
  | id | integer  | yes | no | id of ip range. |
  | from | string  | no | yes | ip which ip range start from. |
  | to | string  | no | yes | ip which ip range end to. |
    
### Get ip range list of ip restriction
  
  `Get /api/v2/account/ipRestriction/ipRanges`

  - Parameters
    No parameters

  - Response
    An array of Ip Range Json Object.

#### Example
    
  Sample request:

```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" https://apptest.platform.comm100.com/accountwebapi/api/v2/account/iprestriction/ipranges
```
    
  Sample response:
     
```json
[
    {
        "id": 4, 
        "from": "192.168.1.1", 
        "to": "192.168.1.2"
    }, 
    {
        "id": 5, 
        "from": "192.168.1.3", 
        "to": "192.168.1.4"
    }
]
```

### Create a new ip range of ip restrictions

  `POST /api/v2/account/ipRestriction/ipRanges/{id}`

  - Parameters
      Ip Range Json Object.

  - Response
      Ip Range Json Object.

#### Example
    
  Sample request:

```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" -X POST -d "from=192.168.1.3&to=192.168.1.4"  https://apptest.platform.comm100.com/accountwebapi/api/v2/account/iprestriction/ipranges
```
    
  Sample response:
     
```json
{
    "id": 5, 
    "from": "192.168.1.3", 
    "to": "192.168.1.4"
}
```

### Remove a ip range of ip restriction

  `DELETE /api/v2/account/ipRestriction/ipRanges/{id}`

  - Parameters
    No parameters.

  - Response
    Status: 200 OK

#### Example
    
  Sample request:

```bash
curl -H "Authorization: Bearer yHShF0rEGY0BcO9TvsjxVRygYl_Ad7-eO3YZ4L1jIrRXUa-_IGHMGHqhRXXdgjvJsYjLlo3i0h_nMmlAeD0eFrW18uFABigYk21hm4n95eEhaWqi6gIiPFddWkoVJTX_jkK_g5me9zwP_RJSunV7okaqciXPRozb2ita6MjS0b7Vrxcy1_ufHNzOjzaUH7AvOmqtL6zMCuBlPcLeDNG3S74Ui5F2npOyg-j0MdIrtfq8gjqMqwywSJc8Kk8gtXGFzZKDK6qdHzT8TeojT9-M4A" -X DELETE https://apptest.platform.comm100.com/accountwebapi/api/v2/account/iprestriction/ipranges/5
```
    
  Sample response:
     
```json
"IPRange '5' has been removed."
```


## Audit Log
  You need `View Audit Log` permission to view audit logs.
  + `Get /api/v2/account/auditLogs` - Get audit Logs list.
    
### Get audit Logs list 

  `Get /api/v2/account/auditLogs`

  - Parameters
    - `dateFrom` - the date from which agent do the action.
    - `dateTo` - the date end which agent do the action.   
    optional：
    - `product` - the product which the action belongs to, including `liveChat` and `account`.
    - `type` - the type of the action.
    - `agentId` - id of the agent who do the action.
    - `keywords` - the key words of inquiring the action
    - `pageIndex` -the page index of query.
      
  - Response
    - `total` -total count of the list.
    - `previousPage` -url of the previous page.
    - `nextPage` -url of the next page.
    - `logs` -audit log list
      + `id` -id of the config.
      + `actionTime` -the time of the action.
      + `agentName` - the agent which do the action.
      + `product` - the module which the action belongs to.
      + `actionType` - the type of the action.
      + `actionSummary` - the summary of the action.
      
#### Example
    
  Sample request:

```bash
curl -H "Authorization: Bearer XCUScuZK21qDa2Tqyo0HF1rvoHC6OTIKZRkj-GgKUcsVyaXyhC7sNfGRyZc5vUGXXeI9wzo74KX9xXrDTA3QR4XCXcaslq7a17ubllUwRRoMqt-cxYETrb5WFjOv4GRvM8nRO5H5nangeGJMHgJczhyiu7897kYvdlRHOudnoYbkwBPNMKUzQN9hiRNtZi8eV3Faf8OZYSWGxFZPvWcNHqY78WGXwnYww_UNB1HzME7UKcvY1Auxhdq_ZR-UncaiNoM46OBYYbU5nNXbKDFPAA" https://apptest.platform.comm100.com/accountwebapi/api/v2/account/auditlogs?datefrom=2018/7/7&dateto=2018/8/8
```
    
  Sample response:
     
```json
{
    "total": 1, 
    "previousPage": null, 
    "nextPage": null, 
    "logs": [
        {
            "id": 1, 
            "actionTime": "2018-08-08T10:21:44.403", 
            "agentName": "testname", 
            "product": "Live Chat", 
            "actionType": "Chats Auto Allocation Management", 
            "actionSummary": "Enable chats auto allocation"
        }
    ]
}
```