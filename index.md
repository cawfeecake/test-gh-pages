---
title: Home
---
{% include favicon.html %}
{% include navigation.html %}

# Weather

Last updated: {{ site.data.weather.update_time }}

{% assign sorted = site.data.metars | sort %}
{% for station_hash in sorted %}
{% assign station = station_hash[0] %}
{% assign station_data = station_hash[1] %}
## {{ station }} ({{ station_data.flight_rules }})

Field elevation: {{ site.data.stations[station].elevation_ft }} ft -- Pressure: {{ station_data.pressure_altitude }} {{ station_data.units.altitude }}; Density: {{ station_data.density_altitude }} {{ station_data.units.altitude }}

Visibility: {{ station_data.visibility.value }} {{ station_data.units.visibility }} 

{% assign ceilings = station_data.clouds %}
{% if ceilings.size > 0 %}
Ceilings
{% for ceiling in ceilings %}
  * {{ ceiling.type }} @ {{ ceiling.altitude }} {{ station_data.units.altitude }}
{% endfor %}
{% endif %}

Altimeter: {{ station_data.altimeter.value }} {{ station_data.units.altimeter }}

Wind: {% if station_data.wind_speed and station_data.wind_speed.value > 0 %}
{{ station_data.wind_direction.repr }} @ {{ station_data.wind_speed.value }} {{ station_data.units.wind_speed }}
{% if station_data.wind_gust %}
 gusting {{ station_data.wind_gust.value }} {{ station_data.units.wind_speed }}
{% endif %}
{% else %}
calm
{% endif %}

Temps: {{ station_data.temperature.value }} {{ station_data.units.temperature }} / dewpoint {{ station_data.dewpoint.value }}

{% endfor %}

---

### Debug

#### Page url
{{ page.url }}

