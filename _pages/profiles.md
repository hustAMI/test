---
layout: profiles
permalink: /people/
title: people
description: members of the lab or group
nav: true
nav_order: 7

<div class="lab-members-page">

  {% for section in site.data.lab_members %}
  <section class="lab-section">
    <h2 class="lab-section-title">{{ section.title }}</h2>

    <div class="lab-grid {% if section.members.size == 1 %}lab-grid-one{% endif %}">
      {% for member in section.members %}
      <div class="lab-card">

        <div class="lab-photo-box">
          <img src="{{ member.photo | relative_url }}" alt="{{ member.name_cn }}">
        </div>

        <div class="lab-info">
          <div class="lab-name-cn">{{ member.name_cn }}</div>
          <div class="lab-name-en">{{ member.name_en }}</div>

          <div class="lab-divider"></div>

          <div class="lab-role">{{ member.role }}</div>

          {% if member.note %}
          <div class="lab-note">{{ member.note }}</div>
          {% endif %}
        </div>

        {% if member.email %}
        <a class="lab-email" href="mailto:{{ member.email }}">
          {{ member.email }}
        </a>
        {% endif %}

        <a class="lab-more" href="{{ member.detail | relative_url }}" aria-label="查看{{ member.name_cn }}详细信息">
          ›
        </a>

      </div>
      {% endfor %}
    </div>
  </section>
  {% endfor %}

</div>

<style>
.lab-members-page {
  margin-top: 1.5rem;
}

.lab-section {
  margin-bottom: 2.2rem;
}

.lab-section-title {
  font-size: 1rem;
  font-weight: 700;
  color: #006eb8;
  border-top: 1px dashed #cfcfcf;
  padding-top: 0.75rem;
  margin-bottom: 1rem;
}

.lab-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(230px, 1fr));
  gap: 1rem;
}

.lab-grid-one {
  grid-template-columns: minmax(260px, 330px);
}

.lab-card {
  position: relative;
  display: grid;
  grid-template-columns: 105px 1fr;
  column-gap: 0.75rem;
  min-height: 150px;
  padding: 0.75rem;
  border: 2px solid #3d6d9d;
  border-radius: 10px;
  background: #ffffff;
  box-shadow: 0 2px 5px rgba(0,0,0,0.04);
}

.lab-photo-box img {
  width: 95px;
  height: 120px;
  object-fit: cover;
  border-top: 1px solid #e0e0e0;
}

.lab-info {
  text-align: center;
  padding-top: 0.25rem;
  padding-right: 0.25rem;
}

.lab-name-cn {
  font-size: 1rem;
  font-weight: 700;
  color: #111;
}

.lab-name-en {
  font-size: 0.8rem;
  font-weight: 600;
  color: #111;
  margin-top: 0.15rem;
}

.lab-divider {
  width: 100%;
  height: 3px;
  background: #1e5a89;
  margin: 0.8rem 0 0.7rem;
}

.lab-role {
  font-size: 0.85rem;
  color: #333;
}

.lab-note {
  font-size: 0.78rem;
  color: #333;
  margin-top: 0.25rem;
  line-height: 1.35;
}

.lab-email {
  position: absolute;
  left: 0.55rem;
  bottom: 0.35rem;
  font-size: 0.75rem;
  color: #2c5e8b;
  text-decoration: none;
}

.lab-email:hover {
  text-decoration: underline;
}

.lab-more {
  position: absolute;
  right: 0.55rem;
  bottom: 0.45rem;
  width: 20px;
  height: 20px;
  line-height: 17px;
  text-align: center;
  border-radius: 5px;
  background: linear-gradient(#3da1d9, #1c6095);
  color: #ffffff !important;
  font-size: 1.25rem;
  font-weight: 700;
  text-decoration: none;
}

.lab-more:hover {
  filter: brightness(1.1);
  text-decoration: none;
}

html[data-theme="dark"] .lab-card {
  background: #1f1f1f;
  border-color: #5b86b0;
}

html[data-theme="dark"] .lab-name-cn,
html[data-theme="dark"] .lab-name-en,
html[data-theme="dark"] .lab-role,
html[data-theme="dark"] .lab-note {
  color: #eeeeee;
}

@media (max-width: 900px) {
  .lab-grid {
    grid-template-columns: repeat(2, minmax(230px, 1fr));
  }
}

@media (max-width: 600px) {
  .lab-grid,
  .lab-grid-one {
    grid-template-columns: 1fr;
  }

  .lab-card {
    grid-template-columns: 95px 1fr;
  }

  .lab-photo-box img {
    width: 85px;
    height: 110px;
  }
}
</style>
