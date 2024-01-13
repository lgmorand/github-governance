# Counting owners per repo

## Context

Trying to see repository with only one owner or too many owners

## Implementation

Look at collaborators of a repo and count the ones with admin: true

https://api.github.com/repos/{{OrgName}}/testLG1/collaborators

ex:
```json
[
    {
        "login": "lgmorand",
        "id": 6757079,
        "node_id": "MDQ6VXNlcjY3NTcwNzk=",
        "avatar_url": "https://avatars.githubusercontent.com/u/6757079?v=4",
        "gravatar_id": "",
        "url": "https://api.github.com/users/lgmorand",
        "html_url": "https://github.com/lgmorand",
        "followers_url": "https://api.github.com/users/lgmorand/followers",
        "following_url": "https://api.github.com/users/lgmorand/following{/other_user}",
        "gists_url": "https://api.github.com/users/lgmorand/gists{/gist_id}",
        "starred_url": "https://api.github.com/users/lgmorand/starred{/owner}{/repo}",
        "subscriptions_url": "https://api.github.com/users/lgmorand/subscriptions",
        "organizations_url": "https://api.github.com/users/lgmorand/orgs",
        "repos_url": "https://api.github.com/users/lgmorand/repos",
        "events_url": "https://api.github.com/users/lgmorand/events{/privacy}",
        "received_events_url": "https://api.github.com/users/lgmorand/received_events",
        "type": "User",
        "site_admin": false,
        "permissions": {
            "admin": true,
            "maintain": true,
            "push": true,
            "triage": true,
            "pull": true
        },
        "role_name": "admin"
    },
    {
        "login": "Justrebl",
        "id": 16562522,
        "node_id": "MDQ6VXNlcjE2NTYyNTIy",
        "avatar_url": "https://avatars.githubusercontent.com/u/16562522?v=4",
        "gravatar_id": "",
        "url": "https://api.github.com/users/Justrebl",
        "html_url": "https://github.com/Justrebl",
        "followers_url": "https://api.github.com/users/Justrebl/followers",
        "following_url": "https://api.github.com/users/Justrebl/following{/other_user}",
        "gists_url": "https://api.github.com/users/Justrebl/gists{/gist_id}",
        "starred_url": "https://api.github.com/users/Justrebl/starred{/owner}{/repo}",
        "subscriptions_url": "https://api.github.com/users/Justrebl/subscriptions",
        "organizations_url": "https://api.github.com/users/Justrebl/orgs",
        "repos_url": "https://api.github.com/users/Justrebl/repos",
        "events_url": "https://api.github.com/users/Justrebl/events{/privacy}",
        "received_events_url": "https://api.github.com/users/Justrebl/received_events",
        "type": "User",
        "site_admin": false,
        "permissions": {
            "admin": true,
            "maintain": true,
            "push": true,
            "triage": true,
            "pull": true
        },
        "role_name": "admin"
    }
]
```