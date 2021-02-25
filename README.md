# Setup 

* 참고 문서: https://jekyllrb.com/docs/step-by-step/01-setup/

```
bundle update
bundle add webrick
bundle exec jekyll serve
```

# Examples

## Post 목록 표시

### title과 excerpt를 표시한 예

**사용 방법**

{% raw %}
```
<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>
```
{% endraw %}

**사용 결과**

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
      {{ post.excerpt }}
    </li>
  {% endfor %}
</ul>

## Tag 목록

tag로 분류하기

**사용 방법**

{% raw %}
```
{% for tag in site.tags %}
  <h3>{{ tag[0] }}</h3>
  <ul>
    {% for post in tag[1] %}
      <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
```
{% endraw %}

**사용 결과**

{% for tag in site.tags %}
  <h3>{{ tag[0] }}</h3>
  <ul>
    {% for post in tag[1] %}
      <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}

## Category 목록

category로 분류하기

**사용 방법**

{% raw %}
```
{% for category in site.categories %}
  <h3>{{ category[0] }}</h3>
  <ul>
    {% for post in category[1] %}
      <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
```
{% endraw %}

**사용 결과**

{% for category in site.categories %}
  <h3>{{ category[0] }}</h3>
  <ul>
    {% for post in category[1] %}
      <li><a href="{{ post.url | relative_url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}

## URL

{% raw %}
```
page.url: {{ page.url | inspect }}
page.url | relative_url: {{ page.url | relative_url | inspect }}
```
{% endraw %}

## Site

site 내용 확인하기

{% raw %}
```
{{ site | jsonfy}}
```
{% endraw %}

## Include

navigation include 하기

{% raw %}
```
{% include navigation.html %}
```
{% endraw %}