[![](https://raw.githubusercontent.com/honkita/PixelButtons/main/Pixel_GitHub.svg)](https://github.com/honkita) [![](https://raw.githubusercontent.com/honkita/PixelButtons/main/Pixel_Link.svg)](https://elitelu.com) [![](https://raw.githubusercontent.com/honkita/PixelButtons/main/Pixel_LinkedIn.svg)](https://www.linkedin.com/in/elitelu/)

# LinkHub

![](https://raw.githubusercontent.com/honkita/PixelButtons/main/Pixel_WIP.svg) ![](https://raw.githubusercontent.com/honkita/PixelIcons/main/Languages/JavaScript.svg) ![](https://raw.githubusercontent.com/honkita/PixelIcons/main/Languages/CSS.svg) ![](https://raw.githubusercontent.com/honkita/PixelIcons/main/Frameworks/Nextjs.svg)

![Main Photo](./readmeimages/main.png)

---

## About

This is a project is a pocket sized version of LinkTree. It allows for users to easily create their own link consolidation hub for social media such as Instagram, X (Formerly Twitter), and Facebook to list a few.

Users can easily modify the colours, font, links, and buttons without having to go through Javascript files. The only files that need to be modified are JSON files and a singular CSS file.

## How to Use

Currently, this project is being used to host my own links, which include my two art Instagram accounts and my Twitch account. However, this project can be easily modified to fit your uses.

### Folder Layout

![Folder Layout Photo](./readmeimages/folderlayout.png)

The only files that basic user modification is needed are the following:

| Name            | Path                          | Purpose                                                                                                           |
| --------------- | ----------------------------- | ----------------------------------------------------------------------------------------------------------------- |
| Buttons.json    | ./public/user/Buttons.json    | A file that contains all the buttons that the user wants on their LinkHub.                                        |
| IconsLinks.json | ./public/user/IconsLinks.json | A file that connects logo names to either the link to the FontAwesome logo or the icon in the CustomIcons folder. |
| userInfo.json   | ./public/user/userInfo.json   | A file to the user's information                                                                                  |
| CustomIcons     | ./public/CustomIcons          | A folder to put all custom SVG icons that are not present in the FontAwesome Library.                             |
| variables.css   | ./styles/variables.css        | The css file for all the colours and font used in the document.                                                   |
| favicon.ico     | ./public/favicon.ico          | The icon of the website                                                                                           |
| pfp.png         | ./public/user/pfp.png         | The profile picture of the user on the FeedHub                                                                    |

### userInfo.json

![userInfo.json file](./readmeimages/userInfoJSON.png)

userInfo.json, as the name implies, is a file with all the main website information such as the person's name, the name of the website, and the main image for the website. The table below describes all the attributes:

| Variable       | Purpose                                                                                                                                   |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------------------- |
| "name"         | The name of the user for the website to display.                                                                                          |
| "website"      | The name of the website when searched online.                                                                                             |
| "mainFace"     | The descriptor name of the main face image for the site. Can be ignored since only used for the alt of the image.                         |
| "mainFaceLink" | The location of the image. Can also be ignored if the user makes their face image pfp.png. Can be a .jpg too, but must be reflected here. |

No additional variables need to be added to this file. Only edit the values.

### variables.css

![variables.css file](./readmeimages/variablescss.png)

The following colour variables will be labeled on the original interface to display which variables impact what parts:

![variables.css file](./readmeimages/variablescssmain.png)

| #   | Variable         | Additional Information                                                            |
| --- | ---------------- | --------------------------------------------------------------------------------- |
| 1   | --background     |                                                                                   |
| 2   | --main-text      | This colour is for all the text in the buttons, the button itself, and the logos. |
| 3   | --title-text     |                                                                                   |
| 4   | --copyright-text |                                                                                   |

#### --font-family

The only lines that need to edited are the under src. Edit these for different fonts. If an extra font is needed, install the .ttf files.

### File Setup Diagram

Will be added

### Buttons.json

![Buttons.json file](./readmeimages/ButtonsJSON.png)

Buttons.json is a JSON Array of elements that all have the following three variables:

| Variable Name | Purpose                                                                |
| ------------- | ---------------------------------------------------------------------- |
| name          | The name of the button that gets displayed on the buttons on LinkHub.  |
| url           | The link to the page that the user wants to go to.                     |
| image         | The name of the image which corresponds to the image in IconsLink.json |

The image names must match up to a button in IconsLinks.json.

### IconsLinks.json

![IconsLinks.json file](./readmeimages/IconsLinksJSON.png)

This file is a JSON the buttons and their representation. Alongside the name (key) of the icon ("Paintbrush", "Instagram", etc.), each key represents the following:

| Variable Name | Purpose                                                                                          | Input Definitions                                                                                                                            |
| ------------- | ------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| "prefix"      | Denotes the type of icon or the location of the icon.                                            | "local" denotes that the icon exists in the folder "CustomIcons". Other prefixes ("fab", "fas", "far") are all specifically for FontAwesome. |
| "iconName"    | Denotes the iconname in either FontAwesome's library or the name of the .svg file in CustomIcons | The name of the FontAwesome icon must be in lowercase and the custom icon must be a .svg file                                                |

#### Adding Icons from FontAwesome

Currently, this project supports only the free version of FontAwesome's library of icons. If the user has access to the Pro library, modify the node_modules and \_app.jsx as needed. This tutorial will only go over adding the free icons (adding Pro icons is the same, but the user must set up the library).

The link for the FontAwesome library is [here](https://fontawesome.com/icons)

![IconsLinks.json file](./readmeimages/FontAwesomeExample.png)

Upon finding the icon, add it to IconsLinks.json. The name(key) does not matter, but must correspond to the "image" variable from Buttons.json. For the "prefix", fill as follows:

| FontAwesome Prefix | Fill As |
| ------------------ | ------- |
| fa-brands          | fab     |
| fa-solid           | fas     |
| fa-regular         | far     |

For the "iconName" variable, remove the "fa-" from the second part (fa-instagram becomes instagram). As a result, the entry in the IconsLinks.json file may look like this:

```
Instagram: {"prefix": fab, "iconName": instagram}
```

## FAQ

### Why use this over LinkTree?

This is an ad free application that does not have a watermark. This application will remain free and have no hidden costs. In addition to this, for developers who want to add additional fields and change the design, this project provides a skeleton for a link consolidation platform.
