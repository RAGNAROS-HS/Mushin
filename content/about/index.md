---
title: "About Me"
description: "Personal profile, skills, and experience"
date: 2025-02-24
draft: false
---

<style>
/* Modern Timeline and Component Layout */
.about-header {
font-size: 1.15rem;
line-height: 1.8;
margin-bottom: 3rem;
padding: 1.5rem 2rem;
background: rgba(110, 142, 251, 0.05);
border-radius: 12px;
border-left: 5px solid #6e8efb;
box-shadow: 0 4px 15px rgba(0,0,0,0.02);
}

[data-theme='dark'] .about-header {
background: rgba(110, 142, 251, 0.05);
}

.timeline-section {
position: relative;
margin: 4rem 0;
}

.timeline-title {
font-size: 2.2rem;
font-weight: 800;
margin-bottom: 2.5rem;
display: flex;
align-items: center;
gap: 0.8rem;
width: fit-content;
}

.timeline-title i {
font-size: 1.8rem;
}

.timeline {
position: relative;
padding-left: 2rem;
}

.timeline::before {
content: '';
position: absolute;
top: 10px;
bottom: 0;
left: 6px;
width: 3px;
background: linear-gradient(to bottom, #6e8efb 0%, #a777e3 50%, rgba(167, 119, 227, 0) 100%);
border-radius: 4px;
}

.timeline-item {
position: relative;
margin-bottom: 2.5rem;
transition: transform 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
}

.timeline-item:hover {
transform: translateX(12px);
}

.timeline-dot {
position: absolute;
left: -2.35rem; 
top: 1.8rem;
width: 14px;
height: 14px;
border-radius: 50%;
background: #f8f9fa;
border: 3px solid #6e8efb;
box-shadow: 0 0 0 5px rgba(110, 142, 251, 0.1);
transition: all 0.3s ease;
z-index: 2;
}

[data-theme='dark'] .timeline-dot {
background: #1e1e1e;
}

.timeline-item:hover .timeline-dot {
background: #a777e3;
border-color: #a777e3;
box-shadow: 0 0 15px rgba(167, 119, 227, 0.5), 0 0 0 6px rgba(167, 119, 227, 0.2);
transform: scale(1.3);
}

.timeline-content {
background: rgba(255, 255, 255, 0.5);
border: 1px solid rgba(110, 142, 251, 0.15);
padding: 1.8rem 2.2rem;
border-radius: 16px;
box-shadow: 0 10px 30px rgba(0, 0, 0, 0.03);
backdrop-filter: blur(10px);
-webkit-backdrop-filter: blur(10px);
transition: all 0.3s ease;
position: relative;
overflow: hidden;
}

[data-theme='dark'] .timeline-content {
background: rgba(30, 30, 35, 0.4);
box-shadow: 0 10px 30px rgba(0, 0, 0, 0.15);
border: 1px solid rgba(255, 255, 255, 0.05);
}

.timeline-content::before {
content: '';
position: absolute;
top: 0;
left: 0;
width: 100%;
height: 100%;
background: linear-gradient(135deg, rgba(110, 142, 251, 0.05), rgba(167, 119, 227, 0.05));
opacity: 0;
transition: opacity 0.3s ease;
z-index: -1;
}

.timeline-item:hover .timeline-content {
border-color: rgba(167, 119, 227, 0.4);
box-shadow: 0 15px 35px rgba(167, 119, 227, 0.1);
}

.timeline-item:hover .timeline-content::before {
opacity: 1;
}

.timeline-header {
display: flex;
justify-content: space-between;
align-items: center;
flex-wrap: wrap;
gap: 1rem;
margin-bottom: 1.2rem;
padding-bottom: 1.2rem;
border-bottom: 1px solid rgba(110, 142, 251, 0.1);
}

[data-theme='dark'] .timeline-header {
border-bottom: 1px solid rgba(255, 255, 255, 0.05);
}

.timeline-role {
font-size: 1.4rem;
font-weight: 700;
margin: 0 0 0.3rem 0;
}

.timeline-company {
font-size: 1.05rem;
font-weight: 600;
opacity: 0.8;
display: flex;
align-items: center;
gap: 0.5rem;
margin: 0;
}

.timeline-date {
font-size: 0.85rem;
font-weight: 700;
background: rgba(167, 119, 227, 0.1);
padding: 0.4rem 1.2rem;
border-radius: 20px;
display: flex;
align-items: center;
gap: 0.5rem;
white-space: nowrap;
letter-spacing: 0.5px;
}

[data-theme='dark'] .timeline-date {
background: rgba(167, 119, 227, 0.15);
}

.timeline-description {
margin: 0;
padding-left: 0.5rem;
line-height: 1.7;
}

.timeline-description li {
margin-bottom: 0.6rem;
position: relative;
list-style-type: none;
font-size: 1rem;
opacity: 0.9;
}

.timeline-description li::before {
content: "▹";
position: absolute;
left: -1.2rem;
font-weight: bold;
}

.timeline-description li:last-child {
margin-bottom: 0;
}

.skills-tags {
display: flex;
flex-wrap: wrap;
gap: 0.8rem;
margin-bottom: 2rem;
}

.skill-tag {
background: rgba(110, 142, 251, 0.05);
padding: 0.6rem 1.2rem;
border-radius: 8px;
font-size: 0.95rem;
font-weight: 600;
display: inline-flex;
align-items: center;
gap: 0.6rem;
border: 1px solid rgba(110, 142, 251, 0.2);
transition: all 0.3s ease;
cursor: default;
}

[data-theme='dark'] .skill-tag {
background: rgba(255, 255, 255, 0.02);
border: 1px solid rgba(255, 255, 255, 0.1);
}

.skill-tag i {
font-size: 1.1rem;
}

.skill-tag:hover {
background: rgba(110, 142, 251, 0.15);
transform: translateY(-2px);
border-color: #6e8efb;
box-shadow: 0 4px 12px rgba(110, 142, 251, 0.1);
}

[data-theme='dark'] .skill-tag:hover {
background: rgba(110, 142, 251, 0.2);
}

.extra-section {
margin-top: 4rem;
}
</style>

<div class="about-header">
Hi there! I'm <strong>Hugo Sokołowski-Katzer</strong>, an MSc Artificial Intelligence student at VU Amsterdam/Universiteit van Amsterdam. I'm in the "AI for Health" track, meaning much of what I learn revolves around the intersection of AI and healthcare. But my background before that is rather diverse, as you will see below.
</div>

<div class="timeline-section">
<h2 class="timeline-title"><i class="fa-solid fa-briefcase"></i> Experience</h2>
<div class="timeline">
<div class="timeline-item">
<div class="timeline-dot"></div>
<div class="timeline-content">
<div class="timeline-header">
<div>
<h3 class="timeline-role">Information Security Intern</h3>
<div class="timeline-company"><i class="fa-solid fa-building"></i> Swapfiets</div>
</div>
<div class="timeline-date"><i class="fa-regular fa-calendar-alt"></i> June 2025 - August 2025</div>
</div>
<ul class="timeline-description">
<li>Assisted with SOC 2 compliance preparation by identifying relevant controls in Vanta and gathering supporting evidence.</li>
<li>Supported incident response efforts by analyzing and resolving security-related issues.</li>
</ul>
</div>
</div>
<div class="timeline-item">
<div class="timeline-dot"></div>
<div class="timeline-content">
<div class="timeline-header">
<div>
<h3 class="timeline-role">IT Intern</h3>
<div class="timeline-company"><i class="fa-solid fa-building"></i> Swapfiets</div>
</div>
<div class="timeline-date"><i class="fa-regular fa-calendar-alt"></i> June 2024 - June 2025</div>
</div>
<ul class="timeline-description">
<li>Resolved a wide range of IT support tickets, ensuring timely and effective resolution.</li>
<li>Designed and implemented automations to streamline internal processes.</li>
<li>Managed access-related issues using Okta and AccessOwl, ensuring smooth permission handling.</li>
</ul>
</div>
</div>
<div class="timeline-item">
<div class="timeline-dot"></div>
<div class="timeline-content">
<div class="timeline-header">
<div>
<h3 class="timeline-role">Shop Assistant</h3>
<div class="timeline-company"><i class="fa-solid fa-store"></i> VU Amsterdam SPAR</div>
</div>
<div class="timeline-date"><i class="fa-regular fa-calendar-alt"></i> January 2024 - June 2024</div>
</div>
<ul class="timeline-description">
<li>Refilled amenities, products and organized incoming deliveries.</li>
<li>Attended customers at checkout and/or individual queries.</li>
</ul>
</div>
</div>
<div class="timeline-item">
<div class="timeline-dot"></div>
<div class="timeline-content">
<div class="timeline-header">
<div>
<h3 class="timeline-role">Housekeeper</h3>
<div class="timeline-company"><i class="fa-solid fa-hotel"></i> Radisson Hotel & Suites Amsterdam South</div>
</div>
<div class="timeline-date"><i class="fa-regular fa-calendar-alt"></i> July 2023 - August 2023</div>
</div>
<ul class="timeline-description">
<li>Managed urgent customer affairs and maintained high standards for public and private spaces.</li>
</ul>
</div>
</div>
</div>
</div>

<div class="timeline-section">
<h2 class="timeline-title"><i class="fa-solid fa-graduation-cap"></i> Education</h2>
<div class="timeline">
<div class="timeline-item">
<div class="timeline-dot"></div>
<div class="timeline-content">
<div class="timeline-header">
<div>
<h3 class="timeline-role">Master of Artificial Intelligence</h3>
<div class="timeline-company"><i class="fa-solid fa-university"></i> AI for Health track | VU / UvA</div>
</div>
<div class="timeline-date"><i class="fa-regular fa-clock"></i> Current</div>
</div>
</div>
</div>
<div class="timeline-item">
<div class="timeline-dot"></div>
<div class="timeline-content">
<div class="timeline-header">
<div>
<h3 class="timeline-role">Undergraduate of Computer Science</h3>
<div class="timeline-company"><i class="fa-solid fa-university"></i> Vrije Universiteit Amsterdam</div>
</div>
</div>
</div>
</div>
<div class="timeline-item">
<div class="timeline-dot"></div>
<div class="timeline-content">
<div class="timeline-header">
<div>
<h3 class="timeline-role">Secondary School</h3>
<div class="timeline-company"><i class="fa-solid fa-school"></i> Konstanty Ildefons Gałczyński School, Olsztyn, Poland</div>
</div>
</div>
</div>
</div>
</div>
</div>

<div class="extra-section">
<h2 class="timeline-title"><i class="fa-solid fa-code"></i> Skills & Tools</h2>
</div>

{{< tabs defaultTab="0" type="card" >}}

  {{% tab title="Languages & Tech" %}}
  - **Programming:** Python 3, C, C++, JavaScript, Scala, Assembly x86, HTML5, CSS
  - **ML Frameworks:** TensorFlow, Keras
  - **Database:** SQLite
  {{% /tab %}}

  {{% tab title="IT & Security Ops" %}}
  - **Access & Security:** Vanta (SOC 2), Okta, AccessOwl
  - **HR & Ops:** Recruitee, Workwize, SDWorx, Hubspot
  {{% /tab %}}

  {{% tab title="Productivity & Design" %}}
  - **Management:** Atlassian Tools (Jira/Confluence), Airtable, Slack, Zapier
  - **Software:** QGIS, Autodesk Fusion 360, MS Office, LaTeX
  {{% /tab %}}

{{< /tabs >}}

<div class="extra-section">
<h2 class="timeline-title"><i class="fa-solid fa-language"></i> Languages</h2>
<div class="skills-tags">
<div class="skill-tag"><i class="fa-solid fa-comment"></i> Polish (Native)</div>
<div class="skill-tag"><i class="fa-solid fa-comment-dots"></i> English (Proficient - Cambridge C2, Grade A)</div>
<div class="skill-tag"><i class="fa-solid fa-comment-dots"></i> German (Fluent - DSD Stufe II C1)</div>
</div>
</div>

<div class="extra-section">
<h2 class="timeline-title"><i class="fa-solid fa-certificate"></i> Qualifications & Certificates</h2>
<div class="skills-tags">
<div class="skill-tag"><i class="fa-solid fa-plane-up"></i> UAV Operator Certificate</div>
<div class="skill-tag"><i class="fa-solid fa-ship"></i> Motorboat Helmsman</div>
<div class="skill-tag"><i class="fa-solid fa-life-ring"></i> WOPR 2nd Degree Lifeguard</div>
</div>
</div>

<div class="extra-section">
<h2 class="timeline-title"><i class="fa-solid fa-heart"></i> Interests</h2>
<p style="font-size: 1.1rem; line-height: 1.8; opacity: 0.9; margin-bottom: 2rem;">
Beyond academics and work I pursue a couple of things, but most notably Brazilian Jiu Jitsu. I train at Dodo Jiujitsu, whenever I'm not working or studying you can probably find me there.
</p>
  
![The flock](/img/fofos.jpeg)
</div>