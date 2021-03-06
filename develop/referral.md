---
title: Referral
description: Resources that represents a sales lead direct from a customer, Microsoft or another partner.  
ms.date: 11/08/2018
ms.localizationpriority: medium
---

# Referral

**Applies To**

-   Partner Center

Resources that represent a sales lead direct from a customer, Microsoft, or another partner.   


## <span id="Referral"></span><span id="referral"></span><span id="REFERRAL"></span>Referral

Represents the referral.

| Property              | Type                                              | Description                                                                                                       |
|-----------------------|---------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| Id                    | string                                            | The ID for this Referral.                                                                                         |
| EngagementId          | string                                            | The EngagementID for this Referral. Multiple referrals can be associated to a single EngagementID                 |
| Name                  | string                                            | The name of the Referral.                 |
| OrganizationId        | string                                            | The organization ID of the party that owns the referral.           |
| BusinessProfileId     | string                                            | The business profile ID of the organization that owns the referral.                                       |
| OrganizationName      | string                                            | The organization name that owns the referral.   |
| ExternalReferenceId   | string                                            | An external identifier for the referral. Example: Store your own Dynamics 365 lead/opportunity ID                    |
| CreatedDateTime       | string in UTC date time format                    | The date the referral was created.                                                                                |
| UpdatedDateTime       | string in UTC date time format                    | The date the referral was last updated.                                                                           |
| ExpirationDateTime    | string in UTC date time format                    | The date the referral will expire.                                                                                |
| Status                | [ReferralStatus](referral.md#ReferralStatus)      | An [Enum](https://docs.microsoft.com/dotnet/api/system.enum) with values that indicate the referral status. |
| Substatus          | [ReferralSubstatus](referral.md#ReferralSubstatus)      | An [Enum](https://docs.microsoft.com/dotnet/api/system.enum) with values that indicate the referral sub status. |
| StatusReason          | string                                            | A descriptive message about the status. Example: Why was the referral lost? |
| ReferralType          | [ReferralType](referral.md#ReferralType)          | Represents the referral type.                                                                                     |
| Qualification         | [ReferralQualification](referral.md#ReferralQualification)| Represents the quality of the referral.                                                                           |
| CustomerProfile       | [CustomerProfile](referral.md#CustomerProfile)    | Information about the customer.                                                                                     |
| Consent               | [Consent](referral.md#Consent)                    | Consent flags around sharing information with other organizations and allowing them to contact users.         |
| Details               | [ReferralDetails](referral.md#ReferralDetails)    | Customer details, notes, deal value, currency closing date.                                                                |
| Team                  | [Member](referral.md#Member)                      | Represents users in the organizations that are involved.                                |
| InviteContext         | [InviteContext](referral.md#InviteContext)        | Represents additional information a user can provide when inviting another organization into the partner engagement.  |
| ETag                  | string                                            | ETags are used and required for concurrency checking when updating resources. |


## <span id="ReferralStatus"></span><span id="referralstatus"></span><span id="REFERRALSTATUS"></span>ReferralStatus

An [Enum](https://docs.microsoft.com/dotnet/api/system.enum) with values that indicate the referral status.

| Value           | Description                                                                                |
|-----------------|---------------------------------------------------------------------------------------------|
| None            |                                                                                             |
| New             | Represents a new referral.                                                                 |
| Active          | Represents an active referral.                                                             |
| Closed          | Represents a closed referral.                                                              |


## <span id="ReferralSubstatus"></span><span id="referralSubstatus"></span><span id="REFERRALSubstatus"></span>ReferralSubstatus

An [Enum](https://docs.microsoft.com/dotnet/api/system.enum) with values that indicate the referral status.

| Value           | Description                                                                                |
|-----------------|--------------------------------------------------------------------------------------------|
| None            |                                                                                            |
| Pending         | Represents a new referral that is pending.                                                 |
| Received        | Represents a new referral that has been received.                   |
| Accepted        | Represents a active referral that has been accepted.                                                    |
| Won             | Represents a closed referral that has been won.                                            |
| Lost            | Represents a closed referral that has been lost.                                           |
| Declined        | Represents a closed referral that has been declined.                                       |
| Expired         | Represents a closed referral that has expired.                                             |

**Status & Substatus transition states**

| Status                | Allowed Status Transition     | Allowed Substatus                |
|-----------------------|-------------------------------|---------------------------------------|
| New                   | New, Active, Closed           | Pending, Received                     |
| Active                | Active, Closed                | Accepted                              |
| Closed                | Closed                        | Won, Lost, Declined, Expired          |


## <span id="ReferralType"></span><span id="referraltype"></span><span id="REFERRALTYPE"></span>ReferralType

An [Enum](https://docs.microsoft.com/dotnet/api/system.enum) with values that indicate the referral type.

| Property              | Description                                                                     |
|-----------------------|---------------------------------------------------------------------------------|
| Shared                | Represents a referral in which all parties involved will collaborate to close.  |
| Independent           | Represents a referral in which two parties will collaborate to close.           |


## <span id="ReferralQualification"></span><span id="referralqualification"></span><span id="REFERRALQUALIFICATION"></span>ReferralQualification

An [Enum](https://docs.microsoft.com/dotnet/api/system.enum) with values that indicate the referral status.

| Value                | Description                                                                                 |
|----------------------|---------------------------------------------------------------------------------------------|
| None                 | Represents a referral that has no quality measure associated.                               |
| Direct               | Represents a referral that has been created directly by a customer.                         |
| MarketingQualified   | Represents a referral that has been generated via Microsoft marketing automation systems.   |
| SalesQualified       | Represents a referral from a Microsoft sales agent.                                         |


## <span id="CustomerProfile"></span><span id="customerprofile"></span><span id="CUSTOMERPROFILE"></span>CustomerProfile

Contains the customer contact information.

| Property        | Type                                                          | Description                                             |
|-----------------|---------------------------------------------------------------|---------------------------------------------------------|
| Id              | string                                                        | The Id for this CustomerProfile.                        |
| Name            | string                                                        | The customer organization name.                         |
| Address         | [Address](referral.md#address)                                | The address of the customer.                            |
| Size            | string                                                        | The number of employees at the customers organization.  |
| Team            | [Member](referral.md#Member)                                  | The contacts for the customer organization.             |
| Ids            | [CustomerProfileType](referral.md#CustomerProfileType)                      | External ID's for the customer.             |

## <span id="CustomerProfileType"></span><span id="customerprofiletype"></span><span id="CUSTOMERPROFILETYPE"></span>CustomerProfileType

Contains the External ID's for the customer. 

| Property        | Type                                                          | Description                                             |
|-----------------|---------------------------------------------------------------|---------------------------------------------------------|
| Duns            | string                                                        | The [Dun & Bradstreet number](https://www.dnb.com/duns-number ) for the customer.                        |
| External        | string                                                        | A customer ID unique to your organization.                      |



## <span id="Address"></span><span id="address"></span><span id="ADDRESS"></span>Address

An address to use for the customer. For more information about the supported formats and properties in different countries/regions, see [Get address formatting rules by market](get-market-specific-validation-data.md).

| Property        | Type        | Description                                                   |
|-----------------|-------------|---------------------------------------------------------------|
| AddressLine1    | string      | The first line of the address.                                |
| AddressLine2    | string      | The second line of the address. This property is optional.    |
| City            | string      | The city.                                                     |
| State           | string      | The state.                                                    |
| PostalCode      | string      | The zip code or postal code                                   |
| Country         | string      | The country/region in ISO country code format.                |
| Region          | string      | The region.                                                   |


## <span id="Member"></span><span id="member"></span><span id="MEMBER"></span>Member

Describes contact information for a specific individual.

| Property    | Type   | Description                  |
|-------------|--------|------------------------------|
| FirstName   | string | The contact's first name.    |
| LastName    | string | The contact's last name.     |
| PhoneNumber | string | The contact's phone number.  |
| Email       | string | The contact's email address. |
| ContactPreference       | [ContactPreference](referral.md#ContactPreference) | The contact's preference for receiving email notifications. |

## <span id="ContactPreference"></span><span id="contactpreference"></span><span id="CONTACTPREFERENCE"></span>ContactPreference

Describes contact preferences for receiving email notifications.

| Property    | Type   | Description                  |
|-------------|--------|------------------------------|
| Locale   | string | The locale of the email notification. [AllCultures](https://docs.microsoft.com/en-us/dotnet/api/system.globalization.culturetypes?view=netframework-4.7.2#System_Globalization_CultureTypes_AllCultures), [NeutralCultures](https://docs.microsoft.com/en-us/dotnet/api/system.globalization.culturetypes?view=netframework-4.7.2#System_Globalization_CultureTypes_NeutralCultures), and [SpecificCultures](https://docs.microsoft.com/en-us/dotnet/api/system.globalization.culturetypes?view=netframework-4.7.2#System_Globalization_CultureTypes_SpecificCultures) are supported  |
| DisableNotifications    | bool | Will disable email notifications for the user.     |


## <span id="Consent"></span><span id="consent"></span><span id="CONSENT"></span>Consent

Consent flags around sharing information with other organizations and allowing them to contact users.

| Property                                         | Type      | Description                                                                                |
|--------------------------------------------------|-----------|--------------------------------------------------------------------------------------------|
| ConsentToToShareInfoWithOthers                   | boolean   | Indicates consent to share personally identifiable information (PII) with others.             |
| ConsentToContact                                 | boolean   | Indicates consent to contact users.  |


## <span id="InviteContext"></span><span id="invitecontext"></span><span id="INVITECONTEXT"></span>InviteContext

Additional information that can be shared when inviting another organizations. 

| Property              | Type                                                       | Description                                                                   |
|-----------------------|------------------------------------------------------------|-------------------------------------------------------------------------------|
| Notes                 | string                                                     | Additional notes for the receiving organization.                |
| InvitedBy | [InvitedBy](referral.md#InvitedBy)                                     | The organization ID that sent the referral.                                   |

## <span id="InvitedBy"></span><span id="invitedby"></span><span id="INVITEDBY"></span>InvitedBy

Additional information that can be shared when inviting another organizations. 

| Property              | Type                                                       | Description                                                                   |
|-----------------------|------------------------------------------------------------|-------------------------------------------------------------------------------|
| OrganizationId        | string                                                     | The organization ID that sent the referral.                |
| OrganizationName      | string                                                     | The organization name that sent the referral.                                   |

## <span id="ReferralDetails"></span><span id="referraldetails"></span><span id="REFERRALDETAILS"></span>ReferralDetails

Represents the referral details.

| Property              | Type                                                       | Description                                                                   |
|-----------------------|------------------------------------------------------------|-------------------------------------------------------------------------------|
| Notes                 | string                                                     | Additional notes for the receiving organization.                |
| DealValue             | decimal                                                    | Value of the referral.                                    |
| Currency              | string                                                    | The [ISO 4217 currency symbol](https://docs.microsoft.com/en-us/dotnet/api/system.globalization.regioninfo.isocurrencysymbol?view=netframework-4.7.2)                                   |
| ClosingDateTime       | string in UTC date time format                         | Date the customer is looking to close by.                           |
| Requirements          | [ReferralRequirements](referral.md#ReferralRequirements)   | Industry, products, service type, and solutions the customer is interested in.|


## <span id="ReferralRequirements"></span><span id="referralrequirements"></span><span id="REFERRALREQUIREMENTS"></span>ReferralRequirements

Contains the customer requirements.

| Property        | Type                                                         | Description                                          |
|-----------------|--------------------------------------------------------------|------------------------------------------------------|
| Industries      | [Tag](referral.md#tag)                                       | The industries the customer is interested in.        |
| Products        | [Tag](referral.md#tag)                                       | The products the customer is interested in.          |
| Services        | [Tag](referral.md#tag)                                       | The services the customer is interested in.          |
| Solutions       | [SolutionTag](referral.md#SolutionTag)                       | The solutions the customer is interested in.                             |

## <span id="SolutionTag"></span><span id="solutiontag"></span><span id="SOLUTIONTAG"></span>SolutionTag

Contains the solution details.

| Property        | Type                                         | Description                                          |
|-----------------|----------------------------------------------|------------------------------------------------------|
| Id              | string                                       | The ID of the solution.        |
| Name            | string                                       | The name of the solution.          |
| SolutionType    | [SolutionType](referral.md#SolutionType)     | The type of solution.          |

## <span id="SolutionType"></span><span id="solutiontype"></span><span id="SOLUTIONTYPE"></span>SolutionType

An [Enum](https://docs.microsoft.com/dotnet/api/system.enum) with values that indicate the solution type.

| Property        | Description                                                     |
|-----------------|-----------------------------------------------------------------|
| None            |                                                                  |
| Category        |  Leverages pre-defined solution names.                            |
| Name            |  Ability to reference solutions from the Microsoft catalog. |


## <span id="Tag"></span><span id="tag"></span><span id="TAG"></span>Tag

Describes the tag.

| Property                  | Type                                                  | Description                                                   |
|---------------------------|-------------------------------------------------------|---------------------------------------------------------------|
| Id                        | string                                                | The ID for this tag.                                          |


### Products

| Value        |
|-----------------|
|Azure|
|EnterpriseMobilityAndSecurity|
|Exchange|
|DeveloperTools|
|Dynamics365Business|
|Dynamics365Enterprise|
|DynamicsAX,GP,NAV,SL|
|Microsoft365|
|Office|
|PowerBI|
|Project|
|SharePoint|
|SkypeForBusiness|
|Surface|
|SurfaceHub|
|SQL|
|Teams|
|Visio|
|Windows|
|Yammer|

### Services

| Value        |
|-----------------|
|ConsultingAndProfessional|
|CustomSolution(ISV)|
|DeploymentOrMigration|
|Hardware|
|Integration|
|IPServices(ISV)|
|LearningAndCertification|
|Licensing|
|ManagedServices|
|ProjectServices|


### Industries

| Value        |
|-----------------|
|Agriculture, Forestry, & Fishing|
|Communications & Media|
|Education|
|Financial Services|
|Government|
|Healthcare|
|Hospitality|
|Manufacturing|
|Power & Utilities|
|Public Safety and National Security|
|Retail & Consumer Goods|
|Services|
|Travel & Transportation|
|Wholesale & Distribution|


### Solutions

| Value        |
|-----------------|
|AdvancedAnalytics|
|ApplicationIntegration|
|ArtificialIntelligence|
|AzureSecurityOperationManagement|
    |AzureStack|
    |BackupDisasterRecovery|
    |BigData|
    |Blockchain|
    |Chatbot|
    |CloudDatabaseMigration|
    |CloudMigration|
    |CloudVoice|
    |CognitiveServices|
    |CompetitiveDatabaseMigration|
    |Containers|
    |DataWarehouse|
    |DatabaseonLinux|
    |DevelopmentandTest|
    |DevOps|
    |DigitalMedia|
    |Dynamics365forCustomerService|
    |Dynamics365forFieldService|
    |Dynamics365forFinanceOperations|
    |Dynamics365forRetail|
    |Dynamics365forSales|
    |Dynamics365forTalent|
    |DynamicsonAzure|
    |EnterpriseBusinessIntelligence|
    |Gaming|
    |HighPerformanceComputing|
    |HybridStorage|
    |IdentityandAccessManagement|
    |InformationManagement|
    |InternetofThings|
    |MachineLearning|
    |Microserviceapplications|
    |MobileApplications|
    |MySQLPostgresMigrationtoAzure|
    |Networking|
    |NoSQLMigration|
    |RedhatonAzure|
    |RegulatoryComplianceGDPR|
    |SAPonAzure|
    |ServerlessComputing|
    |SharepointonAzure|
    |SQLServerUpgrade|
    |ThreatProtection|
    |WebDevelopment|


### Customer Size

| Value        |
|-----------------|
|    1to50employees|
|    51to500employees|
|    Morethan500employees|
|    1to9employees|
|    10to50employees|
|    51to250employees|
|    251to1000employees|
|    1001to5000employees|
|    5001to10000employees|
|    10001to20000employees|
|    Morethan20000employees|
