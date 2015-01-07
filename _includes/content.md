---
title: Homepage
layout: default
---

Public API
==========

http://api.zonza.tv is a fully RESTful JSON-based API accessed using a ZONZA username and API token. It currently supports:

Items:
------
* Upload (non-accelerated, chunked)
* Download (non-accelerated, chunked)
* Metadata view and edit
* Fulltext and field-level search (including negation, sorting and pagination)
* Search faceting
* Search by date ranges
* Access to supporting files
* Still generation and view (full frame captures from video or pages from presentations etc.)
* Thumbnail geniieration and view (including custom thumbnails, e.g. For setting preview on a ZIP)
* Transcoding to
* Export to FTP location
* Deletion of assets, versions, transcodes
* Support for multiple item versions

<!--Jobs:-->
<!--Viewing the status of submitted ingests and other async tasks-->

<!--Collections:-->
<!--Create and view collections-->
<!--Deleting collections-->
<!--Item addition and removal-->
            <!--<p>Full documentation is available at <a href="http://api.zonza.tv:8080/docs">http://api.zonza.tv:8080/docs</a> (password protected). Contact your Account Director for credentials.</p>-->
            <!--<h2><a class="anchor" name="sso-integration" aria-hidden="true"><span class="octicon octicon-link"></span></a>SSO Integration</h2>-->
            <!--<h3>Why would I want this?</h3>-->
            <!--<p>ZONZA has the ability to integrate with third-party authentications solution which can simplify user management and enhance the end-user experience.</p>-->
            <!--<h4>Terminology</h4>-->
            <!--<table>-->
                <!--<tr><td><b>SSO</b></td><td><b>S</b>ingle <b>S</b>ign <b>O</b>n. An overarching term for centralized authentication where the user only has to sign in once to access many separate services</td></th>-->
                <!--<tr><td><b>SAML</b></td><td>A particular method for implementing SSO. A well supported standard. We use <a href="http://en.wikipedia.org/wiki/SAML_2.0" target="_blank">SAML 2.0</a></td></tr>-->
                <!--<tr><td><b>IDP</b></td><td><b>Id</b>entity <b>P</b>rovider. This is the place that ZONZA will contact if using SSO to find out whether to grant users access</td></tr>-->
                <!--<tr><td><b>AD</b></td><td><b>A</b>ctive <b>D</b>irectory. An organisational directory containing user information. Commonly used as the IDP</td></tr>-->
                <!--<tr><td><b>XML</b></td><td>e<b>X</b>tensible <b>M</b>arkup <b>L</b>anguage, the format in which SAML metadata configuration is exchanged</td></tr>-->
            <!--</table>-->
            <!--<h3>How does it work?</h3>-->
            <!--<p>There are two options for user management in ZONZA:</p>-->
            <!--<ol>-->
                <!--<li>(<strong>We manage</strong>, <i>default</i>) If the built-in user management is used then users are created, approved and deleted within a ZONZA administration panel by our helpdesk or optionally by users with administration privileges. If this option is chosen then we have the ability to automatically deactivate user accounts after a period of inactivity and also to force passwords to be reset after X number of days which ensures old users have their access revoked. We also block users (by IP) after X repeat failed logins for additional security.</li>-->
                <!--<li>(<strong>Client manages</strong>) Alternatively, ZONZA can delegate user management to a third party Single Sign On (SAML SSO) Identity Provider in which case all of this can be managed remotely. A major benefit is that the user does not have to remember another username and password since they can reuse the same credentials they use for their organizations' systems.</li>-->
            <!--</ol>-->
            <!--<p>We recommend exploring the SSO route if a client already manages users centrally since it means only managing users in one place and a single identity for users across their organization and ZONZA. There is also the option of combining the two approaches if SSO does not work for all of the clients users.</p>-->
            <!--<h3>Great, how do we get started?</h3>-->
            <!--<p>Setting up SAML integrations between a client and ZONZA is relatively straightforward. The minimum we need to get started is to exchange our XML metadata files describing our service and your IDP.</p>-->
            <!--<p>Before proceeding, you will need to have a SAML Identity Provider (IDP) already in place.</p>-->
            <!--<h4>We provide:</h4>-->
            <!--<ul>-->
                <!--<li>Our SAML metadata (always located at https://<client_prefix>zonza.tv/saml2/metadata, <a href="https://zonza.tv/saml2/metadata">example</a>). This should be configured into the client's IDP, preferably using the URL (since the content can change over time)</li>-->
            <!--</ul>-->
            <!--<h4>You provide:</h4>-->
            <!--<ul>-->
                <!--<li>Their corresponding SAML metadata file – This will be an .xml file that the client can download/copy from their IDP</li>-->
                <!--<li>Confirmation as to what default user group(s) authenticated users get access to and what their default ingest group should be. We can also dynamically set this based on SAML attributes sent by the IDP</li>-->
                <!--<li>Optional logout URL – This is the URL that end users are redirected to once they click logout, this for example could be a client intranet</li>-->
                <!--<li>Option to logout of everything or just ZONZA when the user hits the logout button</li>-->
                <!--<li>Option to allow NOSSO (No Single Sign On) login - This allows end users to bypass SAML and authenticate via the regular ZONZA login page e.g. this is typically required if the ZONZA instance is going to be accessed by users that do not not have a https://<client_prefix>.zonza.tv/authentication/login/nosso/ SAML login. For these types of examples clients typically create a NOSSO link on their IDP landing page e.g.</li>-->
                <!--<li>Option to send an email to new users (custom welcome message and title)</li>-->
            <!--</ul>-->
            <!--<h2><a class="anchor" name="open-source" aria-hidden="true"><span class="octicon octicon-link"></span></a>Open Source</h2>-->
