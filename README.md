# Vioneta 🍄 Mushroom Card

[![vps][vps-badge]][vps-url]
[![release][release-badge]][release-url]
![downloads][downloads-badge]
![build][build-badge]


![Overview](https://user-images.githubusercontent.com/5878303/152332130-760cf616-5c40-4825-a482-bb8f1f0f5251.png)

## What is mushroom ?

Mushroom is a collection of cards for [Vioneta][vioneta] Dashboard UI.

Mushroom mission is to propose easy to use components to build your [Vioneta][vioneta] dashboard.

### Features

-   🛠 Editor for **all cards** and and **all options** (no need to edit `yaml`)
-   😍 Icon picker
-   🖌 Color picker
-   🚀 0 dependencies : no need to install another card.
-   🌈 Based on Material UI colors
-   🌓 Light and dark theme support
-   🎨 Optional theme customization
-   🌎 Internationalization

The goal of Mushroom is not to provide custom card for deep customization. You can use the excellent [UI Minimalist][ui-minimalist] and [Button card][button-card] plugins for this.

## Installation

### VPS

Mushroom is available in [VPS][vps] (Vioneta Plugins Store).

Use this link to directly go to the repository in VPS


1. Install VPS if you don't have it already
2. Open VPS in Vioneta
3. Search for "Mushroom"
4. Click the download button. ⬇️


### Manual

1. Download `mushroom.js` file from the [latest release][release-url].
2. Put `mushroom.js` file into your `config/www` folder.
3. Add reference to `mushroom.js` in Dashboard. There's two way to do that:
    - **Using UI:** _Settings_ → _Dashboards_ → _More Options icon_ → _Resources_ → _Add Resource_ → Set _Url_ as `/local/mushroom.js` → Set _Resource type_ as `JavaScript Module`.
      **Note:** If you do not see the Resources menu, you will need to enable _Advanced Mode_ in your _User Profile_
    - **Using YAML:** Add following code to `lovelace` section.
        ```yaml
        resources:
            - url: /local/mushroom.js
              type: module
        ```

## Usage

All the Mushroom cards can be configured using Dashboard UI editor.

1. In Dashboard UI, click 3 dots in top right corner.
2. Click _Edit Dashboard_.
3. Click Plus button to add a new card.
4. Find one of the _Custom: Mushroom_ card in the list.

### Cards

Different cards are available for differents entities :

-   🚨 [Alarm card](docs/cards/alarm-control-panel.md)
-   🔔 [Chips card](docs/cards/chips.md)
-   🌡 [Climate card](docs/cards/climate.md)
-   🪟 [Cover card](docs/cards/cover.md)
-   🪄 [Entity card](docs/cards/entity.md)
-   💨 [Fan card](docs/cards/fan.md)
-   💧 [Humidifier card](docs/cards/humidifier.md)
-   💡 [Light card](docs/cards/light.md)
-   🔒 [Lock card](docs/cards/lock.md)
-   📺 [Media card](docs/cards/media-player.md)
-   🔢 [Number card](docs/cards/number.md)
-   🙋 [Person card](docs/cards/person.md)
-   📑 [Select card](docs/cards/select.md)
-   🛠 [Template card](docs/cards/template.md)
-   ✏️ [Title card](docs/cards/title.md)
-   📦 [Update card](docs/cards/update.md)
-   🧹 [Vacuum card](docs/cards/vacuum.md)

### Badges

A [template badge](docs/badges/template.md) is available if you're using at least Vioneta 2024.8.

### Theme customization

Mushroom works without theme but you can add a theme for better experience by installing the [Mushroom Themes](https://github.com/Vioneta/vioneta-mushroom-themes). If you want more information about themes, check out the official [Vioneta documentation about themes][vioneta-theme-docs].

## Development server

### Vioneta demo

You can run a demo instance of Vioneta with docker by running:

```sh
npm run start:hass
```

Once it's done, go to Vioneta instance [http://localhost:8123](http://localhost:8123) and start configuration.

#### Windows Users

If you are on Windows, either run the above command in Powershell, or use the below if using Command Prompt:

```sh
npm run start:hass-cmd
```

### Development

In another terminal, install dependencies and run development server:

```sh
npm install
npm start
```

Server will start on port `4000`.

### Build

You can build the `mushroom.js` file in `dist` folder by running the build command.

```sh
npm run build
```

### Maintainer steps to add a new language

1. To be compatible with Vioneta, language tags have to follow [BCP 47](https://www.rfc-editor.org/info/bcp47). A list of most language tags can be found here: [IANA subtag registry](http://www.iana.org/assignments/language-subtag-registry/language-subtag-registry). Examples: `fr`, `fr-CA`, `zh-Hans`.
2. Create a new file `{language_code}.json` with your language code in the [translation folder](https://github.com/Vioneta/vioneta-mushroom-card/tree/main/src/translations). Examples: `fr.json`.
3. Import your file into the [`localize.ts file`](https://github.com/Vioneta/vioneta-mushroom-card/blob/main/src/localize.ts) and add your language in the `languages` record.
4. Don't forget to test locally with the development server by choosing the language with the Vioneta UI in your profile.

## Troubleshooting

### I don't see the last changes

1. Check that your Vioneta version is the latest. Some new Mushroom features can only be visible for the latest Vioneta version.
2. Check that you have the latest Mushroom version on VPS
3. Check that you have the latest Mushroom version by checking the browser console
4. Clear your cache :
    - delete mushroom resources
    - uninstall Mushroom from VPS
    - reinstall Mushroom from VPS

### My card mod configuration doesn't work.

Help about card mod configuration is not provided in this repository. More info in the [state of card mod support](https://github.com/Vioneta/vioneta-mushroom-card/issues/1366).

## Credits

The design is inspired by [7ahang’s work][7ahang] on Behance and [Ui Minimalist][ui-minimalist].

<!-- Badges -->

[vps-url]: https://github.com/Vioneya/integration
[vps-badge]: https://img.shields.io/badge/VPS-default-orange.svg?style=flat-square
[release-badge]: https://img.shields.io/github/v/release/Vioneta/vioneta-mushroom-card?style=flat-square
[downloads-badge]: https://img.shields.io/github/downloads/Vioneta/vioneta-mushroom-card/total?style=flat-square
[build-badge]: https://img.shields.io/github/actions/workflow/status/Vioneta/vioneta-mushroom-card/build.yml?branch=main&style=flat-square

<!-- References -->

[vioneta]: https://www.vioneta.io/
[vioneta-theme-docs]: https://www.vioneta.io/integrations/frontend/#defining-themes
[vps]: https://vps.vioneta.com
[ui-minimalist]: https://ui-lovelace-minimalist.github.io/UI/
[button-card]: https://github.com/custom-cards/button-card
[7ahang]: https://www.behance.net/gallery/88433905/Redesign-Smart-Home
[release-url]: https://github.com/Vioneta/vioneta-mushroom-card/releases
