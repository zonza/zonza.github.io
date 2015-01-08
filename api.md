---
layout: default
published: true
---


<!--## <i class="fa fa-cloud"></i> Public API-->
<h2 id="public-api"><i class="fa fa-cloud"></i> Public API</h2>

Programmatic access to many of ZONZAs features is possible via our public API.
This allows clients to integrate ZONZA with other systems and perform reporting
tasks for example.

`http://api.zonza.tv` is a RESTful JSON-based API. Access is
controlled using your ZONZA username and API token (visible within ZONZA under your user profile page). As of Jan 2015, it
currently supports:

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

Full documentation is available at [http://api.zonza.tv:8080/docs]()
(password protected). Contact your Account Director for credentials.
