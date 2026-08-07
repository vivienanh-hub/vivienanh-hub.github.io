---
layout: page
title: Van-Anh Nguyen
subtitle: Senior Product Manager &middot; Marketplaces &middot; B2B SaaS &middot; AI Products
ext-css:
  - "https://fonts.googleapis.com/css2?family=Source+Sans+3:wght@400;600;700;800&display=swap"
---

<div class="home-alt" markdown="0">

<section class="home-alt-intro home-fresh-intro">
  <figure class="home-alt-portrait home-fresh-portrait">
    <img src="/assets/img/VA.jpg" alt="Van Anh Nguyen">
  </figure>
  <div class="home-alt-intro__copy">
    <p>A personal record of product work across software, monetization, marketplaces, and applied AI. Projects and field notes sit beside career history, including work that is still being tested, changed, or understood.</p>
    <div class="home-alt-actions">
      <a href="/experience/">Experience</a>
      <a href="/projects/">Projects</a>
      <a href="/notes/">Field notes</a>
    </div>
  </div>
</section>

<section class="home-alt-path home-fresh-path">
  <div class="home-alt-section-head">
    <p class="home-alt-kicker">Work over time</p>
    <h2>These are the parts of the path that continue to shape the work.</h2>
  </div>

  <div class="home-alt-timeline home-fresh-timeline">
    <section class="home-alt-milestone home-alt-milestone--teal">
      <h3>Foundations</h3>
      <p>Software delivery and business analysis came first, grounding product decisions in workflows, constraints, data, and implementation detail.</p>
    </section>

    <section class="home-alt-milestone home-alt-milestone--amber">
      <h3>Early product work</h3>
      <p>Roadmaps, workflow design, releases, demos, and onboarding across several B2B products. Product management built on the earlier foundation in delivery and analysis.</p>
    </section>

    <section class="home-alt-milestone home-alt-milestone--blue">
      <h3>Marketplace work</h3>
      <p>Seller products, monetization, partner programs, and automotive marketplace work, across both individual product and team leadership roles.</p>
    </section>

    <section class="home-alt-milestone home-alt-milestone--rose">
      <h3>AI products and practice</h3>
      <p>AI products viewed through real work: where they help, where they fall short, and what still needs checking.</p>
    </section>
  </div>
</section>

<section class="home-alt-project home-fresh-project">
  <div class="home-alt-section-head">
    <p class="home-alt-kicker">Projects</p>
    <h2>Product systems and experiments.</h2>
  </div>
  <div class="home-fresh-project-list">
    <article class="home-fresh-project-item">
      <h3>Learning Loop</h3>
      <p>An AI-assisted system for studying over time: planning what to learn, testing understanding, keeping useful memory, and reviewing what changes.</p>
      <div class="home-alt-actions">
        <a href="https://github.com/vivienanh-hub/learning-loop">View project</a>
        <a href="/2026-08-02-learning-loop/">Read note</a>
      </div>
    </article>
  </div>
</section>

<section class="home-alt-notes home-fresh-notes">
  <div class="home-alt-section-head">
    <p class="home-alt-kicker">Latest field notes</p>
    <h2>Notes on product work, learning, and AI practice.</h2>
  </div>

  <ul>
  {% for post in site.posts limit: 3 %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      <span>{{ post.date | date: "%B %-d, %Y" }}</span>
      {% if post.subtitle %}<p>{{ post.subtitle }}</p>{% endif %}
    </li>
  {% endfor %}
  </ul>

  <a class="home-alt-text-link" href="/notes/">All field notes</a>
</section>

</div>
