---
layout: default
title: Public API
icon: fa-code
tags: learn
---


## <i class="fa {{page.icon}}"></i> {{page.title}}

<div class="pull-right">
<h3>Recent Use-cases</h3>
<ul>
<li>Push product imagery to a Product Catalog (Hybris)</li>
<li>Pull asset data into a SQL database for reporting</li>
<li>Publish showcased assets on a third-party CMS</li>
<li>Bulk-update metadata for specific assets</li>
</ul>
</div>

Programmatic access to many of ZONZAs features is possible via our public API.
This allows clients to integrate ZONZA with other systems or perform reporting
tasks for example. `http://api.zonza.tv` is a RESTful JSON-based API and thus
can be used from any programming language or any HTTP client (including
browser extensions such as [Postman](http://www.getpostman.com/)).

### Great, how do I get started?

Access is controlled using your ZONZA username and API token which is visible
on your ZONZA user profile page. Your account must also have permission to
make API calls so if you do not see your API token then please contact your
Account Director. Once you've got your credentials, simply start making HTTP
requests using the appropriate headers, for example:

{% highlight bash %}
$ curl \
    -H "Bork-Token: <YOUR_TOKEN>" \
    -H "Bork-Username: <YOUR_USERNAME>" \
    http://api.zonza.tv:8080/v0/item
{
  "hits": "1",
  "item": [
      {
        "id": "VX-336335",
        "url": "http://api.zonza.tv:8080/v0/item/VX-336335"
      }
    ]
}
{% endhighlight %}

Check out example code at
[https://github.com/zonza/zonza-api-examples](https://github.com/zonza/zonza-api-examples)
Full documentation is available at
[http://api.zonza.tv:8080/docs/](http://api.zonza.tv:8080/docs/) (password
protected). Contact your Account Director for credentials.

### Screencast

<style>
.embed-container {
    position: relative;
    padding-bottom: 56.25%;
    height: 0;
    overflow: hidden;
    max-width: 100%;
}
.embed-container iframe, .embed-container object, .embed-container embed {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}
</style>
<div class='embed-container'><iframe src='http://player.vimeo.com/video/117852769' frameborder='0' webkitAllowFullScreen mozallowfullscreen allowFullScreen></iframe></div>


### Features

As of Jan 2015, the API supports:

#### Items:
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

#### Jobs:
* Viewing the status of submitted ingests and other async tasks

#### Collections:
* Create and view collections
* Deleting collections
* Item addition and removal
