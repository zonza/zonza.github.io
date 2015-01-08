---
layout: default
published: true
---


<h2 id="public-api"><i class="fa fa-code"></i> Public API</h2>

<div class="pull-right">
<h3>Recent Use-cases</h3>
<ul>
<li>Push product imagery to a Product Catalog (Hybris)</li>
<li>Pull asset data into a SQL database for reporting</li>
<li>Publish showcased assets on a third-party CMS</li>
<li>Bulk-update metadata for specific assets</li>
</ul>
<p>See example code at <a href="https://github.com/zonza/zonza-api-examples">https://github.com/zonza/zonza-api-examples</a></p>
</div>

Programmatic access to many of ZONZAs features is possible via our public API.
This allows clients to integrate ZONZA with other systems and perform reporting
tasks for example.

`http://api.zonza.tv` is a RESTful JSON-based API. Access is controlled using
your ZONZA username and API token (visible within ZONZA under your user
profile page).

Full documentation is available at
[http://api.zonza.tv:8080/docs/](http://api.zonza.tv:8080/docs/) (password
protected). Contact your Account Director for credentials.

As of Jan 2015, the API supports:

### Items:
* Upload (non-accelerated, chunked)
* Download (non-accelerated, chunked)
* Metadata view and edit
* Fulltext and field-level search (including negation, sorting and pagination)
* Search faceting
* Search by date ranges
* Access to supporting files
* Still generation and view (full frame captures from video or pages from
  presentations etc.)
* Thumbnail generation and view (including custom thumbnails, e.g. For
  setting preview on a ZIP)
* Transcoding to
* Export to FTP location
* Deletion of assets, versions, transcodes
* Support for multiple item versions

### Jobs:
* Viewing the status of submitted ingests and other async tasks

### Collections:
* Create and view collections
* Deleting collections
* Item addition and removal
