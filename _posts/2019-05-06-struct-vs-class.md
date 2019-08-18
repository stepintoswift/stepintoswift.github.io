---
author: "Liam"
date: 2019-05-13 00:00:07
description: "Struct or Class"
layout: post
permalink: stuct-or-class
published: true
tags: [class, struct]
title: "Should I use a struct or a class?"
---

## Struct vs Class

We use a struct when:
1. Primary purpose is to encapsulate a few relatively small data values.
2. Reasonably expect encapsulated values to be copied rather than referenced when assigned or passed around.
3. Any properties stored by a struct are themselves value types which should also be copied.
4. The struct does not need to inherit properties or behaviours from another type.

If your purpose does not fit into the above, use a class.

---

Related articles:
- [Class]({% post_url 2019-05-06-class %})
- [Struct]({% post_url 2019-05-06-struct %})
