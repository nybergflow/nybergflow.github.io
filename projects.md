---
layout: default
title: Projects
---
{% include navigation.html %}

### Piccolo

[Piccolo Ultra-High Throughput Screening Platform](https://github.com/nybergg/piccolo)

Piccolo is an ultra-high-throughput screening platform capable of processing millions of microfluidic droplets per hour. We're using it at Calico for applications across our R&D. This aim of sharing this repo publicly is to provide an open-source alternative to the Labview-built systems.

Most academic and industry droplet sorters are trapped in the LabVIEW ecosystem, which locks you into proprietary hardware and inflexible software. When I started building this system at Calico, I wanted to know: what if we built a high-performance sorter using standard, open-source languages like Python and Verilog?

This repo contains the full-stack control software for our custom detection and sorting instrument, built from in-house optics, bespoke microfluidic modules, and the [Red Pitaya](https://redpitaya.com/stemlab-125-14/) FPGA card. (Massive shoutout to [Tobias Wenzel](https://github.com/MakerTobey) and his group for pointing me toward the Red Pitaya, which made this entire architecture possible).

Goodbye LabVIEW. Hello Python and Verilog. And yes, you can develop it further with your LLM of choice. More coming soon on this front.

**Calico Collaborators:** Alfred Millett-Sikking, Lauren Washburn, Amirali Selahi, Rob Keyser. 

![Piccolo]({{ '/assets/img/piccolo_social_preview.png' | relative_url }} 'Piccolo')

---

### SALDA

[A simple automatic liquid dispense arrangement (SALDA) for timelapse microscopy](https://github.com/amsikking/SALDA_for_timelapse_microscopy)

Sometimes you need to add a drug during live-cell imaging, which usually means hovering over the microscope, holding your breath while pipetting into a well, and praying you don't knock your sample out of focus. It's a nightmare workflow that wrecks your environmental control (temperature and CO2) and introduces vibrations that completely destroy the timelapse.

We built SALDA (Simple Automatic Liquid Dispense Arrangement) to eliminate the microscope gymnastics.

Instead of manually pipetting, SALDA uses a programmatically controlled syringe pump and a custom fluidic setup to dispense liquid directly into multiwell plates while they are actively being imaged. It dispenses volumes as low as 10µL with massive precision, nails the timing perfectly, and lets you keep the incubator completely sealed. This repo shows the setup for a specific stage-top incubator, but the architecture is dead simple to adapt to nearly any system.

**Calico Collaborators:** Alfred Millett-Sikking*, Julia Lazzari-Dean, Elliot Mount, Rob Keyser. 

![SALDA]({{ '/assets/img/SALDA_social_preview.png' | relative_url }} 'SALDA')

---

### Angiogenesis-on-a-chip

The formation of new blood vessels — known as angiogenesis — is a fundamental biological process that plays an important role in health and disease. Using a 3D microfluidic platform, also called an “organ-on-a-chip,” the Microfluidics Group at Calico created a model that mimics how blood vessels grow in the human body, showing angiogenesis in action. 

The green highlights human blood vessel cells as they form branching structures. The blue shows cell nuclei and the scaffold that guides cell growth and organization. 

This system helps scientists investigate how molecular signals and environmental factors influence vessel formation — insights that are difficult to capture in traditional models. It’s helping our researchers uncover the signals that support healthy vessel growth, and what might go wrong as we age or in disease.

**Calico Collaborators:** Amirali Selahi*, Amin Davarzani 

![AOC]({{ '/assets/img/aoc_social_preview.gif' | relative_url }} 'AOC')

---

### TeleProt: High-Throughput Data for ML-Guided Enzyme Design

[Engineering highly active nuclease enzymes with machine learning and high-throughput screening
](https://www.cell.com/cell-systems/fulltext/S2405-4712(25)00069-9)

You can build the most sophisticated machine learning m                 odel in the world by scraping publically available data. But if you can't functionally train and validate your model to explore unknown space, then what's the point? Biological AI has a huge ground-truth data bottleneck.

During my time at [Triplebar Bio](https://triplebar.com/), in collaboration with [Google X](https://x.company/) and [DeepMind](https://deepmind.google/), we tackled this exact problem to optimize a nuclease enzyme that degrades chronic wound biofilms. While the ML framework (TeleProt) was the engine, our ultra-high-throughput screening workflows provided the fuel.

We generated a dataset of 55,000 distinct nuclease variants. By feeding the models this scale of function-first data, the AI outperformed traditional directed evolution in finding high-activity variants. And this was several years ago... We open-sourced the entire 55,000-variant genotype-phenotype landscape, because this volume of functional screening is what it takes to make biological AI work.

**Triplebar Collaborators:** Chenling Xu, Hanson Lee, Kat Hirano, Kosuke Iwai, Vanja Polic, Kevin Hoff, Lucas Frenz, Jeremy Agresti  
**Google X Collaborators:** Neil Thomas\*, Charlie Emrich, Jun Kim, Mariya Chavarha, Abi Ramanan  
**Deepmind Collaborators:** David Belanger\*, Lucy Colwell  

![Enzyme Engineering]({{ '/assets/img/nuclease_social_preview.jpg' | relative_url }} 'nuclease')

---
*\*project lead*
