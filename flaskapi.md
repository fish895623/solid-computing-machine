# Flask

## Flask 설치

```bash
python -m pip install --no-cache-dir flask
```

### api test tool

아래의 크롬 확장팩은 POST, GET 을 보다 쉽게 쓸수 있다.

[talend api tester](https://chrome.google.com/webstore/detail/talend-api-tester-free-ed/aejoelaoggembcahagimdiliamlcdmfm)

## Flask api 기본 코드

```python
from flask import Flask, request

app = Flask(__name__)

@app.route("/", methods=["POST"])
def root():
    # json 데이터에서 a0 값을 읽어옴
    a0 = request.get_json()["a0"]
    a1 = request.get_json()["a1"]
    """
    json 데이터 에서 값을 읽어올때 형변환하여 
    새로운 값 ( a2 )에 넣어준다.
    """
    request.get_json()["a2"] = int(a0) + int(a1)

    # 인터넷 창에 반환할 데이터를 입력해준다.
    return request.get_json()


if __name__ == "__main__":
    app.run(host="0.0.0.0", port="5000")
```

