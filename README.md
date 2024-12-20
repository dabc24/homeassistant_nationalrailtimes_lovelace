# Home Assistant National Rail Times Card with support for platform numbers
A custom Home Assistant card for the Lovelace theme to show next available trains to specific stops through the National Rail Darwin API.

Based upon previous work by @crismc (https://github.com/crismc/)

This version adds support for platform numbers and a countdown timer until you need to leave.

To be used with the Home Assistant custom component homeassistant_nationalrailtimes_integration (https://github.com/crismc/homeassistant_nationalrailtimes_integration)

[![License][license-shield]](LICENSE.md)

[![hacs][hacs-badge]][hacs-url]

![alt text](https://raw.githubusercontent.com/dabc24/homeassistant_nationalrailtimes_lovelace/master/screenshot.png)

Based on the community driven boilerplate of best practices for Home Assistant Lovelace custom cards (Boilerplate Card by [@iantrich](https://www.github.com/iantrich) https://github.com/custom-cards/boilerplate-card)

## Options

| Name                 | Type    | Requirement  | Description                                                                   | Default             |
| ---------------------| ------- | ------------ |-------------------------------------------------------------------------------| ------------------- |
| type                 | string  | **Required** | `custom:nationalrail-times-card`                                              |                     |
| name                 | string  | **Optional** | Card name based on entity                                                     | `none`              |
| show_error           | boolean | **Optional** | Show error message such as no service data                                    | `true`              |
| show_warning         | boolean | **Optional** | Show station alert messages                                                   | `true`              |
| show_via_destination | boolean | **Optional** | Show if train goes via an alternate route                                     | `true`              |
| show_callingpoints   | boolean | **Optional** | Show train service calling stops                                              | `true`              |
| show_status          | boolean | **Optional** | Show service status (e.g. On Time, Delayed etc)                               | `true`              |
| show_arrival_time    | boolean | **Optional** | Show train service arrival time at destination                                | `true`              |
| show_departure_time  | boolean | **Optional** | Show train service departure time from primary station                        | `true`              |
| show_lastupdated     | boolean | **Optional** | Show when the service last communicated with the API                          | `true`              |
| show_offset          | boolean | **Optional** | Show walking time to station offset                                           | `true`              |
| show_offset_countdown          | boolean | **Optional** | Show coundown until you need to leave calculated from walking time to station | `true`              |
| show_platform        | boolean | **Optional** | Show platform number train is due to leave from                               | `true`              |
| entity               | string  | **Optional** | Home Assistant entity ID.                                                     | `none`              |


## Install via HACS

The easiest way to install this frontend card is to install via HACS:

1) Simply go to HACS in your Home Assistant
2) Select 'Frontend'
3) In the top right of the screen, select the 3 dots and choose 'Custom repositories'
4) For the repository field enter 'https://github.com/dabc24/homeassistant_nationalrailtimes_lovelace'
5) Choose 'Dashboard' as the type
6) Add
7) Restart your Home Assistant
8) Explore & Download Repositories (depending on your version of Home Assistant)
9) Search for 'National Rail Departure Times'
10) Enjoy

## Installing the card from source

### Step 1

Clone the repository to your machine

### Step 2

Install necessary modules (verified to work in node 8.x)
`yarn install` or `npm install`

### Step 3

Do a test lint & build on the project. You can see available scripts in the package.json
`npm run build`

### Step 4

Copy content of <project_dir>/dist to your Home Assistant instance <config>/www/nationalrailtimes-card
If directories do not exist, create them.

### Step 5
Go to Settings > Dashboards, click the three dots menu in the top right and select Manage Resources.
If you do not have the three dots, you will need to temporarily enable "Advanced Mode" within Profile

### Step 6
Choose "Add Resource" and enter the following:
   URL: /local/nationalrailtimes-card/nationalrailtimes-card.js
   Resource Type: JavaScript Module

### Step 7
If you created the <config>/www directory, restart Home Assistant (Developer Tools > Restart)

<!-- Badges -->
[license-shield]: https://img.shields.io/github/license/custom-cards/boilerplate-card.svg?style=for-the-badge
[hacs-url]: https://github.com/hacs/integration
[hacs-badge]: https://img.shields.io/badge/hacs-default-orange.svg?style=flat-square


<!-- References -->

[home-assistant]: https://www.home-assistant.io/
[home-assitant-theme-docs]: https://www.home-assistant.io/integrations/frontend/#defining-themes
[hacs]: https://hacs.xyz
[ui-lovelace-minimalist]: https://ui-lovelace-minimalist.github.io/UI/
