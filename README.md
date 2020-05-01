# Emby Latest Media Component

[![hacs_badge](https://img.shields.io/badge/HACS-Custom-orange.svg?style=for-the-badge)](https://github.com/custom-components/hacs)

Home Assistant component to feed [Upcoming Media Card](https://github.com/custom-cards/upcoming-media-card) with
the latest releases on an Emby instance.</br>
This component does not require, nor conflict with, the default [Emby](https://www.home-assistant.io/components/emby/) component.</br></br>

### If you're having issues, check out the [troubleshooting guide](https://github.com/custom-cards/upcoming-media-card/blob/master/troubleshooting.md) before posting an issue or asking for help on the forums.

## Installation:

1. Install this component by copying [these files](https://github.com/gcorgnet/sensor.emby_upcoming_media/tree/master/custom_components/emby_upcoming_media) to `/custom_components/emby_upcoming_media/`.
2. Install the card: [Upcoming Media Card](https://github.com/custom-cards/upcoming-media-card)
3. Add the code to your `configuration.yaml` using the config options below.
4. Add the code for the card to your lovelace configuration.
5. **You will need to restart after installation for the component to start working.**

| key | default | required | description
| --- | --- | --- | ---
| api_key | | yes | Your Emby API key
| user_id | | yes | The id of the user you want to impersonate. Note: this is an id, not a username. Spy on Emby API calls to retrieve yours. </br>(The Libraries and Medias that get retrieved depend on what that user has access to)
| host | localhost | no | The host Emby is running on.
| port | 8096 | no | The port Emby is running on.
| ssl | false | no | Whether or not to use SSL for Emby.
| max | 5 | no | Max number of items in sensor.
| include| | no | The names or the Emby Libraries you want to include. If not specified, all libraries will be shown and this component will create one sensor per Library
</br>

**Do not just copy examples, please use config options above to build your own!**
### Sample for configuration.yaml:

```
sensor:
- platform: emby_upcoming_media
  api_key: YOUR_EMBY_API_KEY
  user_id: YOUR_EMBY_USER_ID
  host: 192.168.1.4
  port: 8096
  ssl: True
  max: 5
    include:
    - Movies
    - TV Shows
```

### Sample for ui-lovelace.yaml:

    - type: custom:upcoming-media-card
      entity: sensor.sensor.emby_latest_movies
      title: Latest Movies
