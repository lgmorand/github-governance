# Repo without topics

## Context

It is possible to setup a global setting for default retention at the organization level but repo owners can overwrite this setting

## Need

A script listing repo which overwrite the default setting

## Implementation

List all repos and watch their topics 

### Using Graph

```graph
query {
  viewer {
    name
     repositories(first: 100) {
       nodes {
         name
         repositoryTopics(first: 20) {
          nodes {
            topic {
              name
            }
          }
         }
      }
    }
  }
}
```

### Using REST API

https://api.github.com/orgs/{{OrgName}}/repos


```json
{
        "id": 742596866,
        "node_id": "R_kgDOLEMhAg",
        "name": "testLG1",
        "full_name": "twolefthandev-public/testLG1",
        "private": true,
       
        "topics": [
            "reftech"
        ],
        
    }
```