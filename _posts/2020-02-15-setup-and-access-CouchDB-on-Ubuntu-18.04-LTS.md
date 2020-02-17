---
published: true
layout: post
title: "setup and access CouchDB on Ubuntu 18.04 LTS"
date: 2020-02-15
author: gitificial
description: "setup and access CouchDB on Ubuntu 18.04 LTS"
categories: [system, couchdb]
tags: [Ubuntu 18.04 LTS, couchdb]
---

<br/>
???


Tested with:

|------------------+-----------------|
| OS/Software      |Version          |
|------------------|:----------------|
| Ubuntu           |18.04 LTS        |
| CouchDB          |2.3.1            |
|------------------+-----------------|

<br/>

???

```bash
$ sudo snap install couchdb
```




Start the CouchDB server with:
```bash
sudo snap start couchdb
```

Stop the CouchDB server with:
```bash
sudo snap stop couchdb
```

You reach the servers Fauxton Web UI with your browser under the following URL:
http://127.0.0.1:5984/_utils/




