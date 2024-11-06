
# Anime HUB Documentation

The **Anime Hub API** provides users with access to extensive information on seasonal anime releases and much more. Perfect for anime enthusiasts and developers creating anime-related platforms, this API allows users to retrieve details on current and upcoming anime, including genres, release schedules, episode counts, and other key information.

With endpoints for seasonal releases, anime metadata, and more, the **Anime Hub API** delivers structured data that’s easy to integrate, helping developers offer a comprehensive anime discovery experience. JSON responses ensure seamless integration, making it an ideal tool for enriching anime apps or websites with up-to-date content.

# Authentication
The URL you need to use is the following: `https://anime-hub.p.rapidapi.com/`
The API requires the headers listed below:

 - **`x-rapidapi-host`**: `anime-hub.p.rapidapi.com`
 - **`x-rapidapi-key`**: `YOUR_API_KEY`

Make sure to replace `YOUR_API_KEY` with your API key. You can register one [here](https://rapidapi.com/belchiorarkad-FqvHs2EDOtP/api/anime-hub/pricing).
Some frameworks automatically add extra headers, you have to make sure to remove them in order to get a response from the API.

# Endpoints
The API is configured to accept only **GET** requests. Below are the available endpoints with their descriptions and required parameters.

#### 1. **`GET /user`**
-   **Description**: This endpoint retrieves user

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `username` | string | `-` | The name of the user | Yes |


Example request:
```javascript
fetch('https://anime-hub.p.rapidapi.com/user?username=user', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'anime-hub.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
[]
```

#### 2. **`GET /episodes`**
-   **Description**: This endpoint retrieves a list of episodes for a specified anime series. Each episode entry includes details such as episode number, air date, title, and relevant discussion link.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `name` | string | `-` | Name of the anime series to fetch episodes for | Yes |
| `id` | string | `-` | Unique identifier for the anime series | Yes |


Example request:
```javascript
fetch('https://anime-hub.p.rapidapi.com/episodes?name=BLEACH&id=1', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'anime-hub.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
[
  {
    "epNumber": 1,
    "aired": "Oct 24, 1998",
    "discussionLink": "https://myanimelist.net/forum/?topicid=29264",
    "title": "Asteroid Blues",
    "...": "..."
  },
  {
    "epNumber": 2,
    "aired": "Apr 3, 1998",
    "discussionLink": "https://myanimelist.net/forum/?topicid=29323",
    "title": "Stray Dog Strut",
    "...": "..."
  },
  {
    "epNumber": 3,
    "aired": "Apr 10, 1998",
    "discussionLink": "https://myanimelist.net/forum/?topicid=29334",
    "title": "Honky Tonk Women",
    "...": "..."
  },
  {
    "epNumber": 4,
    "aired": "Nov 14, 1998",
    "discussionLink": "https://myanimelist.net/forum/?topicid=50217",
    "title": "Gateway Shuffle",
    "...": "..."
  },
  "..."
]
```



#### 3. **`GET /news`**
-   **Description**: This endpoint retrieves the latest anime-related news articles, including titles, brief descriptions, links, and images.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `perpage` | string | `-` | Number of news articles per page | No |


Example request:
```javascript
fetch('https://anime-hub.p.rapidapi.com/news?perpage=3', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'anime-hub.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
[
  {
    "title": "Voice Actor Yuu Hayashi Announces Marriage",
    "link": "https://myanimelist.net/news/71922072",
    "image": "https://cdn.myanimelist.net/r/100x156/s/common/uploaded_files/1730337358-4c4844cba26893aba357775ecf896ab3.jpeg?s=535ae8adb101cd9f702991134faa93a6",
    "text": "Voice actor Yuu Hayashi, best known for his roles as Manjiro \"Mikey\" Sano in Tokyo Revengers and Ryuunosuke Tanaka in Haikyuu!! (Haikyu!!), announced his marriage to a non-industry partner on his official X (formerly Twitter) account on Tuesday. \"I, Yuu Hayashi, have registered m...",
    "...": "..."
  },
  {
    "title": "'Kisaki Kyouiku kara Nigetai Watashi' Reveals Additional Cast, Staff, First Promo, Winter 2025 Premiere",
    "link": "https://myanimelist.net/news/71920570",
    "image": "https://cdn.myanimelist.net/r/100x156/s/common/uploaded_files/1730315282-53297fd601c60b1d9ff005c58b693865.jpeg?s=5fa3fd2e42bf8a4b9d35631ffa9db74c",
    "text": "The official website for the television anime adaptation of Izumi Sawano and Uri Sugata's Kisaki Kyouiku kara Nigetai Watashi (I Want to Escape from Princess Lessons) manga revealed additional cast, staff, theme songs, key visual (pictured), and a promotional video on Wednesday....",
    "...": "..."
  },
  {
    "title": "Pierrot Partners with South Korea's Red Dog Culture House to Produce 'Latna Saga: Survival of a Sword King' Anime",
    "link": "https://myanimelist.net/news/71917861",
    "image": "https://cdn.myanimelist.net/r/100x156/s/common/uploaded_files/1730264252-fd75b5eefcc4e1aeb140da005fc626d2.jpeg?s=aa90b634e8139a9477bf1fcd71032c4d",
    "text": " In a significant expansion move, Japan's Pierrot Co., Ltd. has signed a business alliance with South Korean animation studio Red Dog Culture House (RDCH) as of August 2024. This collaboration marks the studios' commitment to jointly produce and invest in anime content for the gl...",
    "...": "..."
  }
]
```



#### 4. **`GET /watchlist`**
-   **Description**: This endpoint retrieves the watchlist for a specified user, including details like watch status, score, tags, and rewatching status. The list can be filtered by anime or manga, and results are paginated if needed.


-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `username` | string | `-` | Username of the user whose watchlist is being retrieved | Yes |
| `after` | string | `-` | Used for pagination; specifies the offset of results to start from. By default, only the first `300` entries are returned | No |
| `type` | string | `-` | Specifies the content type, either `anime` or `manga` | No |
| `status` | string | `7` | Specifies the status filter. Defaults to `7`, which includes all entries | Yes |


Example request:
```javascript
fetch('https://anime-hub.p.rapidapi.com/watchlist?username=user', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'anime-hub.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
[
  {
    "status": 2,
    "score": 6,
    "tags": "",
    "isRewatching": 0,
    "...": "..."
  },
  {
    "status": 2,
    "score": 0,
    "tags": "",
    "isRewatching": 0,
    "...": "..."
  },
  {
    "status": 2,
    "score": 0,
    "tags": "",
    "isRewatching": 0,
    "...": "..."
  },
  {
    "status": 2,
    "score": 0,
    "tags": "",
    "isRewatching": 0,
    "...": "..."
  },
  "..."
]
```



#### 5. **`GET /search-results`**
-   **Description**: This endpoint retrieves search results based on a user query, returning anime or manga entries that match the search term.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `query` | string | `-` | Search term to find matching entries | Yes |
| `type` | string | `anime` | Type of content to search: `anime` or `manga` | No |


Example request:
```javascript
fetch('https://anime-hub.p.rapidapi.com/search-results?query=BLEACH', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'anime-hub.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
[
  {
    "id": 8247,
    "type": "anime",
    "name": "Bleach Movie 4: Jigoku-hen",
    "url": "https://myanimelist.net/anime/8247/Bleach_Movie_4__Jigoku-hen",
    "...": "..."
  },
  {
    "id": 4835,
    "type": "anime",
    "name": "Bleach Movie 3: Fade to Black - Kimi no Na wo Yobu",
    "url": "https://myanimelist.net/anime/4835/Bleach_Movie_3__Fade_to_Black_-_Kimi_no_Na_wo_Yobu",
    "...": "..."
  },
  {
    "id": 1686,
    "type": "anime",
    "name": "Bleach Movie 1: Memories of Nobody",
    "url": "https://myanimelist.net/anime/1686/Bleach_Movie_1__Memories_of_Nobody",
    "...": "..."
  },
  {
    "id": 269,
    "type": "anime",
    "name": "Bleach",
    "url": "https://myanimelist.net/anime/269/Bleach",
    "...": "..."
  },
  "..."
]
```



#### 6. **`GET /info`**
-   **Description**: This endpoint retrieves detailed information about a specified anime or manga, including synopsis, main characters, and images.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `name` | string | `-` | 	Name of the anime or manga to retrieve information for | Yes |
| `type` | string | `anime` | Specifies the type of content: `anime` or `manga` | No |


Example request:
```javascript
fetch('https://anime-hub.p.rapidapi.com/info?name=BLEACH', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'anime-hub.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "title": "Bleach Movie 4: Jigoku-hen",
  "synopsis": "When a soul has committed irredeemable sins, it is removed from the cycle of reincarnation monitored by the Soul Society, and the gates of Hell open to condemn the soul to eternal damnation. From this place from where no one has ever come back, three tormented souls who refer to themselves as Sinners of Hell burst in Karakura Town, where a ruthless fight involving them against the substitute Soul Reaper Ichigo Kurosaki and his friends ensues. In the aftermath of the fight, Ichigo's sisters are abducted, with the aforementioned group's leader Shuren hoping to lure Ichigo to be finally freed from the chains of Hell.\n\nHelped by a Sinner named Kokutou, Ichigo and his friends head to Hell for a rescue mission. However, the Soul Society opposes the journey, in fear of threatening the balance between worlds. As the lines between friends and foes get blurred, Ichigo will have to face his most challenging dilemma yet—a decision that may well engulf the three worlds into chaos.\n\n[Written by MAL Rewrite]",
  "picture": "https://cdn.myanimelist.net/images/anime/1554/134492.jpg",
  "characters": [
    {
      "link": "https://myanimelist.net/character/5/Ichigo_Kurosaki",
      "picture": "https://cdn.myanimelist.net/images/characters/3/512788.jpg",
      "name": "Kurosaki, Ichigo",
      "role": "Main",
      "...": "..."
    },
    {
      "link": "https://myanimelist.net/character/6/Rukia_Kuchiki",
      "picture": "https://cdn.myanimelist.net/images/characters/2/78215.jpg",
      "name": "Kuchiki, Rukia",
      "role": "Main",
      "...": "..."
    },
    {
      "link": "https://myanimelist.net/character/906/Renji_Abarai",
      "picture": "https://cdn.myanimelist.net/images/characters/10/171877.jpg",
      "name": "Abarai, Renji",
      "role": "Main",
      "...": "..."
    },
    {
      "link": "https://myanimelist.net/character/564/Uryuu_Ishida",
      "picture": "https://cdn.myanimelist.net/images/characters/16/139189.jpg",
      "name": "Ishida, Uryuu",
      "role": "Main",
      "...": "..."
    },
    "..."
  ],
  "...": "..."
}
```


### Advanced

#### 1. **`GET /info-from-url`**
-   **Description**: This endpoint retrieves detailed information about an anime or manga from a provided URL. It is particularly useful for fetching data from MyAnimeList (MAL) entries.

-   **Parameters**:

| Parameter        | Type     | Default               | Description     | Required |
|------------------|----------|-----------------------|-----------------|----------|
| `url` | string | `-` | The URL of the anime or manga entry from which to retrieve information. Must be properly URL-encoded. | Yes |


Example request:
```javascript
fetch('https://anime-hub.p.rapidapi.com/info-from-url?url=https%3A%2F%2Fmyanimelist.net%2Fanime%2F20047%2FSakura_Trick', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'anime-hub.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "title": "Sakura Trick",
  "synopsis": "Having been best friends since middle school, Haruka Takayama and Yuu Sonoda plan to attend Misato West High School together. However, despite being assigned to the same class, a cruel twist of fate has them seated on the opposite ends of their classroom! To make matters worse, their school will shut down in three years, making them the final intake of first-year students. Undeterred by this chain of unfortunate events, Haruka is set on sticking with Yuu, striving to create many wonderful memories with her.\n\nMuch to Haruka's jealousy however, Yuu's easygoing demeanor quickly attracts the attention of their female classmates. Sympathizing with her friend's growing insecurity, Yuu ends up sharing a deep, affectionate kiss with her in an empty classroom. The act intensifies their bond as \"special friends,\" gradually revealing a different aspect to their unique friendship while also inviting new conflicts.\n\n[Written by MAL Rewrite]",
  "picture": "https://cdn.myanimelist.net/images/anime/2/56189.jpg",
  "characters": [
    {
      "link": "https://myanimelist.net/character/86385/Haruka_Takayama",
      "picture": "https://cdn.myanimelist.net/images/characters/6/231763.jpg",
      "name": "Takayama, Haruka",
      "role": "Main",
      "...": "..."
    },
    {
      "link": "https://myanimelist.net/character/86387/Yuu_Sonoda",
      "picture": "https://cdn.myanimelist.net/images/characters/16/231761.jpg",
      "name": "Sonoda, Yuu",
      "role": "Main",
      "...": "..."
    },
    {
      "link": "https://myanimelist.net/character/94351/Yuzu_Iizuka",
      "picture": "https://cdn.myanimelist.net/images/characters/13/282698.jpg",
      "name": "Iizuka, Yuzu",
      "role": "Main",
      "...": "..."
    },
    {
      "link": "https://myanimelist.net/character/94355/Kaede_Ikeno",
      "picture": "https://cdn.myanimelist.net/images/characters/11/224575.jpg",
      "name": "Ikeno, Kaede",
      "role": "Main",
      "...": "..."
    },
    "..."
  ],
  "...": "..."
}
```



#### 2. **`GET /search`**
-   **Description**: This endpoint retrieves search results based on various extended parameters, allowing users to refine their search for anime or manga titles.

-   **Parameters**:

| Parameter     | Type   | Default | Description                                               | Required |
|---------------|--------|---------|-----------------------------------------------------------|----------|
| `maxResults`  | string | `50`    | The maximum number of results to return.                  | No       |
| `term`        | string | `-`     | The term or keyword to search for.                        | Yes      |
| `status`      | string | `-`     | Filter results by status (e.g., airing, finished).       | No       |
| `score`       | string | `-`     | Filter results by score (e.g., above a certain rating).  | No       |
| `producer`    | string | `-`     | Filter results by the producer's name.                   | No       |
| `rating`      | string | `-`     | Filter results by rating (e.g., PG, R, etc.).            | No       |
| `startDay`    | string | `-`     | Filter results by start day of airing.                   | No       |
| `startMonth`  | string | `-`     | Filter results by start month of airing.                 | No       |
| `startYear`   | string | `-`     | Filter results by start year of airing.                  | No       |
| `genreType`   | string | `-`     | Specify the genre type (e.g., include or exclude genres).| No       |
| `genres`      | string | `-`     | Comma-separated list of genres to filter by.             | No       |

Example request:
```javascript
fetch('https://anime-hub.p.rapidapi.com/search?maxResults=4&term=BLEACH', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'anime-hub.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
[
  {
    "thumbnail": "https://cdn.myanimelist.net/r/100x140/images/anime/1834/134488.jpg?s=1dbc92901ecd398b312a3703fbc1bb66",
    "url": "https://myanimelist.net/anime/1686/Bleach_Movie_1__Memories_of_Nobody",
    "video": "https://myanimelist.net/anime/1686/Bleach_Movie_1__Memories_of_Nobody/video",
    "shortDescription": "When a life ends, its soul departs to its final resting place known as the Soul Society. However, if a soul is left to wander in the human world for too long, it ends up turning into a corrupted \"Holl...read more.",
    "...": "..."
  },
  {
    "thumbnail": "https://cdn.myanimelist.net/r/100x140/images/anime/3/40451.jpg?s=ae66c4f8a3386d71d45d5f8eaff6c59e",
    "url": "https://myanimelist.net/anime/269/Bleach",
    "video": "https://myanimelist.net/anime/269/Bleach/video",
    "shortDescription": "Ichigo Kurosaki is an ordinary high schooler—until his family is attacked by a Hollow, a corrupt spirit that seeks to devour human souls. It is then that he meets a Soul Reaper named Rukia Kuchiki, wh...read more.",
    "...": "..."
  },
  {
    "thumbnail": "https://cdn.myanimelist.net/r/100x140/images/anime/12/7499.jpg?s=1f53a0aae6b9b1972f3d3950d977ac2a",
    "url": "https://myanimelist.net/anime/2889/Bleach_Movie_2__The_DiamondDust_Rebellion_-_Mou_Hitotsu_no_Hyourinmaru",
    "video": "https://myanimelist.net/anime/2889/Bleach_Movie_2__The_DiamondDust_Rebellion_-_Mou_Hitotsu_no_Hyourinmaru/video",
    "shortDescription": "Assigned to protect a royal procession transporting a powerful artifact called the \"Ouin,\" Squad 10 gathers in the human world as Captain Toushirou Hitsugaya and Lieutenant Rangiku Matsumoto observe t...read more.",
    "...": "..."
  },
  {
    "thumbnail": "https://cdn.myanimelist.net/r/100x140/images/anime/1022/129092.jpg?s=b100d0691a1d7c6a12345f7cf7699001",
    "url": "https://myanimelist.net/anime/762/Bleach__Memories_in_the_Rain",
    "video": null,
    "shortDescription": "Kurosaki Ichigo, the temporary Shinigami(Death God) for Kuchiki Rukia, discovers his mother's killer as one of the Hollows he has been hunting. He does battle with it in a prideful battle of revenge....read more.",
    "...": "..."
  },
  "..."
]
```



#### 3. **`GET /season`**
-   **Description**: This endpoint retrieves a list of anime titles based on the specified season and year. Users can filter results by season type (e.g., winter, spring, summer, fall) and genre type (e.g., TV, OVA, movie). This allows for tailored searches for current or upcoming anime releases.

-   **Parameters**:

| Parameter     | Type   | Default | Description                                               | Required |
|---------------|--------|---------|-----------------------------------------------------------|----------|
| `year`        | string | `-`     | The year for which to retrieve anime titles.             | Yes      |
| `season`      | string | `winter`| The season to filter results by. Must be either `spring`, `summer`, `fall`, or `winter`. Default is `winter`. | No       |
| `type`        | string | `-`     | The type of anime to retrieve. Must be one of the following: `TV`, `TVNew`, `TVCon`, `ONAs`, `OVAs`, `Specials`, or `Movies`. | No       |


Example request:
```javascript
fetch('https://anime-hub.p.rapidapi.com/season?year=2024', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'anime-hub.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "TV": [
    {
      "picture": "https://cdn.myanimelist.net/images/anime/1801/142390.jpg",
      "synopsis": "StudioA-1 PicturesSourceWeb mangaThemesAdult CastUrban Fantasy",
      "licensor": "",
      "title": "Ore dake Level Up na Ken",
      "...": "..."
    },
    {
      "picture": "https://cdn.myanimelist.net/images/anime/1332/139318.jpg",
      "synopsis": "StudioLercheSourceLight novelThemesPsychologicalSchool",
      "licensor": "",
      "title": "Youkoso Jitsuryoku Shijou Shugi no Kyoushitsu e 3rd Season",
      "...": "..."
    },
    {
      "picture": "https://cdn.myanimelist.net/images/anime/1711/142478.jpg",
      "synopsis": "StudioTriggerSourceMangaDemographicSeinen",
      "licensor": "",
      "title": "Dungeon Meshi",
      "...": "..."
    },
    {
      "picture": "https://cdn.myanimelist.net/images/anime/1912/140804.jpg",
      "synopsis": "StudioA-1 PicturesSourceMangaThemesGag HumorParodySchoolDemographicShounen",
      "licensor": "",
      "title": "Mashle: Shinkakusha Kouho Senbatsu Shiken-hen",
      "...": "..."
    },
    "..."
  ],
  "TVNew": [
    {
      "picture": "https://cdn.myanimelist.net/images/anime/1801/142390.jpg",
      "synopsis": "StudioA-1 PicturesSourceWeb mangaThemesAdult CastUrban Fantasy",
      "licensor": "",
      "title": "Ore dake Level Up na Ken",
      "...": "..."
    },
    {
      "picture": "https://cdn.myanimelist.net/images/anime/1332/139318.jpg",
      "synopsis": "StudioLercheSourceLight novelThemesPsychologicalSchool",
      "licensor": "",
      "title": "Youkoso Jitsuryoku Shijou Shugi no Kyoushitsu e 3rd Season",
      "...": "..."
    },
    {
      "picture": "https://cdn.myanimelist.net/images/anime/1711/142478.jpg",
      "synopsis": "StudioTriggerSourceMangaDemographicSeinen",
      "licensor": "",
      "title": "Dungeon Meshi",
      "...": "..."
    },
    {
      "picture": "https://cdn.myanimelist.net/images/anime/1912/140804.jpg",
      "synopsis": "StudioA-1 PicturesSourceMangaThemesGag HumorParodySchoolDemographicShounen",
      "licensor": "",
      "title": "Mashle: Shinkakusha Kouho Senbatsu Shiken-hen",
      "...": "..."
    },
    "..."
  ],
  "TVCon": [
    {
      "picture": "https://cdn.myanimelist.net/images/anime/1244/138851.jpg",
      "synopsis": "StudioToei AnimationSourceMangaDemographicShounen",
      "licensor": "",
      "title": "One Piece",
      "...": "..."
    },
    {
      "picture": "https://cdn.myanimelist.net/images/anime/1015/138006.jpg",
      "synopsis": "StudioMadhouseSourceMangaDemographicShounen",
      "licensor": "",
      "title": "Sousou no Frieren",
      "...": "..."
    },
    {
      "picture": "https://cdn.myanimelist.net/images/anime/1708/138033.jpg",
      "synopsis": "StudiosOLMTOHO animation STUDIOSourceLight novelThemesHistoricalMedical",
      "licensor": "",
      "title": "Kusuriya no Hitorigoto",
      "...": "..."
    },
    {
      "picture": "https://cdn.myanimelist.net/images/anime/7/75199.jpg",
      "synopsis": "StudioTMS EntertainmentSourceMangaThemeDetectiveDemographicShounen",
      "licensor": "",
      "title": "Meitantei Conan",
      "...": "..."
    },
    "..."
  ],
  "OVAs": [
    {
      "picture": "https://cdn.myanimelist.net/images/anime/1508/137052.jpg",
      "synopsis": "StudioKinema CitrusSourceNovelThemesAdult CastHistorical",
      "licensor": "",
      "title": "Watashi no Shiawase na Kekkon: Watashi no Shiawase na Katachi",
      "...": "..."
    },
    {
      "picture": "https://cdn.myanimelist.net/images/anime/1953/140539.jpg",
      "synopsis": "StudioUnknownSourceMusicThemeMusic",
      "licensor": "",
      "title": "Hajimete no Futarikkiri Ryokou",
      "...": "..."
    }
  ],
  "...": "..."
}
```



#### 4. **`GET /recommendations`**
-   **Description**: This endpoint retrieves recommendations for a specified anime based on its name or unique identifier.

-   **Parameters**:

| Parameter        | Type   | Default | Description                                               | Required |
|------------------|--------|---------|-----------------------------------------------------------|----------|
| `name`           | string | `-`     | The name of the anime for which recommendations are requested. | Yes      |
| `id`             | string | `-`     | The unique identifier of the anime for which recommendations are requested. | Yes      |


Example request:
```javascript
fetch('https://anime-hub.p.rapidapi.com/recommendations?name=BLEACH&id=1', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'anime-hub.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
[
  {
    "pictureImage": "https://cdn.myanimelist.net/r/50x70/images/anime/1370/135212.jpg?s=057b95e4f0325310cd6c3747123e7c3b",
    "animeLink": "https://myanimelist.net/anime/205/Samurai_Champloo",
    "anime": "Samurai Champloo",
    "mainRecommendation": "The music is a big influence for both anime. Hip-hop and jazz. Same director, but completely different settings. Even so, they match up very well. You can't watch one without the other. Animes from the same directors. What Cowboy Bebop is to Jazz music is the same as Samurai Champloo to Hip Hop. Beautiful animation in both and very episodic. Same Director, pretty much the spiritual successor to Cowboy Bebop,completely different world/story, their main similarity is...the awesomeness of the music, other than that, it's totally different. Although set in opposing eras, both have a strong musical theme weaving through the engaging journey of a group of accidentally travellers (for Champloo) / bounty hunters (for Bebop). Both series may seem episodic but every one is highly enjoyable. Plus all the characters have fascinating deep/dark backstories.  The same director is enough to put these series together, because Watanabe's way to create is somehow the same with Miyazaki, who share many ideas in his works. The crew contingent is ...",
    "...": "..."
  },
  {
    "pictureImage": "https://cdn.myanimelist.net/r/50x70/images/anime/1130/120002.jpg?s=c92d655c690a3f9729791339aa1fd9df",
    "animeLink": "https://myanimelist.net/anime/6/Trigun",
    "anime": "Trigun",
    "mainRecommendation": "Both these animes have great music, lovable main characters that are infailable gunmen. Both of these animes have some of the best gun martial arts, and gun fights in Anime. Trigun and Cowboy Bebop are both similar in the sense that they both have a western kind of feel to them, except one takes place in space and one takes place in an actual desert setting. Both animes have a very cool, laid back main character, but they are both different in their own rights, too, in that Trigun's main guy is very emotional and a pacifist with the insane luck and the main character of Cowboy Bebop is a bounty hunter, with amazing luck and skill, but they both have very horrible pasts and very different outlooks on life. Each episode of the anime revolves around a different bounty hunter story or a different story about helping people in a different town and every now and then they throw in some real parts about the storyline, hinting at both the past and the lives of the other characters, but it's mostly about the main character and their views on life, their pasts and they both have guns, insane main male characters and awesome fighting action scenes ...",
    "...": "..."
  },
  {
    "pictureImage": "https://cdn.myanimelist.net/r/50x70/images/anime/1906/121592.jpg?s=84c7a5dfd8ce64bd60a80454c3cc2945",
    "animeLink": "https://myanimelist.net/anime/889/Black_Lagoon",
    "anime": "Black Lagoon",
    "mainRecommendation": "both have some great gun fights,the dark backgrounds of the main characters   Similarities are overwhelming. Crude comedy, a bald leader of the group who used to be in the civil service, a hot girl with a bad attitude, a technical genius, and a ship hideaway. Also similar are the violent scenes, and guns, guns, guns. Its pretty obvious at times that Black Lagoon had gotten some inspiration from Cowboy Bebop, BL even has a similar feel to CB as well. \n\nSo if you seen CB or BL and you are looking for more some the same action awesomeness, this series is a great pick. Highly recommended! Same gun-toting badassery, same motley-crew antics, same moments of, \"holy crap, that's actually well-done characterization.\" The similarities between these two anime are not so apparent, however they do share quite a bit in common. Both shows are about a rag tag bunch of pirates (or bounty hunters, same thing, right?) who make their living dong dangerous things. Both shows are episodic in nature, and are very character driven. While not on the same par as Bebop, Black Lagoon is no slouch when it comes to character development, which is a bit of a surprise from a show whose immediate goal is to deliver as much blood, action, and gunplay as possible (which Bebop also has quite a bit of).....",
    "...": "..."
  },
  {
    "pictureImage": "https://cdn.myanimelist.net/r/50x70/images/anime/1868/145122.jpg?s=5d26df53472631aba30c778324596aa2",
    "animeLink": "https://myanimelist.net/anime/400/Seihou_Bukyou_Outlaw_Star",
    "anime": "Seihou Bukyou Outlaw Star",
    "mainRecommendation": "They are both set in space and both deal with crime and adventure. Also the animation style is similar.  Space cowboys anyone? Although at heart these two anime are completely different, they both have themes involving space, bounty hunting and drifting along in life. Fun to watch, adventurous space headhunters anime . Can't beat Cowboy Bebop , but very entertaining =P I feel as if these two anime are very simular. Mainly because its about the world in the future. Spaceships etc. The other reason would partically be because ...",
    "...": "..."
  },
  "..."
]
```



#### 5. **`GET /pictures`**
-   **Description**: This endpoint retrieves pictures related to a specified anime based on its name or unique identifier.

-   **Parameters**:

| Parameter        | Type   | Default | Description                                               | Required |
|------------------|--------|---------|-----------------------------------------------------------|----------|
| `name`           | string | `-`     | The name of the anime for which pictures are requested.   | Yes      |
| `id`             | string | `-`     | The unique identifier of the anime for which pictures are requested. | Yes      |


Example request:
```javascript
fetch('https://anime-hub.p.rapidapi.com/pictures?name=BLEACH&id=1', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'anime-hub.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
[
  {
    "imageLink": "https://cdn.myanimelist.net/images/anime/7/3791.jpg"
  },
  {
    "imageLink": "https://cdn.myanimelist.net/images/anime/12/19609.jpg"
  },
  {
    "imageLink": "https://cdn.myanimelist.net/images/anime/4/19644.jpg"
  },
  {
    "imageLink": "https://cdn.myanimelist.net/images/anime/4/22882.jpg"
  },
  "..."
]
```



#### 6. **`GET /stats`**
-   **Description**: This endpoint retrieves statistical information about a specified anime, including viewing data such as the number of people currently watching, completed, on hold, and dropped.

-   **Parameters**:

| Parameter        | Type   | Default | Description                                               | Required |
|------------------|--------|---------|-----------------------------------------------------------|----------|
| `name`           | string | `-`     | The name of the anime for which statistics are requested. | Yes      |
| `id`             | string | `-`     | The unique identifier of the anime for which statistics are requested. | Yes      |


Example request:
```javascript
fetch('https://anime-hub.p.rapidapi.com/stats?name=BLEACH&id=1', { 
  method: 'GET',
  headers: {
    'x-rapidapi-host': 'anime-hub.p.rapidapi.com',
    'x-rapidapi-key': 'API_KEY' // Replace 'API_KEY' with your API key
  }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

Example response:
```json
{
  "watching": 177575,
  "completed": 1109560,
  "onHold": 109618,
  "dropped": 44940,
  "...": "..."
}
```



## Error Handling
The API returns standard HTTP status codes to indicate the success or failure of API requests. Below are common errors and suggestions for handling them.

|Status Code|Message|Description|Suggested Handling|
|--|--|--|--|
| **400** | Bad Request | The request was malformed or missing required parameters (e.g., `domain` parameter not provided). | Verify that all required parameters are included and correctly formatted. |
| **401** | Unauthorized | Invalid or missing API key in the request headers. | Check that a valid API key is included in `x-rapidapi-key`. |
| **403** | Forbidden | Access to the requested resource is denied, possibly due to rate limits or restricted access. | Review rate limits and ensure API permissions. Retry after a delay if the rate limit is exceeded. |
| **404** | Not Found | The requested domain information could not be found (e.g., domain does not exist). | Check the spelling or availability of the domain. |
| **429** | Too Many Requests | The API rate limit has been exceeded. | Implement rate-limiting logic and retry after the specified rate limit reset time. |
| **500** | Internal Server Error | A server error occurred while processing the request. | Retry the request after a few seconds. If the error persists, contact API support. |
| **503** | Service Unavailable | The API service is temporarily unavailable (e.g., due to maintenance). | Retry the request later or check the API status page for maintenance alerts. |
