# Authentication and Authorization

## Microsoft Entra ID
**Microsoft Entra ID** is a directory service that enables you to sign in and access both Microsoft cloud applications and cloud applications that you develop. Microsoft Entra ID is Microsoft Azure's cloud-based identity and access management service.
- Authentication (employees sign-in to access resources).
- Single sign-on (SSO).
- Application management.
- Business to Business (B2B).
- Device management.

> You manage the credentials, but Microsoft ensures the global availability of the process.

Microsoft also detects suspicious login attempts due to:
- Unknown devices
- Suspicious locations

## Microsoft Entra Domain Services
![Microsoft Entra Domain Services](../assets/az900/entraid-domain-services.png "Microsoft Entra Domain Services")
- Gain the benefit of cloud-based domain services without managing domain controllers
- Run legacy applications (that can't use modern auth standards) in the cloud
- Automatically sync from Microsoft Entra ID

### Compare Authentication and Authorization
Authentication
- Identifies the person or service seeking access to a resource.
- Requests legitimate access credentials.
- Basis for creating secure identity and access control principles.

Authorization
- Determines an authenticated person's or service's level of access.
- Defines which data they can access, and what they can do with it.

## Azure external identities
An external identity is a person, device, service, etc. that is outside your organization. 
The following capabilities make up External Identities:

- **Business to business (B2B) collaboration** \
Collaborate with external users by letting them use their preferred identity to sign-in to your Microsoft applications or other enterprise applications (SaaS apps, custom-developed apps, etc.). B2B collaboration users are represented in your directory, typically as guest users.
- **B2B direct connect** \
 Establish a mutual, two-way trust with another Microsoft Entra organization for seamless collaboration. B2B direct connect currently supports Teams shared channels, enabling external users to access your resources from within their home instances of Teams. B2B direct connect users aren't represented in your directory, but they're visible from within the Teams shared channel and can be monitored in Teams admin center reports.
- **Microsoft Azure Active Directory business to customer (B2C)** \
 Publish modern SaaS apps or custom-developed apps (excluding Microsoft apps) to consumers and customers, while using Azure AD B2C for identity and access management.

 ![Microsoft Entra External ID B2B](../assets/az900/entra-external-id-b2b.png "Microsoft Entra External ID B2B")

### Conditional Access
Organizations now use identity-driven signals as part of their access control decisions. Microsoft Entra Conditional Access brings signals together, to make decisions, and enforce organizational policies. Conditional Access is Microsoft's Zero Trust policy engine taking signals from various sources into account when enforcing policy decisions.

**Conditional Access** is used to bring signals together, to make decisions, and enforce organizational policies.
- User or Group Membership
- IP Location
- Device
- Application
- Risk Detection

![Conditional Access](../assets/az900/conditional-access-signals.png "Conditional Access Signals")

## Role-based access control
- Fine-grained access management.
- Segregate duties within the team and grant only the amount of access to users that they need to perform their jobs.
- Enables access to the Azure portal and controlling access to resources.