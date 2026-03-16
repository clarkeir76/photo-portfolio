# C4 Level 1 — System Context

```mermaid
C4Context
    title System Context — iainclarkephotography.co.uk

    Person(visitor, "Site Visitor", "Members of the public browsing landscape photography, primarily UK-based")
    Person(admin, "Site Admin", "Iain — manages galleries and images via the admin UI")

    System(photoSite, "Photo Portfolio", "Displays landscape photography galleries. Allows admin to manage content.")

    System_Ext(route53, "AWS Route 53", "DNS for iainclarkephotography.co.uk")
    System_Ext(cognito, "AWS Cognito", "Handles admin authentication")
    System_Ext(github, "GitHub", "Source code repository and CI/CD pipeline trigger")

    Rel(visitor, photoSite, "Browses galleries and images", "HTTPS")
    Rel(admin, photoSite, "Manages galleries and images", "HTTPS")
    Rel(photoSite, cognito, "Authenticates admin users", "HTTPS")
    Rel(route53, photoSite, "Routes domain traffic to", "DNS")
    Rel(github, photoSite, "Deploys via CI/CD pipeline", "GitHub Actions")
```
