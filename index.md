---
title: Home
---
{% include favicon.html %}
{% include navigation.html %}

# Welcome!

## Current Weather

Last updated: {{ site.data.weather.update_time }}

{% assign sorted = site.data.stations | sort %}
{% for station_hash in sorted %}
{% assign station = station_hash[0] %}
{% assign station_data = station_hash[1] %}
{{ station }}: {{ station_data.flight_rules }} {{ station_data.altimeter.repr }}

{% endfor %}

## Debug

### Page url
{{ page.url }}

