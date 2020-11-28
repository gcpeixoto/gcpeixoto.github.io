---
title:  Template
tags:
  - tag
  - tag
  - tag
  - tag
---

Brief text

<!--more-->

Remnant text

## Single image


{% highlight html %}

<div class="card mb-3">
    <img class="card-img-top" src="https://drscdn.500px.org/photo/127767019/q%3D80_m%3D1500/v2?webp=true&sig=dd1fa4580c459472969cd4992068922f311f12cf263cf08b39615cfc1812286b"/>
    <div class="card-body bg-light">
        <div class="card-text">
            The Peak District on a mosty morning.
        </div>
    </div>
</div>

{% endhighlight %}


## Icons

{% highlight markdown %}
{% raw %}

<p class="d-flex align-items-center">
    <span class="icon grey mr-2">
        {% include entypo/clock.svg %}
    </span>
    A clock icon in grey left-aligned
</p>

<p class="d-flex align-items-center">
    A cycle icon in red right-aligned
    <span class="icon red ml-2">
        {% include entypo/cycle.svg %}
    </span>
</p>

{% endraw %}
{% endhighlight %}


## Code

{% highlight liquid %}
{% raw %}
{% highlight <lang_name> %}
    ...code here...
{% endhighlight %}
{% endraw %}
{% endhighlight %}

Supported langs on [this wiki page](https://github.com/jneen/rouge/wiki/List-of-supported-languages-and-lexers).