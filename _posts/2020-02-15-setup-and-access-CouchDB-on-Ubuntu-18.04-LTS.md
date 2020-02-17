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
Apache [CouchDB](https://couchdb.apache.org/) is a document oriented NoSQL database. This post describes how to install CouchDB on a Ubuntu 18.04 LTS via snap.


Tested with:

|------------------+-----------------|
| OS/Software      |Version          |
|------------------|:----------------|
| Ubuntu           |18.04 LTS        |
| CouchDB          |2.3.1            |
|------------------+-----------------|

<br/>

Use following command to install the CouchDB server on your system:

```bash
$ sudo snap install couchdb
```




Start the CouchDB server with:
```bash
$ sudo snap start couchdb
```

Use following command to check if the server is running:
```bash
$ curl http://127.0.0.1:5984/
```

If the CouchDB server is running, you would get a response similar to this:
```bash
{"couchdb":"Welcome","version":"2.3.1","git_sha":"ababababa","uuid":"abababababababababababababababab","features":["pluggable-storage-engines","scheduler"],"vendor":{"name":"The Apache Software Foundation"}}
```

Or use snap info to get informations about the service:
```bash
$ sudo snap info "couchdb"
```

If the CouchDB server is running, you would get a response containing this line:
```bash
...
services: 
    couchdb.server: simple, enabled, active
...
```

Stop the CouchDB server with:
```bash
$ sudo snap stop couchdb
```

<br/>
You reach the servers Fauxton Web UI with your browser under the following URL:
```bash
http://127.0.0.1:5984/_utils/
```





