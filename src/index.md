---
layout: default
title: Home
---

<!-- BIO -->
<section id="home" class="sa-section">
  <div class="bio-copy">
    <h1 class="sa-h1">Bio</h1>
    <p>
      My name is Sam Davis Omekara. I’m a Software Engineer at Microsoft on the Web Platform team. I have the privilege to work on arguably the most used software on the planet: the browser. I believe the browser is where a lot of Computer science concepts come to life. I find myself constantly trying to balance curiosity with not getting overwhelmed or stuck in rabbit holes. It’s amazing.
    </p>
    <p>
      Before Microsoft, I studied Computer Science and Mathematics at Philander Smith University. There, I served as a Teaching Assistant, led teams to represent the college in national competitions, and graduated as valedictorian.
    </p>
    <p>
      Today, my work spans accessibility and rendering in Chromium. I hold a Chromium committer status and have contributed about 200 changes in two years, collaborating with engineers across companies and participating in web standards as a member of the W3C CSS Working Group.
    </p>
    <p>
      Outside of school and work, I gravitate toward community building. I support local small businesses through seasonal markets, help organize events for artists, and create spaces where people can come together. I’m also a supporter of Arsenal Football Club. 
    </p>

    <ul class="bio-links">
      <li><a href="https://www.linkedin.com/in/samdavisomekara" target="_blank" rel="noopener">LinkedIn</a></li>
      <li><a href="https://github.com/oSamDavis" target="_blank" rel="noopener">GitHub</a></li>
      <li><a href="mailto:osamdavis@example.com">Email</a></li>
      <li><a href="https://drive.google.com/file/d/1QePGeSlVErEXBecMGDeJLZkjKM0Sz9_h/view?usp=sharing">Resume</a></li>
    </ul>

  </div>

  <figure class="bio-photo">
    <img src="/assets/images/osam.jpg" alt="Sam Davis Omekara">
  </figure>
</section>

<!-- EXPERIENCES -->
<section id="experiences" class="sa-section">
  <h2 class="sa-h2">Experiences</h2>
  {% assign sorted = site.experiences | sort: 'weight' %}
  <div class="sa-list xp-list">
    {% for item in sorted %}
      <article class="sa-item xp">
        <div class="xp-body">
          <h3 class="sa-title">{{ item.title }}</h3>

          {% if item.summary %}
            <p class="sa-dek xp-summary">{{ item.summary }}</p>
          {% endif %}

          {% if item.bullets and item.bullets.size > 0 %}
            <ul class="sa-bullets xp-bullets">
              {% for bullet in item.bullets %}
                <li>{{ bullet }}</li>
              {% endfor %}
            </ul>
          {% endif %}

          {% if item.links and item.links.size > 0 %}
            <p class="sa-links xp-links">
              {% for link in item.links %}
                <a href="{{ link.url }}">{{ link.text }}</a>{% unless forloop.last %}<span class="sa-sep"> · </span>{% endunless %}
              {% endfor %}
            </p>
          {% endif %}
        </div>

        {% if item.image %}
          <figure class="xp-media">
            <img src="{{ item.image }}" alt="{{ item.image_alt | default: item.title }}" loading="lazy">
          </figure>
        {% endif %}
      </article>
    {% endfor %}

  </div>
</section>

<!-- PROJECTS -->
<section id="projects" class="sa-section">
  <h2 class="sa-h2">Projects</h2>

  <ul class="sa-list projects-list">
    {% assign sorted = site.projects | sort: "date" | reverse %}
    {% for item in sorted limit:5 %}
      <li class="sa-item">
        <div class="sa-linkline">
          <strong>
            {% if item.external_link %}
              <a href="{{ item.external_link }}" target="_blank" rel="noopener">
                {{ item.title }}
              </a>
            {% else %}
              <a href="{{ item.url | relative_url }}">
                {{ item.title }}
              </a>
            {% endif %}
          </strong>
        </div>
        {% if item.core_tech %}
          <span class="tech"> · {{ item.core_tech | join: ", " }}</span>
        {% endif %}
        {% if item.summary %}
          <div class="summary sa-dek">{{ item.summary }}</div>
        {% endif %}
      </li>
    {% endfor %}
  </ul>

  <p class="sa-see-all"><a href="{{ '/projects/' | relative_url }}">See all →</a></p>
