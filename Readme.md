## How to run

```
virtualenv venv
source venv/bin/activate
pip install -r requirements.txt
pip install -r requirements.txt --no-deps
```

```
jupyter notebook \
    --notebook-dir="." \
    --ip=0.0.0.0 --port=3225
```

```
python -m debugpy --listen 4444 test.py
```

```
fastapi dev main.py
```

## Enable push to git

```
nano ~/.gitconfig
```

```
code ~/.gitconfig
```

```
[user]
Please adapt and uncomment the following lines:
        name = <Jenny TING>
        email = <tingjenny88430@gmail.com>
        username = <jting0499>
```
