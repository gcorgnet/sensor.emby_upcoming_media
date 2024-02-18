Home Assistant component to feed [Upcoming Media Card](./146783593) with the latest media on an Emby instance.
This component does not require, nor conflict with, the default [Emby](https://www.home-assistant.io/components/emby/) component.

![Screenshot|501x592](https://community-home-assistant-assets.s3.dualstack.us-west-2.amazonaws.com/original/3X/1/e/1e51b25c36cc865222645e139cbd46e562a28e84.jpeg)

## Configuration
| key | default | required | description
| --- | --- | --- | ---
| api_key | | yes | Your Emby API key
| user_id | | yes | The id of the user you want to impersonate. Note: this is an id, not a username. Spy on Emby API calls to retrieve yours. </br>(The Libraries and Medias that get retrieved depend on what that user has access to)
| host | localhost | no | The host Emby is running on.
| port | 8096 | no | The port Emby is running on.
| ssl | false | no | Whether or not to use SSL for Emby.
| max | 5 | no | Max number of items in sensor.
| use_backdrop | false | no | Defines whether to use the Backdrop Image, instead of the poster. (Great for using with the `fanart` display mode)
| include| | no | The names of the <strong>Emby Libraries</strong> you want to include. If not specified, all libraries will be shown and this component will create one sensor per Library. This is language specific.
| group_libraries| false| no | This option generates only two sensors (emby_latest_movies / emby_latest_tv_shows), grouping all your movies and tv into seperate sensors despite library setup in Emby. </br>This is useful for when Emby has many libraries but you only want one sensor in Home Assistant.
| episodes | true | no | Setting this to false will change the items shown from Episodes to Seasons (for tv show libraries) and Songs to Albums (for music libraries).
