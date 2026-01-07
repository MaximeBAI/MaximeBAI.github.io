---
layout: default
title: Agentforce
---

## Agentforce deployment

### Embedded Messaging widget

{% if site.embedded_messaging and site.embedded_messaging.enabled %}
<div class="note">
  <p><strong>Tip:</strong> the chat bubble should appear in the bottom corner after the page loads.</p>
</div>

<script type="text/javascript">
  function initEmbeddedMessaging() {
    try {
      embeddedservice_bootstrap.settings.language = "{{ site.embedded_messaging.language | default: 'en_US' }}";
      embeddedservice_bootstrap.init(
        "{{ site.embedded_messaging.org_id }}",
        "{{ site.embedded_messaging.deployment_name }}",
        "{{ site.embedded_messaging.site_url }}",
        {
          scrt2URL: "{{ site.embedded_messaging.scrt2_url }}"
        }
      );
    } catch (err) {
      console.error("Error loading Embedded Messaging: ", err);
    }
  }
</script>
<script
  type="text/javascript"
  src="{{ site.embedded_messaging.bootstrap_url }}"
  onload="initEmbeddedMessaging()"
></script>
{% else %}
To enable the Agentforce chat widget on this page, set `embedded_messaging.enabled: true` in `_config.yml`.
{% endif %}

{% if site.agentforce_iframe_url and site.agentforce_iframe_url != "" %}
<div class="embed-wrap">
  <iframe
    class="embed-frame"
    src="{{ site.agentforce_iframe_url }}"
    title="Agentforce demo"
    loading="lazy"
    referrerpolicy="no-referrer-when-downgrade"
    allow="microphone; clipboard-read; clipboard-write"
  ></iframe>
</div>

If the embed doesn’t load, open it directly: <a href="{{ site.agentforce_iframe_url }}">{{ site.agentforce_iframe_url }}</a>.
{% elsif site.agentforce_url and site.agentforce_url != "" %}
The deployment is available here: <a href="{{ site.agentforce_url }}">{{ site.agentforce_url }}</a>
{% else %}
Set `agentforce_url` (and optionally `agentforce_iframe_url`) in `_config.yml`.
{% endif %}


