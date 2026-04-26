---
layout: splash
title: "Events"
permalink: /events/
header:
  overlay_color: "#1a1a2e"
  overlay_filter: 0.5
  overlay_image:
  caption: ""
excerpt: "Join us for our upcoming events"
---

<div class="events-page">

  <!-- ============================================================
       RECURRING EVENTS
       ============================================================ -->
  <section class="events-section events-section--recurring">
    <div class="events-section__header">
      <span class="events-section__badge events-section__badge--recurring">Recurring</span>
      <h2 class="events-section__title">Regular Events</h2>
      <p class="events-section__subtitle">
        Ongoing events that happen on a regular (usually biweekly) schedule.
      </p>
    </div>

    <div class="events-grid">
      {% assign recurring_events = site.events | where: "event_type", "recurring" | sort: "sort_order" %}
      {% if recurring_events.size > 0 %}
        {% for event in recurring_events %}
          {% include event-card.html event=event %}
        {% endfor %}
      {% else %}
        <p class="events-empty">No recurring events at the moment. Check back soon!</p>
      {% endif %}
    </div>
  </section>

  <hr class="events-divider" />

  <!-- ============================================================
       ONE-OFF EVENTS
       ============================================================ -->
  <section class="events-section events-section--oneoff">
    <div class="events-section__header">
      <span class="events-section__badge events-section__badge--oneoff">Special</span>
      <h2 class="events-section__title">One-Off Events</h2>
      <p class="events-section__subtitle">
        Annual events and one-off occasions, like integration bees and trivia nights. Updated as the semester goes on.
      </p>
    </div>

    <div class="events-grid">
      {% assign oneoff_events = site.events | where: "event_type", "one-off" | sort: "date" %}
      {% if oneoff_events.size > 0 %}
        {% for event in oneoff_events %}
          {% include event-card.html event=event %}
        {% endfor %}
      {% else %}
        <p class="events-empty">No upcoming special events scheduled. Stay tuned!</p>
      {% endif %}
    </div>
  </section>

</div>

<style>
/* ================================================================
   EVENTS PAGE STYLES
   ================================================================ */

.events-page {
  max-width: 1200px;
  margin: 2rem auto;
  padding: 0 1.5rem;
}

/* Section layout */
.events-section {
  margin-bottom: 3rem;
}

.events-section__header {
  margin-bottom: 2rem;
}

.events-section__title {
  font-size: 1.8rem;
  font-weight: 700;
  margin: 0.5rem 0 0.4rem;
  color: var(--global-theme-color, #0d2b6e);
  border-bottom: none; /* override Minimal Mistakes default */
}

.events-section__subtitle {
  color: #666;
  font-size: 1rem;
  margin: 0;
}

/* Badge labels */
.events-section__badge {
  display: inline-block;
  padding: 0.2rem 0.75rem;
  border-radius: 2rem;
  font-size: 0.72rem;
  font-weight: 700;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}

.events-section__badge--recurring {
  background-color: #e8f5e9;
  color: #2e7d32;
  border: 1px solid #a5d6a7;
}

.events-section__badge--oneoff {
  background-color: #fff3e0;
  color: #e65100;
  border: 1px solid #ffcc80;
}

/* Divider */
.events-divider {
  border: none;
  border-top: 2px dashed #e0e0e0;
  margin: 3rem 0;
}

/* Grid */
.events-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 1.5rem;
}

/* Empty state */
.events-empty {
  color: #999;
  font-style: italic;
  grid-column: 1 / -1;
}

/* ================================================================
   EVENT CARD
   ================================================================ */

.event-card {
  background: #fff;
  border: 1px solid #e8e8e8;
  border-radius: 8px;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  transition: box-shadow 0.2s ease, transform 0.2s ease;
  text-decoration: none;
  color: inherit;
}

.event-card:hover {
  box-shadow: 0 6px 24px rgba(0,0,0,0.1);
  transform: translateY(-3px);
  text-decoration: none;
}

/* Card top colour strip */
.event-card__stripe {
  height: 5px;
  background: linear-gradient(90deg, #0d2b6e, #1a6dd5);
}

.events-section--oneoff .event-card__stripe {
  background: linear-gradient(90deg, #e65100, #ff8f00);
}

.event-card__body {
  padding: 1.25rem 1.5rem;
  flex: 1;
  display: flex;
  flex-direction: column;
}

.event-card__meta {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 0.78rem;
  color: #888;
  margin-bottom: 0.6rem;
  flex-wrap: wrap;
}

.event-card__meta-icon {
  font-size: 0.9rem;
}

.event-card__title {
  font-size: 1.1rem;
  font-weight: 700;
  margin: 0 0 0.5rem;
  color: #1a1a1a;
  line-height: 1.35;
}

.event-card__excerpt {
  font-size: 0.88rem;
  color: #555;
  line-height: 1.55;
  flex: 1;
  margin: 0 0 1rem;
}

.event-card__footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 0.5rem;
  padding-top: 0.75rem;
  border-top: 1px solid #f0f0f0;
}

.event-card__tag {
  font-size: 0.72rem;
  background: #f0f4ff;
  color: #0d2b6e;
  padding: 0.2rem 0.6rem;
  border-radius: 20px;
  font-weight: 600;
}

.events-section--oneoff .event-card__tag {
  background: #fff3e0;
  color: #e65100;
}

.event-card__link {
  font-size: 0.82rem;
  font-weight: 600;
  color: #1a6dd5;
  text-decoration: none;
}

.event-card__link:hover {
  text-decoration: underline;
}

/* Responsive */
@media (max-width: 640px) {
  .events-grid {
    grid-template-columns: 1fr;
  }
}
</style>
