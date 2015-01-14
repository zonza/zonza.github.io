---
layout: default
title: SSO Integration
icon: fa-users
tags: learn
---

## <i class="fa {{page.icon}}"></i> {{page.title}}

ZONZA has the ability to integrate with a third-party authentication solution
which can simplify user management and enhance the end-user experience.

#### Terminology

| **SSO**   | **S**ingle **S**ign **O**n. An overarching term for centralized authentication where the user only has to sign in once to access many separate services |
| **SAML**  | A particular method for implementing SSO. A well supported standard. We use [SAML 2.0](http://en.wikipedia.org/wiki/SAML_2.0) |
| **IDP**   | **I**dentity **P**rovider. This is the place that ZONZA will contact if using SSO to find out whether to grant users access |
| **AD**    | **A**ctive **D**irectory. An organisational directory containing user information. Commonly used as the IDP |
| **XML**   | e**X**tensible **M**arkup **L**anguage, the format in which SAML metadata configuration is exchanged |

### How does it work?

<div class="pull-right">
<h3>Live examples</h3>
<p><a href="http://greyworks.zonza.tv">greyworks.zonza.tv <i class="fa fa-external-link"></i></a></p>
<p>Notice how you are immediately redirected to a third-party site which
collects the user credentials. Upon authenticating with Grey, the user will be
seamlessly redirected back to ZONZA with their account configured and logged
in.</p>
<p><a href="http://fg.zonza.tv">fg.zonza.tv <i class="fa fa-external-link"></i></a></p>
<p>Notice how the user has the option of signing in with SSO or a regular
ZONZA account.</p>
<p><a href="http://zonza.tv">zonza.tv <i class="fa fa-external-link"></i></a></p>
<p>The regular ZONZA login screen.</p>
</div>

There are two options for user management in ZONZA:

* (**We manage**, *default*) If the built-in user management is used then
   users are created, approved and deleted within a ZONZA administration panel
   by our helpdesk or optionally by users with administration privileges. If
   this option is chosen then we have the ability to automatically deactivate
   user accounts after a period of inactivity and also to force passwords to be
   reset after X number of days which ensures old users have their access
   revoked. We also block users (by IP) after X repeat failed logins for
   additional security.
* (**Client manages**) Alternatively, ZONZA can delegate user management to a
   third party Single Sign On (SAML SSO) Identity Provider in which case all of
   this can be managed remotely. A major benefit is that the user does not have
   to remember another username and password since they can reuse the same
   credentials they use for their organizations' systems.

We recommend exploring the SSO route if a client already manages users
centrally since it means only managing users in one place and a single identity
for users across their organization and ZONZA. There is also the option of
    combining the two approaches if SSO does not work for all of the clients
    users.

### Great, how do I get started?
Setting up SAML integrations between a client and ZONZA is relatively
straightforward. The minimum we need to get started is to exchange our XML
metadata files describing our service and your IDP. Before proceeding, you will
need to have a SAML Identity Provider (IDP) already in place.

#### We provide:
* Our SAML metadata (always located at
  `https://<client_prefix>.zonza.tv/saml2/metadata`,
  [example](https://zonza.tv/saml2/metadata). This should be configured into
  the client's IDP, preferably using   the URL (since the content can change
  over time)

#### You provide:
* Your corresponding SAML metadata file – This will be an `.xml` file that you
  can download/copy from your IDP
* Confirmation as to what default user group(s) authenticated users get access
  to and what their default ingest group should be. We can also dynamically set
  this based on SAML attributes sent by the IDP (See [Dynamic
  Groups](#dynamic-groups))
* Optional logout URL – This is the URL that end users are redirected to once
  they click logout, this for example could be your intranet
* Option to logout of everything or just ZONZA when the user hits the logout
  button
* Option to allow No-SSO (No Single Sign On) login - This allows end users to
  bypass SSO and authenticate via the regular ZONZA login page e.g. this is
  typically required if the ZONZA instance is going to be accessed by users
  that do not not have an SSO login (e.g. contractors). In these cases,
  clients typically create a No-SSO link on their IDP landing page to
  `https://<client_prefix>.zonza.tv/authentication/login/nosso/`.
* Option to send an email to new users (custom welcome message and title)

To get up and running, configure your IDP with our metadata and provide your
Account Director with the details of your metadata and specified configuration
options.

### Dynamic Groups

Users who login to ZONZA using SSO for the first time are assigned to one more
groups, allowing them to access assets and perform actions within the system.
By default, this list of groups is the same for all SSO users who sign in
which is not always ideal.

For clients who wish to dynamically assign these groups using user details
already stored in the IDP, ZONZA has the capability to use configurable
mappings to determine these groups. These mappings specify which provided
attributes correspond to which existing ZONZA groups.

This means for example that you can send a `country` attribute in the SAML
assertion after authenticating a user and we can configure mappings in ZONZA
such that the user is assigned to a group specifically for users in that
country.

To configure these rules, your account manager will need to be provided with a
list of the desired mappings. These mappings should consist of:

* ZONZA Group Name
* SAML Attribute Field Name
* SAML Attribute Field Value

e.g. 'ACME - EMEA', 'region', 'EMEA'

You can specify as many of these mappings as needed. ZONZA will ignore any
attributes that do not match the configured mappings. Users will be added to
all groups that match. If no matches are found, the user is added to the
default group.

If multiple mappings match, ZONZA will use the first match to determine which
group the user will ingest to.

Each time a user logs in via SSO, ZONZA will re-check the SAML attributes and
**add** any new groups. ZONZA will not remove any existing groups. This is
useful if the useful for example if the users region changes and has been
updated on the IDP.
