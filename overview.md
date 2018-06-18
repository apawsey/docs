bigNEON Platform Overview
=========================== 

bigNEON is the first mobile-centric ticketing platform that combines the primary and secondary markets using blockchain technology. This platform will be open sourced so that anyone can launch a ticketing platform on the blockchain.

## Event Ticketing

bigNEON makes it easy for anyone to create, manage, sell, and verify tickets to events in a secure and scalable way. While ticket records do exist in the bigNEON platform database, the actual digital ticket asset that event attendees own resides on, and is secured by, a blockchain protocol specifically designed to manage digital assets like tickets at scale. This protocol ensures rules set by ticket sellers are adhered to, and risk of fraud is mitigated, while simultaneously enabling a more open secondary market experience that benefits all parties involved. 

## Event Marketing

bigNEON helps anyone market their events by providing automated tools, integrations and APIs for event promoters to easily drive awareness across a variety of channels.

## Event Monitoring and Reporting

bigNEON provides real-time event statistics including sales, attendence, visibility, and more.

Platforms/Interfaces
===========================

 - iOS Native Client `full consumer experience`, `venue scanning/check-in`
 - Android Native Client `full consumer experience`, `venue scanning/check-in`
 - Responsive Web Client `consumer marketing`, `full admin experience`
 - API `all client experiences`, `read-only event api`

Native applications for iOS and Android devices will be developed to provide consumers with the full event discovery, ticket purchasing, ticket transferring/selling and event attendance experience. There must also be a mobile experience for venue operaters to scan and verify tickets as legitimate. It is to be determined if these consumer and operator experiences will exist in the same application, or seperate applications.

A responsive web interface must be developed for any visitor who navigates to the platform via a desktop or mobile web browser. There must be a full organization and event management experience available on the web for Organization Owners and Members. For consumers, the web experience will ultimately drive users to install the native applications where they will be able to purchase tickets to events.

An API must be developed to power these cross-platform client experiences. A read-only version of this API must be accessible to so that organizations/venues/promoters can display their events on their 3rd party websites. Intgrations with popular CMS platforms will be developed.

Entities, Actors, and User Requirements
===========================

## Organization Account Management

### System Administrator

A System Administrator is the owner of the ticketing system (the root user). An System Administrator manages adding and removing Organizations from the system, as well as assigning the Organizations a user who will be the Owner.

### Organization

Organizations are the business entity that operates the events and ticket sales.

### Organization Owner

Every Organization has a single user who is designated as the Owner of the organization. This user has the highest level of access within that organization. An organization owner is responsible for adding and managing the Organization members and has the role of `Organization Admin`

### Organization Member

Organization Members are invited by Organization Owners to help manage the business activities of that Organization. Each Organization Member will be assigned an access level that will determine what activities they are allowed to perform on behalf of that Organization.

#### Organization Member Roles

All Organization Members are given a specific role.
Organization Members can have access to either all, or a limitted subset of events within that organization.

 - `Organization Admin`
 Permission to create & edit Event Details. Abiliy to view Will Call lists, Transaction Detail lists, Event Audit Reports, Event Summary Reports, Box Office Summary, Box Office Detail Reports, Weekly Settlement reports and Ticket Counts. Ability to do refunds and create Comps. Ability to add any level of user.
 - `Organization User`
 Permission to create & edit Event Details. Abiliy to view Will Call lists, Transaction Detail lists, Event Audit Reports, Event Summary Reports, Box Office Summary, Box Office Detail Reports, Weekly Settlement reports and Ticket Counts. Ability to do refunds and create Comps.
 - `Box Office Supervisor`
 Permission to view Event Details, Will Call lists, Transaction Detail lists, Event Audit Reports, Event Summary Reports, Box Office Summary, Box Office Detail Reports, Weekly Settlement reports and Ticket Counts. Ability to do refunds.
 - `Box Office Seller`
 Permission to view Event Details, Will Call lists, Box Office Summary, and Ticket Counts.
 - `Read Only User`
 Permission to view Event Details, Will Call lists, and Event Audit Reports.
 - `Box Office Service Only`
 Permission to Box Office Service.

### URS

 - A system administrator should be able to create a new organization
 - A system administrator should be able to assign a user as an organizations owner
 - A system administrator should be able to add venues to an organization so that the organization can create events at that venue
 - An `Organization Admin` should be able to invite users to their organization as organization members
 - An `Organization Admin` should be able to remove organization members from their organization
 - An `Organization Admin` should be able to update their organizations details
 - An `Organization Admin` should be able to assign a role to organization members
 - An `Organization Admin` should be able to edit other organization members
 - An `Organization Admin` should be able to manage organization members rights to access all events (default) or a limitted subset of events

## User Account Creation and Authentication

### User

A User is a registered account on the system. A User can purchase tickets to an event, view tickets, view purchase history, transfer tickets to/receive tickets from other Users, and can be invited to an Organization to be an Organization Member.

### Visitor

A Visitor is a person who interacts with the system without being logged into an account. A Visitor can browse, search, and view events, login, and create an account.

