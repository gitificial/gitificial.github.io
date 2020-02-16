## python-cloudant CouchDB Endpoint access

[python-cloudant Endpoint access](https://python-cloudant.readthedocs.io/en/latest/getting_started.html#endpoint-access)

You can use the [editor on GitHub](https://github.com/gitificial/gitificial.github.io/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text
```

{% highlight python %}
def endpointAccess(params, endpoint):
    end_point = '{0}/{1}'.format(client.server_url, endpoint)
    headers = {'Content-Type': 'application/json'}
    response = response.json()
    return response
{% endhighlight %}


```python3
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
```

[python-cloudant CouchDB Endpoint access](_posts/2020-02-16_python-cloudant_Enpoint-access.md) and ![Image](src)


For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/gitificial/gitificial.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
