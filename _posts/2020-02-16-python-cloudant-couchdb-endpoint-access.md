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

This example shows how to call a CouchDB endpoint directly through the python-cloudant Requests session object as described in [python-cloudant Endpoint access](https://python-cloudant.readthedocs.io/en/latest/getting_started.html#endpoint-access).




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
# Define the end point and parameters
endpoint = 'scrapy/_find'
params = {'selector': {'source': 'pcworld', 'searchterm': 'Joyent'}, 'execution$

def endpointAccess(params, endpoint):
    end_point = '{0}/{1}'.format(client.server_url, endpoint)
    headers = {'Content-Type': 'application/json'}
    response = db.r_session.post(end_point, headers=headers, data=json.dumps(pa$
    response = response.json()
    return response

response = endpointAccess(params, endpoint)
print(response['execution_stats']['results_returned'])
{% endhighlight %}


