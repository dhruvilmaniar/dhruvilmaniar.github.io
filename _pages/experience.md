---
layout: archive
title: "Experience"
permalink: /experience/
author_profile: true
---

{% include base_path %}

<div class="timeline">
  {% for job in site.data.experience %}
  <div class="timeline__company">

    <div class="timeline__company-header">
      <div class="timeline__company-dot"></div>
      <div class="timeline__company-info">
        <h2 class="timeline__company-name">
          {% if job.url %}
            <a href="{{ job.url }}" target="_blank" rel="noopener">{{ job.company }}</a>
          {% else %}
            {{ job.company }}
          {% endif %}
        </h2>
        {% if job.location %}
          <span class="timeline__company-location">
            <i class="fas fa-location-dot"></i> {{ job.location }}
          </span>
        {% endif %}
      </div>
    </div>

    <div class="timeline__roles">
      {% for role in job.roles %}
      <div class="timeline__role">
        <div class="timeline__role-header">
          <span class="timeline__role-title">{{ role.title }}</span>
          <span class="timeline__role-period">{{ role.period }}</span>
        </div>
        {% if role.description %}
          <p class="timeline__role-description">{{ role.description }}</p>
        {% endif %}
        {% if role.highlights %}
          <ul class="timeline__role-highlights">
            {% for item in role.highlights %}
              <li>{{ item }}</li>
            {% endfor %}
          </ul>
        {% endif %}
        {% unless forloop.last %}
          <div class="timeline__role-divider"></div>
        {% endunless %}
      </div>
      {% endfor %}
    </div>

  </div>
  {% endfor %}
</div>

<style>
/* ── Timeline container ─────────────────────────────────── */
.timeline {
  position: relative;
  padding-left: 2rem;
}

.timeline::before {
  content: "";
  position: absolute;
  left: 0.55rem;
  top: 0.5rem;
  bottom: 0.5rem;
  width: 2px;
  background: var(--border-color, #ddd);
}

/* ── Company block ──────────────────────────────────────── */
.timeline__company {
  position: relative;
  margin-bottom: 2.5rem;
}

.timeline__company-header {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
  margin-bottom: 0.75rem;
}

.timeline__company-dot {
  position: absolute;
  left: -2rem;
  top: 0.35rem;
  width: 1.1rem;
  height: 1.1rem;
  border-radius: 50%;
  background: #4a90e2;
  border: 2px solid var(--background-color, #fff);
  box-shadow: 0 0 0 2px #4a90e2;
  flex-shrink: 0;
  z-index: 1;
}

.timeline__company-name {
  font-size: 1.25rem;
  font-weight: 700;
  margin: 0 0 0.15rem 0;
}

.timeline__company-name a {
  color: inherit;
  text-decoration: none;
}

.timeline__company-name a:hover {
  color: #4a90e2;
  text-decoration: underline;
}

.timeline__company-location {
  font-size: 0.85rem;
  opacity: 0.65;
}

.timeline__company-location i {
  margin-right: 0.25rem;
}

/* ── Roles inside a company ─────────────────────────────── */
.timeline__roles {
  background: var(--code-background-color, #f8f8f8);
  border: 1px solid var(--border-color, #e0e0e0);
  border-radius: 8px;
  padding: 1rem 1.25rem;
}

.timeline__role {
  padding: 0.25rem 0;
}

.timeline__role-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 0.25rem;
  margin-bottom: 0.5rem;
}

.timeline__role-title {
  font-weight: 600;
  font-size: 1rem;
  color: #4a90e2;
}

.timeline__role-period {
  font-size: 0.82rem;
  opacity: 0.7;
  font-style: italic;
}

.timeline__role-description {
  font-size: 0.9rem;
  margin: 0.4rem 0 0.6rem 0;
  line-height: 1.6;
}

.timeline__role-highlights {
  margin: 0.4rem 0 0.5rem 1.2rem;
  padding: 0;
  font-size: 0.88rem;
  line-height: 1.65;
}

.timeline__role-highlights li {
  margin-bottom: 0.3rem;
}

.timeline__role-divider {
  border: none;
  border-top: 1px dashed var(--border-color, #ddd);
  margin: 0.85rem 0;
}
</style>
