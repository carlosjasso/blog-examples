# curl - API testing made really simple

This document is an example used on [one of my blog posts]().

## GET

```bash
curl -X GET "https://httpbin.org/get" \
-H "accept: application/json" \
-D result.headers \
-o result.json
```

## POST

### - Pain Text

```bash
curl -X POST "https://httpbin.org/post" \
-H "accept: application/json" \
-H "Content-Type: text/plain" \
-H "Custom-Header: Testing" \
-d "I love hashnode" \
-D result.headers \
-o result.json
```

### - Query string params

```bash
curl -X POST "https://httpbin.org/post?name=Carlos&lastname=Jasso" \
-H "accept: application/json" \
-D result.headers \
-o result.json
```

### - Form

```bash
curl -X POST "https://httpbin.org/post" \
-H "Content-Type: multipart/form-data" \
-F "FavoriteFood=Pizza" \
-F "FavoriteBeverage=Beer" \
-D result.headers \
-o result.json
```

### - Data

```bash
curl -X POST "https://httpbin.org/post" \
-H "Content-Type: application/json; charset=utf-8" \
-d @data/data.json \
-D result.headers \
-o result.json
```

### - File

```bash
curl -X POST "https://httpbin.org/post" \
-H "Content-Type: multipart/form-data" \
-F "FileComment=This is a JPG file" \
-F "image=@data/image.jpg" \
-D result.headers \
-o result.json
```

## PUT

```bash
curl -X PUT "https://httpbin.org/put" \
-H "Content-Type: application/json; charset=utf-8" \
-H "Header-Type: Testing" \
-d @data/data.json \
-D result.headers \
-o result.json
```

## Auth

```bash
curl -X GET "https://httpbin.org/basic-auth/carlos/secret" \
-u carlos:secret \
-H "accept: application/json" \
-D result.headers \
-o result.json
```