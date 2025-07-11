## Color Set Type

A color, which may have multiple variants.

### Extension

`.colorset`

### Folder Contents

None

### Contents.json File

Metadata, on-demand resource tags, and properties for the color set are shown in (Table 31-1).

**Table 31-1**

| Key                    | Type                  | Description                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| ---------------------- | --------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `info`                 | Dictionary            | Versioning information for the asset catalog.                                                                                                                                                                                                                                                                                                                                                                                                         |
| &nbsp;&nbsp;`author`               | String                | The application that authored the asset catalog.                                                                                                                                                                                                                                                                                                                                                                                                      |
| &nbsp;&nbsp;`version`              | Number                | The version of the asset catalog.                                                                                                                                                                                                                                                                                                                                                                                                                     |
| `colors`               | Array of dictionaries | The colors in the set.                                                                                                                                                                                                                                                                                                                                                                                                                                |
| &nbsp;&nbsp;`idiom`                    | Slot component | The device type for the image. For the values, see [idiom](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW2) in [Image Set Type](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW1).                               |
| &nbsp;&nbsp;`color`           | Dictionary     | The color itself.                                                                                                                                                                                                                                                                                                                                                                                      |
| &nbsp;&nbsp;&nbsp;&nbsp;`color-space`          | Slot component | The color space for the data item. For the values, see [color-space](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW5) in [Image Set Type](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW1).                     |
| &nbsp;&nbsp;&nbsp;&nbsp;`display-gamut`        | Slot component | The color gamut of the device display. For the values, see [display-gamut](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW35) in [Image Set Type](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW1).              |
| &nbsp;&nbsp;&nbsp;&nbsp;`graphics-feature-set` | Slot component | The graphics features required for the item. For the values, see [graphics-feature-set](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW24) in [Image Set Type](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW1). |
| &nbsp;&nbsp;&nbsp;&nbsp;`components`           | Dictionary     | The components of the color. Keys depend on the color space.                                                                                                                                                                                                                                                                                                                                                                                          |
| &nbsp;&nbsp;&nbsp;&nbsp;`reference`            | Dictionary     | Another color set which this color is an alias to.                                                                                                                                                                                                                                                                                                                                                                                                        |

### Values for Enumerated Tags

### color-space

See [color-space](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW5) in [Image Set Type](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW1).

### display-gamut

See [display-gamut](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW35) in [Image Set Type](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW1).

### graphics-feature-set

See [graphics-feature-set](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW24) in [Image Set Type](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW1).

### idiom

See [idiom](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW2) in [Image Set Type](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW1).

### interpretation

See [interpretation](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/2DTextureType.html#//apple_ref/doc/uid/TP40015170-CH55-SW6) in [Texture Type](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/2DTextureType.html#//apple_ref/doc/uid/TP40015170-CH55-SW1).

### memory

See [memory](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW25) in [Image Set Type](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW1).

### origin

See [origin](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/2DTextureType.html#//apple_ref/doc/uid/TP40015170-CH55-SW8) in [Texture Type](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/2DTextureType.html#//apple_ref/doc/uid/TP40015170-CH55-SW1).

### pixel-format

See [pixel-format](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/2DTextureType.html#//apple_ref/doc/uid/TP40015170-CH55-SW7) in [Texture Type](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/2DTextureType.html#//apple_ref/doc/uid/TP40015170-CH55-SW1).

### scale

See [scale](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW3) in [Image Set Type](https://developer.apple.com/library/archive/documentation/Xcode/Reference/xcode_ref-Asset_Catalog_Format/ImageSetType.html#//apple_ref/doc/uid/TP40015170-CH25-SW1).

### Sample Contents.json File

Source: \<https://github.com/git-up/GitUp/blob/master/GitUpKit/Interface/Interface.xcassets/branch/8.colorset/Contents.json\>

```
{
  "info" : {
    "version" : 1,
    "author" : "xcode"
  },
  "colors" : [
    {
      "idiom" : "universal",
      "color" : {
        "color-space" : "srgb",
        "components" : {
          "red" : "0.900",
          "alpha" : "1.000",
          "blue" : "0.742",
          "green" : "0.558"
        }
      }
    },
    {
      "idiom" : "universal",
      "appearances" : [
        {
          "appearance" : "luminosity",
          "value" : "dark"
        }
      ],
      "color" : {
        "color-space" : "srgb",
        "components" : {
          "red" : "0.812",
          "alpha" : "1.000",
          "blue" : "0.612",
          "green" : "0.388"
        }
      }
    }
  ]
}
```

### Sample #2

Source: \<https://github.com/git-up/GitUp/blob/master/GitUpKit/Utilities/Utilities.xcassets/separator.colorset/Contents.json\>

```
{
  "info" : {
    "version" : 1,
    "author" : "xcode"
  },
  "colors" : [
    {
      "idiom" : "universal",
      "color" : {
        "reference" : "separatorColor"
      }
    },
    {
      "idiom" : "universal",
      "appearances" : [
        {
          "appearance" : "luminosity",
          "value" : "dark"
        }
      ],
      "color" : {
        "reference" : "separatorColor"
      }
    },
    {
      "idiom" : "universal",
      "appearances" : [
        {
          "appearance" : "contrast",
          "value" : "high"
        }
      ],
      "color" : {
        "reference" : "separatorColor"
      }
    },
    {
      "idiom" : "universal",
      "appearances" : [
        {
          "appearance" : "luminosity",
          "value" : "dark"
        },
        {
          "appearance" : "contrast",
          "value" : "high"
        }
      ],
      "color" : {
        "reference" : "separatorColor"
      }
    }
  ]
}
```
