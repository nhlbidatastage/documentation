# GitBook Markdown

## Title and Summary

GitBook creates a SUMMARY.md file in the root of the repository. The title of the Markdown page is listed in the SUMMARY.md page. 

## Common Markdown 

_See Common Markdown guidance_

## Explicit HTML is Ignored

According to [the relevant GitBook docs](https://docs.gitbook.com/integrations/github/limitations#html), arbitrary HTML content in your Markdown will not be honored.

## Display Equations

GitBook supports display equations compiled with LaTeX. Encase them in double dollar signs as you would in a LaTeX document:

```text
$$
e^{\pi i} + 1 = 0
$$
```

Becomes:

$$
e^{\pi i} + 1 = 0
$$

## Downloadable Files

You can include a link to downloadable file by adding it to your repository and using the following markup:

```text
{% file src="sample-downloadable-file.txt" %}
```

This will get rendered like this:

{% file src=".gitbook/assets/sample-downloadable-file.txt" %}

## Code Samples

Standard Markdown [fenced code blocks](https://help.github.com/en/articles/creating-and-highlighting-code-blocks), delimited in triple backticks, work just fine. They get styled like this:

```python
print('Python sample')
```

You can use a [language identifier](https://help.github.com/en/articles/creating-and-highlighting-code-blocks#syntax-highlighting) to tell GitBook to apply syntax highlighting for a particular language; above, I used the word `python` immediately after the opening backticks.

But you can also use an extended syntax that lets you show example code associated with a specific filename, and multiple tabs that the viewer can choose between. The syntax is:

```text
{% code-tabs %}
{% code-tabs-item title="myfile.py" %}
```python
print('Here is a nice Python code block.')
```
{% endcode-tabs-item %}
{% code-tabs-item title="myfile.js" %}
```js
console.log('Here is some JavaScript.');
```
{% endcode-tabs-item %}
{% endcode-tabs %}
```

This gets rendered as:

{% tabs %}
{% tab title="myfile.py" %}
```python
print('Here is a nice Python code block.')
```
{% endtab %}

{% tab title="myfile.js" %}
```javascript
console.log('Here is some JavaScript.');
```
{% endtab %}
{% endtabs %}

We do _not_ recommend using the “tabs” feature, however, since it can be confusing if people don’t realize that there are different pieces of code associated with the different tabs.

## Callouts

You can include callout boxes which highlight content. Sample syntax is:

```text
{% hint style="info" %}
This is an informational callout.
{% endhint %}
```

Callout styles available include `info`, `success`, `warning`, and `danger`.

Info:

{% hint style="info" %}
This is an informational callout.
{% endhint %}

Success:

{% hint style="success" %}
Good job, you did it!
{% endhint %}

Warning:

{% hint style="warning" %}
Something might go wrong.
{% endhint %}

Danger:

{% hint style="danger" %}
Danger Zone!
{% endhint %}

## Internal Links

To make an internal link, make a link beginning with `./` and pointing to the name of a Markdown file in the repository. Paths are relative to the current document; for instance, to link to the previous page, I can write:

```text
[a link like this](./repo-structure.md)
```

\(which generates [a link like this](https://github.com/libcce/biodata-catalyst/tree/14eae261fe7c276e06e63b88456c0b2bca3e6494/repo-structure.md)\), rather than having the link text be `./gitbook-spec/repo-structure.md`.

You can also write a page reference that is called out fairly aggressively like so:

```text
{% page-ref page="Available-Markdown.md" %}
```

This gets rendered as:

{% page-ref page="./" %}

Once again, the file path is relative to the current Markdown file’s location in the Git repository.

## Web API Method Styling

GitBook provides a fairly elaborate framework for document Web API methods. The interactive entry form is documented [here](https://docs.gitbook.com/content-editing/rich-content#api-methods). For reference, here is _a subset_ of the special tags used in the Markdown representation of this construct:

```text
{% api-method method="get" host="https://api.example.com" path="/urlpath/:param" %}
{% api-method-summary %}
method-name
{% endapi-method-summary %}

{% api-method-description %}
Method description.
{% endapi-method-description %}

{% api-method-spec %}
(A lot of additional markup goes here, but I have not documented it since
I don't think we'll be using this construct.)
{% endapi-method-spec %}
{% endapi-method %}
```

Which results in:

{% api-method method="get" host="https://api.example.com" path="/urlpath/:param" %}
{% api-method-summary %}
method-name
{% endapi-method-summary %}

{% api-method-description %}
Method description.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

## Note

There are issues with footnotes in GitBook, in the meantime explore references: [https://github.com/GitbookIO/gitbook/blob/master/docs/syntax/markdown.md\#footnotes](https://github.com/GitbookIO/gitbook/blob/master/docs/syntax/markdown.md#footnotes)

