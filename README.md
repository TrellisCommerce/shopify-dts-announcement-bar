Brought to you and maintained by [Trellis Commerce](https://trellis.co/) - A full-service eCommerce agency based in Boston, MA

# Dawn TailWindCSS Starter Component - Announcement Bar

![A computer mouse cursor moves to the top right of the browser screen. There is a click on a right pointing chevron icon on the right side of the announcement bar element. This triggers the announcement message with a white background to slide to the left and reveal another message with a blue background. The mouse then clicks on a left pointing chevron icon on the left side of the blue background message that has appeared with the new message. The click triggers the message with a blue background to slide back to the right, revealing the initial message with a white background.](https://user-images.githubusercontent.com/75811975/170133373-fc02d54d-b771-4bc7-8f77-0a985207cdc1.gif)

Extension of Shopify's Dawn theme announcement bar. Carousel arrows appear when more than 1 announcement bar block is added. Users are able to toggle through multiple announcement bars.

## How to Add to Your Theme

1. Add an `announcement-bar-trellis.liquid` file to the `sections` directory and copy in the file's code from this repo.
- If you are not using the [dawn-tailwind-starter-base](https://github.com/TrellisCommerce/dawn-tailwind-starter-base) as your theme, you will need to add the following styles to your liquid file:
```
.twcss-absolute {
  position: absolute;
}

.twcss-relative {
  position: relative;
}

.twcss-left-0 {
  left: 0px;
}

.twcss-top-0 {
  top: 0px;
}

.twcss-right-0 {
  right: 0px;
}
```

2. In layout > theme.liquid, replace `{% section 'announcement-bar' %}` with `{% section 'announcement-bar-trellis' %}`

3. In config > settings_data.json, replace the `announcement-bar` object with

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

4. In locales > en.default.schema.json, add the following object after the `announcement-bar` object:

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
        "color_scheme": {
          "label": "Color scheme",
          "options__1": {
            "label": "Background 1"
          },
          "options__2": {
            "label": "Background 2"
          },
          "options__3": {
            "label": "Inverse"
          },
          "options__4": {
            "label": "Accent 1"
          },
          "options__5": {
            "label": "Accent 2"
          }
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
