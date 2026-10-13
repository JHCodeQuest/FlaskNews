# FlaskNews

A small Flask web app that fetches and displays news headlines from
[NewsAPI](https://newsapi.org/), with filtering by source and domain.

## How it works

- `app.py` — the whole app: a Flask route renders headlines, and a helper
  (`get_sources_and_domains`) pulls the available NewsAPI sources and
  normalises their URLs into plain domains for the filter dropdown.
- `home.html` — the single page template.

## Stack

Python · Flask · [newsapi-python](https://github.com/mattlisiv/newsapi-python)

## Running it

```bash
pip install flask newsapi-python
python app.py
```

Then open <http://127.0.0.1:5000>.

### You need a NewsAPI key

`app.py` initialises the client with an empty key:

```python
newsapi = NewsApiClient(api_key='')
```

Get a free key from <https://newsapi.org/register> and set it before the app
will return anything. Prefer reading it from the environment rather than
committing it:

```python
newsapi = NewsApiClient(api_key=os.environ["NEWSAPI_KEY"])
```

## Status

Learning project — small and complete in scope, not actively developed.
