A [Dash example](https://plot.ly/dash/getting-started) deployed with  using [Zappa](https://github.com/Miserlou/Zappa)

Modify the zappa_settings.json so it points to your bucket

```bash
virtualenv -p ($which python3) env
source env/bin/activate
pip install -r requirements.txt
zappa deploy
```
