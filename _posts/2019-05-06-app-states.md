---
author: "Liam"
date: 2019-05-06 00:00:01
description: "Application States"
layout: post
permalink: application-states
published: true
tags: [application state]
title: "What are the Application States?"
---

## Application States

- Not Running   
- Inactive      
- Active        
- Background
- Suspended

### Valid transitions:
- `Not Running` <---> `Suspended`
- `Inactive` <---> `Active`
- `Inactive` <---> `Background`

Related articles:
- [Application Lifecycle]({% post_url 2019-05-06-app-lifecycle %})
