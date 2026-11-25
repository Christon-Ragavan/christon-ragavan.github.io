---
title: Let's talk
permalink: /talk/
---

Stuck on a data or AI problem? Thinking about whether an LLM actually fits your use case? Grab a 30-minute slot. No sales pitch, just a conversation.

{% if site.booking_url %}
<p><a class="button" href="{{ site.booking_url }}">Book 30 minutes</a></p>
{% else %}
<p><a class="button" href="mailto:{{ site.author.email }}?subject=Let's%20talk">Email me to set up a time</a></p>
{% endif %}

## Things I'm happy to talk about

- **Is ML or an LLM the right tool here?** Scoping a use case before anyone writes code.
- **RAG and knowledge graphs.** Retrieval that holds up beyond the demo, private LLM deployments.
- **Data platforms.** Databricks, Spark and Delta Lake pipelines, MLOps with MLflow.
- **Time series and sensor data.** Monitoring, anomaly detection, predictive maintenance.
- **Careers in data and ML.** Moving from research to industry, or into a senior role.

## How it works

Send me a couple of lines about what you're working on, and we'll find a time. I'll come prepared with questions; you leave with a clearer next step, even if that step doesn't involve me.

Prefer email? Write to [{{ site.author.email }}](mailto:{{ site.author.email }}).
