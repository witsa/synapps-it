---
nav_order: 30
---

# Synapps Studio

Télécharger la version actuelle [{{ site.data.releases[0].version }}](https://github.com/witsa/synapps/releases/download/{{ site.data.releases[0].version }}/synapps-studio-setup.zip)

Voir la [Note de version]({{ site.data.releases[0].notes }}{{ site.data.releases[0].version }}){:target="_blank"}

# Historique des versions

| Version | Date |
|---------|-----|-|
{% for release in site.data.releases %}| [**{{ release.version }}**]({{ release.notes }}{{ release.version }}){:target="_blank"} | {{ release.date }} |
{% endfor %}
