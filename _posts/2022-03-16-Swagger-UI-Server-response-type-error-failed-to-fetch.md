---
layout: post
title: "Swagger UI Server response type error failed to fetch"
date: 2022-03-16 11:25:06 -0700
tags: [Swagger UI]
comments: true
---

使用flask、flasgger建立Swagger UI，並使用Bearer authentication，使用Swagger UI時，若Server response出現TypeError: Failed to fetch，則可能為flask CORS未enable，可參考如下步驟使用套件flask_cors啟用CORS。

1. Install flask_cors package
===================================
```
$ pip install flask_cors
```

2. Import and add CORS to your flask app
==============================================
```
...
from flask_cors import CORS
app = Flask(__name__)
cors = CORS(app)
...
```