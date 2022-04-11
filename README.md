# dts-announcement-bar

https://user-images.githubusercontent.com/75811975/162091545-1cb0e8a6-ec42-4595-9d8d-9a92e17952c7.mp4

Extension of Shopify's Dawn theme announcement bar. Carousel arrows appear when more than 1 announcement bar block is added. Users are able to toggle through multiple announcement bars.

1. In layout > theme.liquid, replace `{% section 'announcement-bar' %}` with `{% section 'announcement-bar-trellis' %}`

2. In config > settings_data.json, replace the `announcement-bar` object with

```...
"announcement-bar-trellis": {
  "type": "announcement-bar-trellis",
  "blocks": {
    "announcement-bar-trellis-0": {
      "type": "announcement",
      "settings": {
        "text": "Welcome to our store",
        "color_scheme": "background-1",
        "link": ""
      }
    }
  },
  "block_order": [
    "announcement-bar-trellis-0"
  ]
},
...
```

3. In locales > en.default.schema.json, add the following object after the `announcement-bar` object:

```...
"announcement-bar-trellis": {
  "name": "Announcement bar Trellis",
  "blocks": {
    "announcement": {
      "name": "Announcement",
      "settings": {
        "text": {
          "label": "Text"
        },
        "link": {
          "label": "Link"
        }
      }
    }
  }
},
...
```
