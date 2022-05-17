---
title: Data Science - Introduction
description: A Case Study
theme: black
---

## Project

Collect ~10,000 pathology images for ML

<span class="fragment">Major hurdle: proprietary format</span>

----

## Project details
- ~10,000 pathology images
- ~100 MB per image
- images are in a proprietary format
- ~30 minutes to convert single image
- timeline: within 2 weeks

----

## 10k Images: Quick calcs
- ~100 MB/image
  - ~1 TB total
- ~30 min/image
  - ~300k min
  - ~5k hrs
  - ~200 days
  - ~7 mo

----

## 7 mo >> 2 weeks

----

## Strategies
- Fess up: it will take 7 months
- Get a much bigger computer(s) ( >$10k )
- Use "the cloud"

----

## Used the cloud
- Google Compute Platform

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
  - VM details
  - Process ( Docker container + Python sript )
  - Input ( proprietary image )
  - Output ( converted image + metadata )
  - 1 VM : 1 Docker : 1 image
- Launched dsub

----

## dsub Workflow
- launch VM
- pull image from GS onto VM
- pull Docker from GCR onto VM
- launch Docker to convert image
- push converted image + metadata to GS
- destroy VM
- repeat for each image

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
## ( CSWAP )
- collect
- store
- wrangle
- analyze
- present

----

## Questions:
- Why 4,000 VMs instead of 10,000 VMs?
- Why ~3 hours and not 1.5 hours?
- Were all 10,000 images successfully converted?













To the optimist, the glass is half full.
To the pessimist, the glass is half empty.
To the engineer, the glass is twice as big as it needs to be.
To Excel, the glass is January 2nd.



