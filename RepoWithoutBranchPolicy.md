# Repositories without branch policies

## Context

Ensure that all repos have some good practices with branch policies


## Graph API

```graph
query {
  viewer {
    name
     repositories(first: 10) {
       nodes {
         name
         branchProtectionRules(first: 20) {
          nodes {
            allowsDeletions
            allowsForcePushes
            dismissesStaleReviews
            pattern

          }
        }
       }
       
     }
   }
}
```