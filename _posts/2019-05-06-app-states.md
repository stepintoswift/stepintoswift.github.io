---
author: "Liam"
date: 2019-05-06 00:00:13
description: "What are the Application States?"
layout: post
permalink: application-states
tags: [application state]
title: "Application States"
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
