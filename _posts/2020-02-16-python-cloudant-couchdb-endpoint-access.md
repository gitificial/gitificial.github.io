---
published: true
layout: post
title: "python-cloudant CouchDB Endpoint Access"
date: 2020-02-17
author: gitificial
description: "python-cloudant Couchdb Endpoint Access"
categories: [python, couchdb]
tags: [python, couchdb, python-cloudant]
---

<br/>
This example shows how to call a CouchDB endpoint directly through the python-cloudant Requests session object as described in [python-cloudant Endpoint access](https://python-cloudant.readthedocs.io/en/latest/getting_started.html#endpoint-access).


Tested with:

|------------------+-----------------|
| OS/Software      |Version          |
|------------------|:----------------|
| Ubuntu           |18.04 LTS        |
| CouchDB          |2.3.1            |
| python-cloudant  |2.12.0           |
|------------------+-----------------|


The [CouchDB API Reference](https://docs.couchdb.org/en/latest/api/index.html) gives you a list with all available endpoints. 

Let's assume you want to get some statistics about a search result, e.g. how many documents where retrieved by a particular query. Of course, you can count the retrieved documents with a for loop, but this costs you some extra computing time.   


{% highlight json %}
{
  "_id": "0062fa1f8efa4d9a94cd9fc0cd07f9d2",
  "_rev": "1-acf955fa098fd3c1add1bb3a757e298e",
  "source": "CNN",
  "category": "news",
  "content": "But while the routes they take are often spectacular, these trains are not. ...",
}
{% endhighlight %}


{% highlight python %}
import json
from cloudant.client import CouchDB

USERNAME = 'admin'
PASSWORD = 'password'
DATABASE = 'dbname'

client = CouchDB(USERNAME, PASSWORD, url='http://127.0.0.1:5984', connect=True)

# Open an existing database
db = client[DATABASE]

# Define the end point and parameters
endpoint = DATABASE + '/_find'
params = {'selector': {'source': 'pcworld', 'searchterm': 'Joyent'}, 'execution_stats': True}

def endpointAccess(params, endpoint):
    end_point = '{0}/{1}'.format(client.server_url, endpoint)
    headers = {'Content-Type': 'application/json'}
    response = db.r_session.post(end_point, headers=headers, data=json.dumps(params, cls=db.client.encoder))
    response = response.json()
    return response

response = endpointAccess(params, endpoint)
print(response['execution_stats']['results_returned']
{% endhighlight %}


