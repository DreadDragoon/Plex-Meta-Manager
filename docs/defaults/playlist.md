# Playlists

The `playlist` Default Metadata File is used to create playlists based on popular Movie/TV Show universes (such as the Marvel Cinematic Universe or Star Trek).

This Default file requires [Trakt Authentication](../config/trakt)

![](images/playlist.png)

## Playlists

| Playlist                                     |     Key     | Description                                                                       |
|:---------------------------------------------|:-----------:|:----------------------------------------------------------------------------------|
| `Arrowverse (Timeline Order)`                |   `arrow`   | Playlist of Movies and Episodes in the Arrowverse (Timeline Order)                |
| `Marvel Cinematic Universe (Timeline Order)` |    `mcu`    | Playlist of Movies and Episodes in the Marvel Cinematic Universe (Timeline Order) |
| `DC Animated Universe (Timeline Order)`      |   `dcau`    | Playlist of Movies and Episodes in the DC Animated Universe (Timeline Order)      |
| `Pokémon (Timeline Order)`                   |  `pokemon`  | Playlist of Movies and Episodes in the Pokémon (Timeline Order)                   |
| `Star Trek (Timeline Order)`                 | `startrek`  | Playlist of Movies and Episodes in the Star Trek (Timeline Order)                 |
| `Star Wars (Timeline Order)`                 | `starwars`  | Playlist of Movies and Episodes in the Star Wars (Timeline Order)                 |
| `Star Wars The Clone Wars (Timeline Order)`  | `clonewars` | Playlist of Movies and Episodes in the Star Wars The Clone Wars (Timeline Order)  |
| `X-Men (Timeline Order)`                     |   `xmen`    | Playlist of Movies and Episodes in the X-Men (Timeline Order)                     |

## Config

The below YAML in your config.yml will create the collections:

```yaml
playlist_files:
  - pmm: playlist
```

## Template Variables

Template Variables can be used to manipulate the file in various ways to slightly change how it works without having to make your own local copy.

Note that the `templates_variables:` section only needs to be used if you do want to actually change how the defaults work. Any value not specified is its default value if it has one if not it's just ignored.

**[Shared Variables](variables) are NOT available to this default file.**

