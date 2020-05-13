---
layout: default
title: Free to Use APIs
nav_order: 9
permalink: /free_apis
---

# Description of Free to Use APIs we provide

Signup [**here**](https://tech.notai.tech/signup) for free API key.

- We don't send any verification emails/ spam or store your email publicly.

- You are allowed to use fake email ids (eg: a@amail.com) while signing up.

- For obvious reasons, `/sync` is not enabled on the APIs we provide. `/async`, `/result`, webhooks, client side batching, work as expected.

**Limit**: Maximum number of requests allowed per hour.
**Batch Size**: Maximum Client side batch size allowed per request.

- For example, Limit = 16 and Batch size = 4, allows you to process maximum of 64 examples per hour.

| Recipe                                                                    | URL                                              | Limit| Batch Size |
|:-------------------------------------------------------------------------:|:------------------------------------------------:|:----:|:----------:|
|[deepsegment_en](https://fastdeploy.notai.tech/recipes#deepsegment_enfrit) |https://tech.notai.tech/deepsegment/en/async      |64|16|
|[efficientnet_b2]()                                                        |https://tech.notai.tech/efficientnet/b2/async     |16|4|


The request/response structure is explained [**here.**](https://fastdeploy.notai.tech/api)

Async with webhook example.
```bash
curl -d '{"data": ["are we gonna hate each other some day I ordered a pizza I was hungry"], "webhook": "https://fastdeploy.requestcatcher.com"}' -H "Content-Type: application/json" "https://tech.notai.tech/deepsegment/en/async?api_key=API_KEY"
```

```python
import requests

data = {"data": ["are we gonna hate each other some day I ordered a pizza I was hungry"], "webhook": "https://fastdeploy.requestcatcher.com"}

requests.post('https://tech.notai.tech/deepsegment/en/async', params={'api_key': API_KEY}, json=data).json()
```