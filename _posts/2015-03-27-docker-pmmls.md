---
layout: post
title: Docker--- is it the new PMML?
---

One of our design goals for our product was to develop a drop-in, truly stack-agnostic solution for model monitoring. 
Of course, you can only monitor a model if you can get it to run. So part of the journey for us was deciding on a set
of standards for model scoring.

There have been attempts in the past to create standard notation for model specification, most notably PMML.
Benefits of PMML include agreed-upon implementations for scoring models and easy portability across batch and streaming jobs.
However, there are some downsides that restrict adoption by everyone. 

Probably most importantly for us, PMML represents an extra step of removal from the user's real stack. Most businesses do not 
deploy models using PMML for scoring; rather, they are using custom bits of R or python, often embedded in bigger systems like search engines.
 So it didn't feel right to force it on everyone; if we aren't monitoring the actual production script used to create scoring, at least we'd like to
monitor the closest thing possible for as many users as we can.

So, we decided to widen the net and only require a Docker container that takes input and output paths from the environment.
This allows us to score models implemented in PMML, but it also allows the user to just toss a python script in there and let 'er rip.

Of course, you can still score PMML models using Ship Data Science; just copy an open-source project or library that can score these models
and use it in your container. We'll throw a demo up in the weeks ahead.

--------



See you next time!


