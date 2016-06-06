# RDP

Grab RDP information and screenshots.

## RDP Request Example

  ```
curl -v -L https://api.binaryedge.io/v1/tasks  -d  '{"type":"grab", "options":[{"targets":["X.X.X.X"], "ports":[{"port":3389,"modules": ["rdp"]}]}]}' -H "X-Token:NNNNNN"
  ```

## Schema

### RDP Event Schema
```
{
  ...
  "result": {
    "data": {
      "security": "string",
      "link": "string"
    }
}
```

### Contents of the fields:

  * security - Type of RDP security
  * link - URL link to the screenshot

## RDP Event Example

```
{
  "origin": {
    "type": "rdp",
    "job_id": "client-49f4e8c6-af44-4d22-bfc6-8fbf7f313418",
    "client_id": "client",
    "module": "grabber",
    "country": "fr",
    "ts": 1464873866890
  },
  "target": {
    "ip": "X.X.X.X",
    "port": 3389
  },
  "result": {
    "data": {
      "security": "SSL",
      "link": "https://url/to/image.jpg"
    }
  }
}
```