| Variable                     | Description & Values                                                                                                                                                                                                                                                                         |
|:-----------------------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `use_<<key>>`                | **Description:** Turns off individual Playlists in a Defaults file.<br>**Values:** `false` to turn off the playlist                                                                                                                                                                          |
| `name_<<key>>`               | **Description:** Changes the name of the specified key's playlist.<br>**Values:** New Playlist Name                                                                                                                                                                                          |
| `summary_<<key>>`            | **Description:** Changes the summary of the specified key's playlist.<br>**Values:** New Playlist Summary                                                                                                                                                                                    |
| `libraries`                  | **Description:** Sets the names of the libraries to use for the Playlists.<br>**Default:** `Movies, TV Shows`<br>**Values:** Comma-separated string or list of library mapping names defined in the `libraries` attribute in the base of your [Configuration File](../config/configuration). |
| `trakt_list_<<key>>`         | **Description:** Adds the Movies in the Trakt List to the specified key's playlist. Overrides the [default trakt_list](#default-trakt_list) for that playlist if used.<br>**Values:** List of Trakt List URLs                                                                                |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| `ignore_ids`                 | **Description:** Set a list or comma-separated string of TMDb/TVDb IDs to ignore in all playlists.<br>**Values:** List or comma-separated string of TMDb/TVDb IDs                                                                                                                            |
| `ignore_imdb_ids`            | **Description:** Set a list or comma-separated string of IMDb IDs to ignore in all playlists.<br>**Values:** List or comma-separated string of IMDb IDs                                                                                                                                      |
| `url_poster_<<key>>`         | **Description:** Changes the poster url of the specified key's playlist.<br>**Values:** URL directly to the Image                                                                                                                                                                            |
| `radarr_add_missing`         | **Description:** Override Radarr `add_missing` attribute for all playlists in a Defaults file.<br>**Values:** `true` or `false`                                                                                                                                                              |
| `radarr_add_missing_<<key>>` | **Description:** Override Radarr `add_missing` attribute of the specified key's playlist.<br>**Default:** `radarr_add_missing`<br>**Values:** `true` or `false`                                                                                                                              |
| `radarr_folder`              | **Description:** Override Radarr `root_folder_path` attribute for all playlists in a Defaults file.<br>**Values:** Folder Path                                                                                                                                                               |
| `radarr_folder_<<key>>`      | **Description:** Override Radarr `root_folder_path` attribute of the specified key's playlist.<br>**Default:** `radarr_folder`<br>**Values:** Folder Path                                                                                                                                    |
| `radarr_tag`                 | **Description:** Override Radarr `tag` attribute for all playlists in a Defaults file.<br>**Values:** List or comma-separated string of tags                                                                                                                                                 |
| `radarr_tag_<<key>>`         | **Description:** Override Radarr `tag` attribute of the specified key's playlist.<br>**Default:** `radarr_tag`<br>**Values:** List or comma-separated string of tags                                                                                                                         |
| `item_radarr_tag`            | **Description:** Used to append a tag in Radarr for every movie found by the builders that's in Radarr for all playlists in a Defaults file.<br>**Values:** List or comma-separated string of tags                                                                                           |
| `item_radarr_tag_<<key>>`    | **Description:** Used to append a tag in Radarr for every movie found by the builders that's in Radarr of the specified key's playlist.<br>**Default:** `item_radarr_tag`<br>**Values:** List or comma-separated string of tags                                                              |
| `sonarr_add_missing`         | **Description:** Override Sonarr `add_missing` attribute for all playlists in a Defaults file.<br>**Values:** `true` or `false`                                                                                                                                                              |
| `sonarr_add_missing_<<key>>` | **Description:** Override Sonarr `add_missing` attribute of the specified key's playlist.<br>**Default:** `sonarr_add_missing`<br>**Values:** `true` or `false`                                                                                                                              |
| `sonarr_folder`              | **Description:** Override Sonarr `root_folder_path` attribute for all playlists in a Defaults file.<br>**Values:** Folder Path                                                                                                                                                               |
| `sonarr_folder_<<key>>`      | **Description:** Override Sonarr `root_folder_path` attribute of the specified key's playlist.<br>**Default:** `sonarr_folder`<br>**Values:** Folder Path                                                                                                                                    |
| `sonarr_tag`                 | **Description:** Override Sonarr `tag` attribute for all playlists in a Defaults file.<br>**Values:** List or comma-separated string of tags                                                                                                                                                 |
| `sonarr_tag_<<key>>`         | **Description:** Override Sonarr `tag` attribute of the specified key's playlist.<br>**Default:** `sonarr_tag`<br>**Values:** List or comma-separated string of tags                                                                                                                         |
| `item_sonarr_tag`            | **Description:** Used to append a tag in Sonarr for every series found by the builders that's in Sonarr for all playlists in a Defaults file.<br>**Values:** List or comma-separated string of tags                                                                                          |
| `item_sonarr_tag_<<key>>`    | **Description:** Used to append a tag in Sonarr for every series found by the builders that's in Sonarr of the specified key's playlist.<br>**Default:** `item_sonarr_tag`<br>**Values:** List or comma-separated string of tags                                                             |

The below is an example config.yml extract with some Template Variables added in to change how the file works.

```yaml
playlist_files:
  - pmm: playlist
    template_variables:
      radarr_add_missing: true
```

## Default `trakt_list`**

```yaml
trakt_list:
  arrow: https://trakt.tv/users/donxy/lists/arrowverse
  mcu: https://trakt.tv/users/donxy/lists/marvel-cinematic-universe
  dcau: https://trakt.tv/users/donxy/lists/dc-animated-series-universe
  pokemon: https://trakt.tv/users/munch54/lists/pokemon-watching-order
  startrek: https://trakt.tv/users/pedrohcramos/lists/star-trek-timeline
  starwars: https://trakt.tv/users/ruben_vw_/lists/star-wars-canon-timeline
  clonewars: https://trakt.tv/users/tomfin46/lists/star-wars-the-clone-wars-chronological-episode-order
  xmen: https://trakt.tv/users/heyitsbea/lists/x-men
```