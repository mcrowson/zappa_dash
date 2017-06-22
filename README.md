A [Dash example](https://plot.ly/dash/getting-started) deployed with  using [Zappa](https://github.com/Miserlou/Zappa)

Currently hosted on API Gateway and AWS Lambda at [https://dash.struce.com]('https://dash.struce.com/])

Modify the zappa_settings.json so it points to your bucket

```bash
virtualenv -p ($which python3) env
source env/bin/activate
pip install -r requirements.txt
zappa deploy
```

Note that Zappa's middleware attempts to call the Dash object as if it were a Flask object. Therefore the following 
method was added to my dash.dash.Dash class:
 
```python
def __call__(self, *args, **kwargs):
    return self.server.__call__(*args, **kwargs)
```

Status: The demo is not fully functional yet and you can follow the progress on this issue: [https://github.com/plotly/dash/issues/22](https://github.com/plotly/dash/issues/22)