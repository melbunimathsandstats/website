---
title: "Melbourne Uni Maths + Stats"
layout: splash
header:
  overlay_image: assets/melb_uni_maths_and_stats_cover.jpeg
  excerpt: ???
  overlay_color: "#000"
  overlay_filter: "0.5"
  actions:
    - label: "Join us?"
      url: "https://umsu.unimelb.edu.au/buddy-up/clubs/clubs-listing/join/mums/"
      excerpt: "We're a student run club at the University of Melbourne welcoming anyone with an interest in mathematics and statistics!"
feature_row:
  - image_path: assets/mums-banner.png
    alt: "placeholder image 1"
    title: "Resources"
    excerpt: "Problems from competitions and notes from seminars"
  - image_path: assets/mums-room.png
    alt: "placeholder image 2"
    title: "About us"
    excerpt: "Find out about the club and meet the committee."
    url: /about/
    btn_label: "Read More"
    btn_class: "btn--inverse"
  - image_path: assets/WICC1.JPG
    alt: "placeholder image 3"
    title: "Events"
    excerpt: "Annual and weekly events, such as our fortnightly board games night!"
    url: /events/
    btn_label: "Read more"
    btn_class: "btn--inverse"
    author_profile: true
sponsors:
  - image_path: assets/umsu_logo.avif
    excerpt: We are an UMSU affiliated club
  - image_path: assets/unimelb_logo.avif
    excerpt: School of Maths & Stats - supporter
  - image_path: assets/jane_st_logo.avif
    excerpt: Jane Street - platinum sponsor
sponsors2:
  - image_path: assets/optiver_logo.avif
    excerpt: Optiver - gold sponsor
  - image_path: assets/imc_logo.avif
    excerpt: IMC - gold sponsor
  - image_path: assets/sig_logo.avif
    excerpt: Susquehanna - gold sponsor
sponsors3:
  - image_path: assets/Taylor_Fry_Logo_edited.avif
    excerpt: Taylor Fry - gold sponsor
---

# The MUMS club
We're a student run club at the University of Melbourne welcoming anyone with an interest in mathematics and statistics!
We hold regular social, academic and career event to connect you to like-minded peers and bring you interesting mathematical content.

<div style="--teaser-height: 250px">
{% include feature_row %}
</div>
## Event calendar
<iframe id="cal-frame" style="width:100%; height:680px; border:none;"></iframe>

<script>
const html = `
<!DOCTYPE html>
<html>
<head>
  <link href='https://cdn.jsdelivr.net/npm/fullcalendar@6.1.20/index.global.min.css' rel='stylesheet' />
  <script src='https://cdn.jsdelivr.net/npm/fullcalendar@6.1.20/index.global.min.js'><\/script>
  <script src="events.js"><\/script>
  <style>
    body { margin: 0; padding: 0; font-family: sans-serif; }
    #calendar { height: 670px; padding: 10px; }
  </style>
</head>
<body>
  <div id="calendar"></div>
  <script>
    document.addEventListener('DOMContentLoaded', function() {
      const calendar = new FullCalendar.Calendar(document.getElementById('calendar'), {
initialView: 'dayGridMonth',
        height: 650,
        headerToolbar: {
          left: 'prev,next today',
          center: 'title',
          right: 'dayGridMonth,timeGridWeek,listWeek'
        },
        events: EVENTS,
		eventClick: function(info) {
			info.jsEvent.preventDefault();
			window.open(info.event.url, '_blank');
		}
      });
      calendar.render();
    });
  <\/script>
</body>
</html>
`;

document.getElementById('cal-frame').srcdoc = html;
</script>
# What's new?
{% for post in site.posts limit:3 %}
	{% include post-card.html post=post %} <br />
{% endfor %}
# Our sponsors

{% include sponsors.html  %}
