---
layout: page
title: packme
description: Collaborative packing assistant for Android and iOS
img: assets/img/packme/packme_logo.jpg
# redirect: https://unsplash.com
importance: 1
category: software development
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/packme/packme_logo_narrow.png" title="packme logo" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

**Keywords:** *mobile app, android, ios, spring boot, kotlin, websockets, CRDT, real-time collaborative editing, flutter, keycloak, agile, scrum*

## Co-Authors

The app was developed as a part of the project in Advanced Software Engineering course together with my colleagues:
- Johannes Zottele
- Dominik Nussbaumer
- Paul Pinter
- Matthias Schellner
- Steven Ludwig

## Description

### Goal

PackMe is a packing list with social features. We believe that a normal ToDo-List is ill suited for preparing a trip.
Most ToDo-List apps...
1. don't offer extensive templating capabilities
2. don't allow lists to be made public
3. have no way of searching public lists
4. don't provide a way of recommending other lists
5. don’t have a concept of bags, weight and capacity
The goal of PackMe is to address these shortcomings and provide the best user experience for the problem domain of packing.

### Features

We developed a collaborative packing assistant which enables users to create packing lists and list templates. Users can share these lists and invite other users to collaboratively edit them in real-time. Other functionalities include:
- setting item weight
- adding multiple bags
- item categories (e.g. *hygiene, clothes*)
- re-packing for the way back
- list tags
- localization (en/de)
- single sign on (`Keycloak`)
- optimized search (`Elasticsearch`)
- html embeddings for list templates (`Thymeleaf`)

> Code upon request.

## Implementation details

### Backend

Backend was developed as a **Spring Boot** project in Kotlin. We decided to use **Postgres** as the database and to use a self-managed instance of **Keycloak** for identity & user management (Spring Security was adapted for this purpose). In order to implement real-time editing (live-editing) we used Spring Websockets and modeled the lists as [CRDTs](https://en.wikipedia.org/wiki/Conflict-free_replicated_data_type).


### Frontend

The fronted was developed in Flutter using the [Bloc](https://bloclibrary.dev/) state management library. In the following the screenshots of the app are provided.


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/packme/list.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/packme/more_actions_list.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/packme/pre_sign_in.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/packme/apple_id.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/packme/profile.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>





