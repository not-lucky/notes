
# Flask:
```python
from flask import Flask, render_template

app = Flask(__name__)

@app.route("/")
def hello_world():
    return render_template('index.html')

if __name__ == '__main__':
	app.run(debug=True)
```



## Variables:
```python
from markupsafe import escape

@app.route('/user/<username>')
def show_user_profile(username):
    # show the user profile for that user
    return f'User {escape(username)}'

@app.route('/post/<int:post_id>')
def show_post(post_id):
    # show the post with the given id, the id is an integer
    return f'Post {post_id}'

@app.route('/path/<path:subpath>')
def show_subpath(subpath):
    # show the subpath after /path/
    return f'Subpath {escape(subpath)}'
```

variable rules:

| variable | hmmmm                                      |
| -------- | ------------------------------------------ |
| `string`  | (default) accepts any text without a slash |
| `int`  | accepts positive integers |
| `float` | accepts positive floating point values |
| `path`  | like `string` but also accepts slashes     |
| `uuid` | accepts UUID strings |


## URL Building:

url_for(func_name, keyword_args)
```python
from flask import url_for

@app.route('/user/<string:username>')
def profile(username):
    return f'{username}\'s profile'

with app.test_request_context():
    print(url_for('profile', username='John Doe'))
```

Output will be:
``/user/John%20Doe``

## Methods:
```python
from flask import request

@app.route('/login', methods=['GET', 'POST'])
def login():
    if request.method == 'POST':
        return do_the_login()
    else:
        return show_the_login_form()
```

LOOK AT PROJECTS TO GET MORE INFO