### URS

 - An System Administrator should be able to configure which login options will be available for users
 - A Visitor should be login using a mobile phone number
 - A Visitor should be create an account using a mobile phone number
 - A Visitor should be able to create an account with their email address and a password
 - A Visitor should be able to logout of the platform
 - A Visitor should be able to reset their account password
 - A Visitor should be able to login to the platform using their facebook account
 - A Visitor should be able to login to the platform using their email address and a password
 - A Visitor should be able to create an account using their facebook account

## Event Mangement

### Event

Events are created by a member of an organization. Each event might have the following attributes:
 - Title
 - Headlining Artist
 - Additional Artist(s)
 - Description
 - Main Image
 - Additional Images
 - Venue
 - Start Date/Time
 - End Date/Time
 - Ticketing Status (ie "On Sale", "Sold Out", "Closed", "Ended")
 - Ticket Allocation(s)

### Ticket Allocation

Each Event can have multiple Ticket Allocations (or ticket "types"). Each Ticket allocation might have the following attributes:
 - Name (ie. "General Admission", "VIP", "GA Early Bird")
 - Description
 - Quantity Available
 - Quantity Reserved
 - Quantity Sold
 - Quantity Used
 - Price
 - On Sale Date/Time
 - Sale End Date/Time

### URS

 - An `Organization Admin` and `Organization User` should be able to create a new event
 - An `Organization Admin` and `Organization User` should be able to create Ticket Allocations for an event
 - An `Organization Admin` and `Organization User` should be able to update the on sale status of an event
 - An `Organization Admin` and `Organization User` to put tickets on hold for an event
 - An `Organization Admin` and `Organization User` to update ticket allocations for an event
 - An `Organization Admin` and `Organization User` should be able to update event details
 - An organization member should be able to search for an event
 - An organization member should be able to see a list of all events

## Event Search/Discovery

### URS

 - A visitor should be able to browse a list of all events
 - A visitor should be able to view event details
 - A visitor should be able to search for an event
 - A visitor should be able to filter events by region
 - A person should be able to scan a QR code to quickly access an event detail page
 - A person should be able to follow a direct link to an event detail page

## Ticket Purchasing Experience

### Ticket

A Ticket is a single digital asset associated with a specific event and user that exists on the blockchain.

### URS

 - Any Visitor should be able to add a specified quantity of tickets to a cart
 - Any Visitor should be able to update the quantity of tickets they want to add to the cart
 - Any Visitor should be able to purchase tickets with a credit card
 - Any Visitor should be able to purchase tickets with Apple Pay
 - Any Visitor should be able to purchase tickets using venmo
 - Any Visitor should be able to view a summary of their purchase after successfully paying for their ticket
 - A User should be able to save their preferred payment method to their account
 - A User should be able to purchase tickets using a previously saved payment method

## User Account Management

### URS

 - A User should be able to view a list of organizations they are members of
 - A User should be able to update their payment preferences
 - A User should be able to update their contact information
 - A User should be able to set notification preferences
 - A User should be able to view their purchase history
 - A User should be able to access their account dashboard

## Ticket Wallet & Transfers

### URS

 - A User should be able to transfer a ticket to another person
 - A User should be able to view all tickets (past and upcoming) that they own
 - A User should be able to view individual ticket details

## Venue Event Check-in Experience

A user will arrive at the event and should be able to gain access to have their tickets verified to gain entry to the event

### URS

 - A User should be able to have their ticket scanned to gain entry to an event
 - A User should be able to share that they are checking into an event with other users
 - An Organization member should be able to look up a users ticket ID to check a User into an event
 - An Organization member should be able to look up a users name to check a User into an event
 - An Organization member should be able to scan a ticket to check a User into an event

## Venue Box Office

A Venue should be able to manage and sell tickets at the venue box office.

### URS

 - An organization member should be able to sell a ticket to an event

## Event Reporting

An Organization member should be able to view reports based on their permissions

### Reports
 - Event Audit Reports
 - Event Summary Reports
 - Box Office Summary
 - Box Office Detail Reports
 - Weekly Settlement reports

## Activity Feed

### URS

 - A User should be able to see a feed of activity shared by people they known
 - A User should be able to share with friends, friends of friends, or globally that they are interested in an event
 - A User should be able to share with friends, friends of friends, or globally that they purchased a ticket to an event
 - A User should be able to share with friends, friends of friends, or globally that they just arrived at an event
 - A User should be able to set up automatic sharing preferences 
 - A User should be able to set up activity feed notification preferences

## User Engagement

An Organization should be able to engage with Users who are attending their events.

### URS

 - An `Organization Admin` and `Organization User` should be able to trigger a push notification to let event attendees know that it is last call at the bar
 - An `Organization Admin` and `Organization User` should be able to schedule a push notification to let event attendees know that it is last call at the bar
 
## Analytics

An Organization may have their own analytics service that they want traffic data sent to

### URS

 - An `Organization Admin` and `Organization User` should be able to integrate with their Google Analytics account to capture basic event page traffic statistics

## Marketing

### URS

 - An `Organization Admin` and `Organization User` should be able to integrate with their Mailchimp email list where customer information will be sent to
 - An `Organization Admin` and `Organization User` should be able to integrate with their SendGrid email list where customer information will be sent to
 - An Organization should be able to list events on their website hosted outside of the platform
 
