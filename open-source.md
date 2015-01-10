---
layout: default
title: Open Source
icon: fa-key
tags: learn
---


## <i class="fa {{page.icon}}"></i> {{page.title}}


ZONZA makes use of many Open Source libraries and components and often
contributes improvements back to the community. We also selectively publish
projects created by our own team. All of our public repositories can be
browsed at [{{site.github.owner_url}}]({{site.github.owner_url}}) and are
listed below:

{% for repo in {{site.github.public_repositories}} %}
* **[{{repo.name}}]({{repo.html_url}})** - {{repo.description}}
{% endfor %}
