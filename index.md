---
layout: landing
permalink: /
description: "Nodirbek Makhtumov is an AI/ML Engineer in Daejeon, Korea: computer vision on Jetsons and NPUs, RAG on local LLMs, and network security on edge devices."
custom_css: landing
custom_js: landing
---

<div class="landing-page">
    <div class="profile">
        <img src="{{ site.baseurl }}/assets/images/avatar.webp"
             alt="Nodirbek Makhtumov — AI/ML Engineer"
             class="profile-photo"
             width="150" height="150"
             fetchpriority="high">
        <div class="profile-info">
            <div class="whoami" aria-hidden="true"><span class="whoami-prompt">$</span> whoami</div>
            <h1 class="name">Nodirbek Makhtumov</h1>
            <div class="title"
                 data-titles='{{ site.landing_titles | jsonify }}'
                 aria-live="off"
                 aria-label="{{ site.landing_titles | first }}">{{ site.landing_titles | first }}</div>
        </div>
        <div class="social-links">
            <a href="{{ site.profiles.github }}" target="_blank" rel="noopener noreferrer" aria-label="GitHub Profile" title="GitHub">{% include icon.html name="github" %}</a>
            <a href="{{ site.profiles.linkedin }}" target="_blank" rel="noopener noreferrer" aria-label="LinkedIn Profile" title="LinkedIn">{% include icon.html name="linkedin" %}</a>
            <a href="mailto:{{ site.email }}" aria-label="Email" title="Email">{% include icon.html name="email" %}</a>
        </div>
    </div>
    <div class="description">
        {{ site.description }}
    </div>
    <div class="buttons">
        <a href="{{ site.baseurl }}/projects/" class="read-blog">View Projects{% include icon.html name="arrow-right" %}</a>
        <a href="{{ site.baseurl }}/about/" class="about-me">About Me</a>
    </div>

</div>

<a href="#experience" class="scroll-down-btn" aria-label="Scroll to experience">
    <span class="scroll-dot"></span>
</a>

<div class="timeline-section" id="experience">
    <h2 class="timeline-section-title">Experience</h2>
    {% include timeline.html %}
</div>