</section>


<!-- RESEARCH -->
<section id="research" class="sa-section">
  <h2 class="sa-h2">Research</h2>
  <ul class="sa-list research-list">
    {% assign items = site.research | sort: "date" | reverse %}
    {% for item in items limit:5 %}
<li class="sa-item">
  <div class="sa-linkline">
    <strong>
      {% if item.external_url %}
        <a href="{{ item.external_url }}" target="_blank" rel="noopener">{{ item.title }}</a>
      {% else %}
        <a href="{{ item.url | relative_url }}">{{ item.title }}</a>
      {% endif %}
    </strong>
  </div>
  {% if item.summary %}
    <div class="summary sa-dek">{{ item.summary }}</div>
  {% endif %}
  {% if item.venue or item.date %}
    <div class="meta">
      {{ item.venue }}{% if item.venue and item.date %} · {% endif %}
      {% if item.date %}{{ item.date | date: '%Y' }}{% endif %}
    </div>
  {% endif %}
</li>
    {% endfor %}
  </ul>
</section>

<!-- VOLUNTEERING -->
<section id="volunteering" class="sa-section">
  <h2 class="sa-h2">Volunteering</h2>
  <ul class="sa-list">
    {% for item in site.volunteering limit:10 %}
      <li class="sa-item">
        <strong>{{ item.title }}</strong>
        –
        <div class="sa-linkline">

          {% if item.link %}
            <a class="org-link" href="{{ item.link }}" target="_blank" rel="noopener">{{ item.org }}</a>
          {% else %}
            {{ item.org }}
          {% endif %}

        </div>
        <span class="meta">({{ item.date | date: "%Y" }})</span>
        <div class="sa-dek">{{ item.description }}</div>
      </li>
    {% endfor %}

  </ul>
</section>

<!-- WRITING -->
<section id="writing" class="sa-section">
  <h2 class="sa-h2">Writing</h2>
  <ul class="writing-list">
    {% assign recent = site.writing | sort: "date" | reverse %}
    {% for item in recent limit:5 %}
      <li class="sa-linkrow">
        <span class="date">{{ item.date | date: "%Y-%m-%d" }}</span>
        <a href="{{ item.url | relative_url }}">{{ item.title }}</a>
      </li>
    {% endfor %}
  </ul>
  <p class="sa-see-all"><a href="{{ '/writing/' | relative_url }}">See all →</a></p>
</section>

<!-- FEATURED -->
<section id="featured" class="sa-section">
  <h2 class="sa-h2">Featured</h2>
  {% assign items = site.data.featured | sort: "date" | reverse %}
  <div class="featured-grid">
    {% for f in items %}
      <div class="featured-card">
        <div class="featured-meta">
          <span class="badge badge-{{ f.kind | downcase }}">{{ f.kind }}</span>
          <time datetime="{{ f.date | date_to_xmlschema }}">{{ f.date | date: "%Y" }}</time>
        </div>

        <a class="featured-title" href="{{ f.href }}" target="_blank" rel="noopener">
          {{ f.title }}
        </a>

        {% if f.org %}<div class="featured-org">{{ f.org }}</div>{% endif %}

        {% if f.image %}
          <a href="{{ f.href }}" target="_blank" rel="noopener" class="featured-thumb">
            <img src="{{ f.image | relative_url }}" alt="{{ f.title | escape }}">
          </a>
        {% endif %}

        {% if f.blurb %}
          <p class="featured-blurb">{{ f.blurb }}</p>
        {% endif %}
      </div>
    {% endfor %}

  </div>
</section>
