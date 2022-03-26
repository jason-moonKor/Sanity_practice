## Sanity 를 이용해서 Blog 만들어보기

Next.js 를 공부하기전에 선행학습용 Sanity

### 추가 설치

- react-ace
- sanity url-metadata-input

### Test Query

```
*[_type == "post"]{title,subtitle,createAt,"content":content[]{...,...select(_type == "imageGallery" => {"images":images[]{...,"url":asset -> url}})},
    "slug":slug.current,
    "thumbnail":{
    "alt":thumbnail.alt,
    "imageUrl":thumbnail.asset -> url
    },
    "author":author -> {
    name,
    role,
    "image" : image.asset -> url
    },
    "tag":tag -> {
    title,
    "slug" : slug.current
    }
}
```
