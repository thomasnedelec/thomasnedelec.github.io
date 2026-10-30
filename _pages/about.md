---
permalink: /
title: "About me"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I am a Principal Investigator at the Paris Brain Institute (ICM), in the ARAMIS Lab, a joint INRIA–ICM team that develops data-science and AI methods for neurology. Within ARAMIS, I lead a group of six working on routinely collected health data, and I am a member of the Institute's Center for AI and Data Science for neurological disorders. I am also a medical resident at AP-HP (Pitié-Salpêtrière), with clinical training due to end in May 2028.

I came to epidemiology from machine learning. After an engineering degree from École Polytechnique, specialising in applied mathematics, and an M.Sc. in Machine Learning from University College London, I completed a PhD in Applied Mathematics at ENS Paris-Saclay under the supervision of Vianney Perchet and Noureddine El Karoui. My thesis, prepared in parallel with a position at Criteo AI Lab, dealt with online learning and auction theory; it led to publications at ICML and AISTATS and a monograph in *Foundations and Trends in Machine Learning*. I joined the ARAMIS Lab as a postdoctoral fellow in 2019, moved to the epidemiology of neurodegenerative diseases, and obtained the Habilitation à Diriger des Recherches from Sorbonne University in 2026.

In 2026, I was selected as one of France's ten Next Gen Leaders in Health (La French Care and Le Figaro, academic category), and our work on the rising prevalence of motor neurodegenerative diseases was selected among the five most exciting studies at the European Academy of Neurology Congress.

Research
======

My research uses routinely collected health data (national claims databases, hospital data warehouses and population registers) to study neurological disorders from their earliest signs to their progression.

<figure class="research-figure">
  <img src="/images/trajectories.png" alt="Schematic care trajectories for Alzheimer's disease, Parkinson's disease, multiple sclerosis and ALS, from the prodrome to progression">
  <figcaption>Care trajectories recorded in routine health data, before and after diagnosis (schematic).</figcaption>
</figure>

The work is organised around four axes.

**Validating national health databases and comparing countries.** A disease must be identified and dated consistently before it can be compared across health systems. We develop harmonised case definitions and use them to estimate incidence and its trends in France and across Europe, so that differences between countries reflect populations rather than data sources. Recent work includes national incidence estimates for multiple sclerosis and motor neuron diseases in France, and a France–Sweden analysis of what drives their rising prevalence. This axis relies on collaborations with Karolinska Institutet, Aarhus University, the Zi in Berlin and University College London.

**The prodrome.** Neurodegenerative diseases begin years before diagnosis. Using agnostic case-control designs on national data, we have identified conditions associated with Alzheimer's disease up to fifteen years before diagnosis, shown that early presentations differ between Alzheimer's disease, Parkinson's disease and dementia with Lewy bodies, and replicated pre-diagnostic signatures across France, Sweden and Australia. We now use Mendelian randomisation and target-trial emulation to separate early symptoms from causal risk factors and to estimate treatment effects.

**Phenotyping from clinical notes.** Administrative data do not record disease onset or severity. With NeuroCohortBuilder, a pipeline built on open-weight language models run inside the hospital environment, we extract confirmed diagnoses, onset dates and clinical scores from the notes of the AP-HP clinical data warehouse, and link them to the national claims database to measure what national data can and cannot show.

**Data-driven subtyping.** We combine care trajectories, clinical information, environmental exposures and genetics to identify subgroups of patients that may cut across diagnostic categories and differ in their course. The long-term aim is to stratify patients at diagnosis and to identify, for each subgroup, existing interventions that may alter it.

Funding
======

My work is funded by the PEPR ProdroMND (France 2030, Principal Investigator) and the PEPR Transcend (France 2030, co-investigator). It was previously funded by the EU Joint Programme – Neurodegenerative Disease Research (JPND), in collaboration with Karolinska Institutet and the University of Queensland.

Team
======

{%- assign groups = "current|former" | split: "|" -%}
{%- for g in groups -%}
{%- assign members = site.data.team | where: "status", g -%}
{%- if members.size > 0 %}
<h3>{% if g == "current" %}Current members{% else %}Former members{% endif %}</h3>
<div class="team-grid">
{%- for m in members %}
<div class="team-member">
{%- if m.photo %}<img src="/images/team/{{ m.photo }}" alt="{{ m.name }}">{% else %}{% assign parts = m.name | split: " " %}<div class="team-initials">{{ parts[0] | slice: 0 }}{{ parts[1] | slice: 0 }}</div>{% endif -%}
<div class="team-name">{{ m.name }}</div>
{%- if m.role %}<div class="team-role">{{ m.role }}</div>{% endif -%}
</div>
{%- endfor %}
</div>
{% endif -%}
{%- endfor %}
