---
title: Data Science
description:  An Introduction
theme: black
---

# Case Study


---

## Project

Collect ~10,000 pathology images for machine learning

<span class="fragment">Major hurdle: proprietary format</span>

<img src="https://cancer.osu.edu/-/media/images/cancer/website/pages-and-carousels/about/publications/frontiers/2018/winter/hand-holding-glass-slide.jpg" alt="slide" width="400"/>

----

## Project details
- ~10,000 pathology images
- ~100 MB per image
- images are in a proprietary format
- ~30 minutes to convert single image
- timeline: within 2 weeks

----

## 10,000 Images: Quick calcs
- ~100 MB/image
  - ~1 TB total

----

## 10,000 Images: Quick calcs
- ~100 MB/image
  - ~1 TB total<br />

- ~30 min/image
  - ~300,000 min
  - ~5,000 hrs
  - ~200 days
  - ~7 mo

----

# 7 mo >> 2 weeks


<img src="https://png.pngtree.com/png-vector/20210402/ourlarge/pngtree-heart-shaped-anniversary-black-and-white-calendar-icon-date-plan-png-image_3189633.jpg" alt="calendar" width="400"/>


----

## Strategies
- Fess up: it will take 7 months

- <span class="fragment">
Get a much bigger computer(s) ( >$10k )
</span>

- <span class="fragment">
Use "the cloud"
</span>


----

## Used the cloud
- Google Cloud Platform

<img src="https://www.gstatic.com/devrel-devsite/prod/v6cd15f45ec209c8961e07ea7e57ed9a0e9da4333bc915e67d1fcd2b2a9ec62d1/cloud/images/social-icon-google-cloud-1200-630.png" alt="GCP" width="400"/>


----

## Components Used
- Google Cloud Storage ( GS )
- Python ( conversion )
- Docker ( container )
- Google Container Registry ( GCR )
- dsub ( batch scheduler )

----

## Connecting the Dots
- Pushed images to GS
- Wrapped Python script in Docker
- Pushed Docker to GCR
- Created dsub template
  - VM details ( CPUs, RAM, local storage, preemptible )
  - Process ( Docker container + Python sript )
  - Input ( proprietary image )
  - Output ( converted image + metadata )
  - 1 VM : 1 Docker : 1 image
- Launched dsub

----
## Connecting the Dots

<img src="../../public/dsub.workflow.push-to-gs.png" alt="slide" width="600"/>

~~~

<img src="../../public/dsub.workflow.python-in-docker-to-GCR.png" alt="slide" width="600"/>

----

## dsub Workflow
- launch VM
- pull image from GS onto VM
- pull Docker from GCR onto VM
- launch Docker to convert image
- push converted image + metadata to GS
- destroy VM
- repeat for each image <span class="fragment">... in parallel</span>



----

## Metrics
- 4,000 VMs in parallel
- ~30 min/image
- total time: ~3 hours
- total cost: ~$300

----

## Big savings
- 3 hrs << 2 weeks
- 3 hours vs 5k hours => 0.06% time
- $300 vs $10k => 3% of cost
- In dollar-hours:
  - $900-hours vs $50e6-hours => 0.0018%

----

## Take home messages
1. assume your data is garbage
1. be familiar with data technologies
  - Python + modules
  - Docker
  - dsub
  - cloud services
1. talk with your customers
  - early and often
1. glimps into Data Science

----

## What is Data Science?
- new name for statistics
- Big Data
- Machine Learning

----

## Data Science in Five Steps
- **C**<span class="fragment">ollect</span>
- **S**<span class="fragment">tore</span>
- **W**<span class="fragment">rangle</span>
- **A**<span class="fragment">nalyze</span>
- **P**<span class="fragment">resent</span>

----
## Further Reading
- [Docker](https://github.com/rwcitek/docker/blob/master/A_Gentle_Introduction_To_Docker/Docker-walkthrough.md)
- [Python](https://github.com/rwcitek/PythonResources)
- [GCR](https://cloud.google.com/container-registry)
- [GS](https://cloud.google.com/storage)
- [dsub](https://github.com/DataBiosphere/dsub)
- [git](https://github.com/rwcitek/git.sample/tree/master/git.deep.dive)
- [GitHub](https://rwcitek.github.io/gh-slides/slides/github-demo/#/)

----
##

----
##

----
##



## Questions:
- Why 4,000 VMs instead of 10,000 VMs?
- Why ~3 hours and not 1.5 hours?
- Were all 10,000 images successfully converted?

----


----









To the optimist, the glass is half full.
To the pessimist, the glass is half empty.
To the engineer, the glass is twice as big as it needs to be.
To Excel, the glass is January 2nd.


----
## Stubs

<img src="
" alt="slide" width="400"/>

- <span class="fragment">
</span>

![Stub](../../public/apple-touch-icon-precomposed.png)


