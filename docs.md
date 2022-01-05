---
title: Unsplash API v1
language_tabs:
  - shell: cURL
toc_footers:
  - <a href="https://unsplash.com/documentation">Find out more about Unsplash</a>
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="unsplash-api">Unsplash API v1</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

This document describes the resources that make up the official Unsplash JSON API.

Base URLs:

* <a href="https://api.unsplash.com/">https://api.unsplash.com/</a>

<a href="https://unsplash.com/api-terms">Terms of service</a>

# Authentication

* API Key (publicAuth)
    - Parameter Name: **Authorization**, in: header. Add token in the form \"Client-ID {TOKEN}\"

- HTTP Authentication, scheme: bearer Bearer token

<h1 id="unsplash-api-current-user">Current user</h1>

<a href="https://unsplash.com/documentation#current-user">Find out more</a>

## getCurrentUser

<a id="opIdgetCurrentUser"></a>

> Code samples

```shell
curl --request GET \
  --url https://api.unsplash.com//me \
  --header 'Accept: application/json' \
  --header 'Authorization: Bearer {access-token}'
```

`GET /me`

*Get the user’s profile*

Note: To access a user’s private data, the user is required to authorize the read_user scope. Without a Bearer token (i.e. using a Client-ID token) this request will return a 401 Unauthorized response.

> Example responses

> 200 Response

```json
{
  "bio": "string",
  "downloads": 0,
  "email": "string",
  "first_name": "string",
  "followed_by_user": true,
  "id": "string",
  "instagram_username": "string",
  "last_name": "string",
  "links": {
    "html": "string",
    "likes": "string",
    "photos": "string",
    "portfolio": "string",
    "self": "string"
  },
  "location": "string",
  "portfolio_url": "string",
  "total_collections": 0,
  "total_likes": 0,
  "total_photos": 0,
  "twitter_username": "string",
  "updated_at": "string",
  "uploads_remaining": 0,
  "username": "string"
}
```

<h3 id="getcurrentuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[CurrentUser](#schemacurrentuser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
userAuth ( Scopes: read_user )
</aside>

## updateCurrentUser

<a id="opIdupdateCurrentUser"></a>

> Code samples

```shell
curl --request PUT \
  --url 'https://api.unsplash.com//me?bio=string' \
  --header 'Accept: application/json' \
  --header 'Authorization: Bearer {access-token}'
```

`PUT /me`

*Update the current user’s profile*

Note: This action requires the write_user scope. Without it, it will return a 403 Forbidden response.

<h3 id="updatecurrentuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|query|string|false|Username.|
|first_name|query|string|false|First name.|
|last_name|query|string|false|Last name.|
|email|query|string|false|Email.|
|url|query|string|false|Portfolio/personal URL.|
|location|query|string|false|Location.|
|bio|query|string|true|About/bio.|
|instagram_username|query|string|false|Instagram username.|

> Example responses

> 200 Response

```json
{
  "bio": "string",
  "downloads": 0,
  "email": "string",
  "first_name": "string",
  "followed_by_user": true,
  "id": "string",
  "instagram_username": "string",
  "last_name": "string",
  "links": {
    "html": "string",
    "likes": "string",
    "photos": "string",
    "portfolio": "string",
    "self": "string"
  },
  "location": "string",
  "portfolio_url": "string",
  "total_collections": 0,
  "total_likes": 0,
  "total_photos": 0,
  "twitter_username": "string",
  "updated_at": "string",
  "uploads_remaining": 0,
  "username": "string"
}
```

<h3 id="updatecurrentuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[CurrentUser](#schemacurrentuser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
userAuth ( Scopes: write_user )
</aside>

<h1 id="unsplash-api-users">Users</h1>

<a href="https://unsplash.com/documentation#users">Find out more</a>

## getUser

<a id="opIdgetUser"></a>

> Code samples

```shell
curl --request GET \
  --url https://api.unsplash.com//users/string \
  --header 'Accept: application/json' \
  --header 'Authorization: API_KEY'
```

`GET /users/{username}`

*Get a user’s public profile*

Retrieve public details on a given user.

<h3 id="getuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|The user’s username.|

> Example responses

> 200 Response

```json
{
  "badge": {
    "link": "string",
    "primary": true,
    "slug": "string",
    "title": "string"
  },
  "bio": "string",
  "downloads": 0,
  "first_name": "string",
  "followed_by_user": true,
  "followers_count": 0,
  "following_count": 0,
  "id": "string",
  "instagram_username": "string",
  "last_name": "string",
  "links": {
    "html": "string",
    "likes": "string",
    "photos": "string",
    "portfolio": "string",
    "self": "string"
  },
  "location": "string",
  "name": "string",
  "portfolio_url": "string",
  "profile_image": {
    "small": "string",
    "medium": "string",
    "large": "string"
  },
  "total_collections": 0,
  "total_likes": 0,
  "total_photos": 0,
  "twitter_username": "string",
  "updated_at": "2019-08-24T14:15:22Z",
  "username": "string"
}
```

<h3 id="getuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[User](#schemauser)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
publicAuth
</aside>

## getUserPortfolioLink

<a id="opIdgetUserPortfolioLink"></a>

> Code samples

```shell
curl --request GET \
  --url https://api.unsplash.com//users/string/portfolio \
  --header 'Accept: application/json' \
  --header 'Authorization: API_KEY'
```

`GET /users/{username}/portfolio`

*Get a user’s portfolio link*

<h3 id="getuserportfoliolink-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|The user’s username.|

> Example responses

> 200 Response

```json
{
  "url": "string"
}
```

<h3 id="getuserportfoliolink-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[PortfolioLink](#schemaportfoliolink)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
publicAuth
</aside>

## getUserPhotos

<a id="opIdgetUserPhotos"></a>

> Code samples

```shell
curl --request GET \
  --url https://api.unsplash.com//users/string/photos \
  --header 'Accept: application/json' \
  --header 'Authorization: API_KEY'
```

`GET /users/{username}/photos`

*List a user’s photos*

Get a list of photos uploaded by a user.

<h3 id="getuserphotos-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|The user’s username.|
|page|query|integer|false|Page number to retrieve. (Optional, default: 1)|
|per_page|query|integer|false|Number of items per page. (Optional; default: 10)|
|order_by|query|[OrderBy](#schemaorderby)|false|How to sort the photos. Optional. (Valid values: latest, oldest, popular; default: latest)|
|stats|query|boolean|false|Show the stats for each user’s photo. (Optional; default: false)|
|resolution|query|[StatResolution](#schemastatresolution)|false|The frequency of the stats. (Optional; default: “days”)|
|quantity|query|integer|false|The amount of for each stat. (Optional; default: 30)|
|orientation|query|[Orientation](#schemaorientation)|false|Filter by photo orientation. Optional. (Valid values: landscape, portrait, squarish)|

#### Detailed descriptions

**page**: Page number to retrieve. (Optional, default: 1)

**per_page**: Number of items per page. (Optional; default: 10)

**order_by**: How to sort the photos. Optional. (Valid values: latest, oldest, popular; default: latest)

**stats**: Show the stats for each user’s photo. (Optional; default: false)

**resolution**: The frequency of the stats. (Optional; default: “days”)

**quantity**: The amount of for each stat. (Optional; default: 30)

**orientation**: Filter by photo orientation. Optional. (Valid values: landscape, portrait, squarish)

#### Enumerated Values

|Parameter|Value|
|---|---|
|order_by|latest|
|order_by|oldest|
|order_by|popular|
|resolution|days|
|orientation|landscape|
|orientation|portrait|
|orientation|squarish|

> Example responses

> 200 Response

```json
[
  {
    "blur_hash": "string",
    "color": "string",
    "created_at": "2019-08-24T14:15:22Z",
    "current_user_collections": [
      {
        "cover_photo": {},
        "description": "string",
        "featured": true,
        "id": 0,
        "last_collected_at": "2019-08-24T14:15:22Z",
        "links": {
          "html": "string",
          "photos": "string",
          "related": "string",
          "self": "string"
        },
        "private": true,
        "published_at": "2019-08-24T14:15:22Z",
        "share_key": "string",
        "title": "string",
        "total_photos": true,
        "updated_at": "2019-08-24T14:15:22Z",
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        }
      }
    ],
    "description": "string",
    "downloads": 0,
    "exif": {
      "make": "string",
      "model": "string",
      "exposure_time": "string",
      "aperture": 0,
      "focal_length": 0,
      "iso": 0
    },
    "height": 0,
    "id": "string",
    "liked_by_user": true,
    "likes": 0,
    "links": {
      "download": "string",
      "download_location": "string",
      "html": "string",
      "self": "string"
    },
    "location": {
      "city": "string",
      "country": "string",
      "name": "string",
      "position": {
        "latitude": 0,
        "longitude": 0
      }
    },
    "tags": [
      {
        "title": "string"
      }
    ],
    "updated_at": "2019-08-24T14:15:22Z",
    "urls": {
      "raw": "string",
      "full": "string",
      "regular": "string",
      "small": "string",
      "thumb": "string"
    },
    "user": {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    },
    "width": 0
  }
]
```

<h3 id="getuserphotos-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="getuserphotos-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Photo](#schemaphoto)]|false|none|none|
|» blur_hash|string|false|none|none|
|» color|string|false|none|none|
|» created_at|string(date-time)|false|none|none|
|» current_user_collections|[[Collection](#schemacollection)]|false|none|none|
|»» cover_photo|[Photo](#schemaphoto)|false|none|none|
|»» description|string|false|none|none|
|»» featured|boolean|false|none|none|
|»» id|integer|false|none|none|
|»» last_collected_at|string(date-time)|false|none|none|
|»» links|[CollectionLinks](#schemacollectionlinks)|false|none|none|
|»»» html|string|false|none|none|
|»»» photos|string|false|none|none|
|»»» related|string|false|none|none|
|»»» self|string|false|none|none|
|»» private|boolean|false|none|none|
|»» published_at|string(date-time)|false|none|none|
|»» share_key|string|false|none|none|
|»» title|string|false|none|none|
|»» total_photos|boolean|false|none|none|
|»» updated_at|string(date-time)|false|none|none|
|»» user|[User](#schemauser)|false|none|none|
|»»» badge|object|false|none|none|
|»»»» link|string|false|none|none|
|»»»» primary|boolean|false|none|none|
|»»»» slug|string|false|none|none|
|»»»» title|string|false|none|none|
|»»» bio|string|false|none|none|
|»»» downloads|integer|false|none|none|
|»»» first_name|string|false|none|none|
|»»» followed_by_user|boolean|false|none|none|
|»»» followers_count|integer|false|none|none|
|»»» following_count|integer|false|none|none|
|»»» id|string|false|none|none|
|»»» instagram_username|string|false|none|none|
|»»» last_name|string|false|none|none|
|»»» links|[UserLinks](#schemauserlinks)|false|none|none|
|»»»» html|string|false|none|none|
|»»»» likes|string|false|none|none|
|»»»» photos|string|false|none|none|
|»»»» portfolio|string|false|none|none|
|»»»» self|string|false|none|none|
|»»» location|string|false|none|none|
|»»» name|string|false|none|none|
|»»» portfolio_url|string|false|none|none|
|»»» profile_image|[ProfileImage](#schemaprofileimage)|false|none|none|
|»»»» small|string|false|none|none|
|»»»» medium|string|false|none|none|
|»»»» large|string|false|none|none|
|»»» total_collections|integer|false|none|none|
|»»» total_likes|integer|false|none|none|
|»»» total_photos|integer|false|none|none|
|»»» twitter_username|string|false|none|none|
|»»» updated_at|string(date-time)|false|none|none|
|»»» username|string|false|none|none|
|» description|string|false|none|none|
|» downloads|integer|false|none|none|
|» exif|[Exif](#schemaexif)|false|none|none|
|»» make|string|false|none|none|
|»» model|string|false|none|none|
|»» exposure_time|string|false|none|none|
|»» aperture|number(double)|false|none|none|
|»» focal_length|number(double)|false|none|none|
|»» iso|integer|false|none|none|
|» height|integer|false|none|none|
|» id|string|false|none|none|
|» liked_by_user|boolean|false|none|none|
|» likes|integer|false|none|none|
|» links|[PhotoLinks](#schemaphotolinks)|false|none|none|
|»» download|string|false|none|none|
|»» download_location|string|false|none|none|
|»» html|string|false|none|none|
|»» self|string|false|none|none|
|» location|[Location](#schemalocation)|false|none|none|
|»» city|string|false|none|none|
|»» country|string|false|none|none|
|»» name|string|false|none|none|
|»» position|object|false|none|none|
|»»» latitude|number(double)|false|none|none|
|»»» longitude|number(double)|false|none|none|
|» tags|[object]|false|none|none|
|»» title|string|false|none|none|
|» updated_at|string(date-time)|false|none|none|
|» urls|[PhotoUrls](#schemaphotourls)|false|none|none|
|»» raw|string|false|none|none|
|»» full|string|false|none|none|
|»» regular|string|false|none|none|
|»» small|string|false|none|none|
|»» thumb|string|false|none|none|
|» user|[User](#schemauser)|false|none|none|
|» width|integer|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
publicAuth
</aside>

## getUserLikedPhotos

<a id="opIdgetUserLikedPhotos"></a>

> Code samples

```shell
curl --request GET \
  --url https://api.unsplash.com//users/string/likes \
  --header 'Accept: application/json' \
  --header 'Authorization: API_KEY'
```

`GET /users/{username}/likes`

*List a user's liked photos*

Get a list of photos liked by a user.

<h3 id="getuserlikedphotos-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|The user’s username.|
|page|query|integer|false|Page number to retrieve. (Optional, default: 1)|
|per_page|query|integer|false|Number of items per page. (Optional; default: 10)|
|order_by|query|[OrderBy](#schemaorderby)|false|How to sort the photos. Optional. (Valid values: latest, oldest, popular; default: latest)|
|orientation|query|[Orientation](#schemaorientation)|false|Filter by photo orientation. Optional. (Valid values: landscape, portrait, squarish)|

#### Detailed descriptions

**username**: The user’s username.

**page**: Page number to retrieve. (Optional, default: 1)

**per_page**: Number of items per page. (Optional; default: 10)

**order_by**: How to sort the photos. Optional. (Valid values: latest, oldest, popular; default: latest)

**orientation**: Filter by photo orientation. Optional. (Valid values: landscape, portrait, squarish)

#### Enumerated Values

|Parameter|Value|
|---|---|
|order_by|latest|
|order_by|oldest|
|order_by|popular|
|orientation|landscape|
|orientation|portrait|
|orientation|squarish|

> Example responses

> 200 Response

```json
[
  {
    "blur_hash": "string",
    "color": "string",
    "created_at": "2019-08-24T14:15:22Z",
    "current_user_collections": [
      {
        "cover_photo": {},
        "description": "string",
        "featured": true,
        "id": 0,
        "last_collected_at": "2019-08-24T14:15:22Z",
        "links": {
          "html": "string",
          "photos": "string",
          "related": "string",
          "self": "string"
        },
        "private": true,
        "published_at": "2019-08-24T14:15:22Z",
        "share_key": "string",
        "title": "string",
        "total_photos": true,
        "updated_at": "2019-08-24T14:15:22Z",
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        }
      }
    ],
    "description": "string",
    "downloads": 0,
    "exif": {
      "make": "string",
      "model": "string",
      "exposure_time": "string",
      "aperture": 0,
      "focal_length": 0,
      "iso": 0
    },
    "height": 0,
    "id": "string",
    "liked_by_user": true,
    "likes": 0,
    "links": {
      "download": "string",
      "download_location": "string",
      "html": "string",
      "self": "string"
    },
    "location": {
      "city": "string",
      "country": "string",
      "name": "string",
      "position": {
        "latitude": 0,
        "longitude": 0
      }
    },
    "tags": [
      {
        "title": "string"
      }
    ],
    "updated_at": "2019-08-24T14:15:22Z",
    "urls": {
      "raw": "string",
      "full": "string",
      "regular": "string",
      "small": "string",
      "thumb": "string"
    },
    "user": {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    },
    "width": 0
  }
]
```

<h3 id="getuserlikedphotos-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="getuserlikedphotos-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Photo](#schemaphoto)]|false|none|none|
|» blur_hash|string|false|none|none|
|» color|string|false|none|none|
|» created_at|string(date-time)|false|none|none|
|» current_user_collections|[[Collection](#schemacollection)]|false|none|none|
|»» cover_photo|[Photo](#schemaphoto)|false|none|none|
|»» description|string|false|none|none|
|»» featured|boolean|false|none|none|
|»» id|integer|false|none|none|
|»» last_collected_at|string(date-time)|false|none|none|
|»» links|[CollectionLinks](#schemacollectionlinks)|false|none|none|
|»»» html|string|false|none|none|
|»»» photos|string|false|none|none|
|»»» related|string|false|none|none|
|»»» self|string|false|none|none|
|»» private|boolean|false|none|none|
|»» published_at|string(date-time)|false|none|none|
|»» share_key|string|false|none|none|
|»» title|string|false|none|none|
|»» total_photos|boolean|false|none|none|
|»» updated_at|string(date-time)|false|none|none|
|»» user|[User](#schemauser)|false|none|none|
|»»» badge|object|false|none|none|
|»»»» link|string|false|none|none|
|»»»» primary|boolean|false|none|none|
|»»»» slug|string|false|none|none|
|»»»» title|string|false|none|none|
|»»» bio|string|false|none|none|
|»»» downloads|integer|false|none|none|
|»»» first_name|string|false|none|none|
|»»» followed_by_user|boolean|false|none|none|
|»»» followers_count|integer|false|none|none|
|»»» following_count|integer|false|none|none|
|»»» id|string|false|none|none|
|»»» instagram_username|string|false|none|none|
|»»» last_name|string|false|none|none|
|»»» links|[UserLinks](#schemauserlinks)|false|none|none|
|»»»» html|string|false|none|none|
|»»»» likes|string|false|none|none|
|»»»» photos|string|false|none|none|
|»»»» portfolio|string|false|none|none|
|»»»» self|string|false|none|none|
|»»» location|string|false|none|none|
|»»» name|string|false|none|none|
|»»» portfolio_url|string|false|none|none|
|»»» profile_image|[ProfileImage](#schemaprofileimage)|false|none|none|
|»»»» small|string|false|none|none|
|»»»» medium|string|false|none|none|
|»»»» large|string|false|none|none|
|»»» total_collections|integer|false|none|none|
|»»» total_likes|integer|false|none|none|
|»»» total_photos|integer|false|none|none|
|»»» twitter_username|string|false|none|none|
|»»» updated_at|string(date-time)|false|none|none|
|»»» username|string|false|none|none|
|» description|string|false|none|none|
|» downloads|integer|false|none|none|
|» exif|[Exif](#schemaexif)|false|none|none|
|»» make|string|false|none|none|
|»» model|string|false|none|none|
|»» exposure_time|string|false|none|none|
|»» aperture|number(double)|false|none|none|
|»» focal_length|number(double)|false|none|none|
|»» iso|integer|false|none|none|
|» height|integer|false|none|none|
|» id|string|false|none|none|
|» liked_by_user|boolean|false|none|none|
|» likes|integer|false|none|none|
|» links|[PhotoLinks](#schemaphotolinks)|false|none|none|
|»» download|string|false|none|none|
|»» download_location|string|false|none|none|
|»» html|string|false|none|none|
|»» self|string|false|none|none|
|» location|[Location](#schemalocation)|false|none|none|
|»» city|string|false|none|none|
|»» country|string|false|none|none|
|»» name|string|false|none|none|
|»» position|object|false|none|none|
|»»» latitude|number(double)|false|none|none|
|»»» longitude|number(double)|false|none|none|
|» tags|[object]|false|none|none|
|»» title|string|false|none|none|
|» updated_at|string(date-time)|false|none|none|
|» urls|[PhotoUrls](#schemaphotourls)|false|none|none|
|»» raw|string|false|none|none|
|»» full|string|false|none|none|
|»» regular|string|false|none|none|
|»» small|string|false|none|none|
|»» thumb|string|false|none|none|
|» user|[User](#schemauser)|false|none|none|
|» width|integer|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
publicAuth
</aside>

## getUserCollections

<a id="opIdgetUserCollections"></a>

> Code samples

```shell
curl --request GET \
  --url https://api.unsplash.com//users/string/collections \
  --header 'Accept: application/json' \
  --header 'Authorization: API_KEY'
```

`GET /users/{username}/collections`

*List a user’s collections*

Get a list of collections created by the user.

<h3 id="getusercollections-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|The user’s username.|
|page|query|integer|false|Page number to retrieve. (Optional, default: 1)|
|per_page|query|integer|false|Number of items per page. (Optional; default: 10)|

#### Detailed descriptions

**page**: Page number to retrieve. (Optional, default: 1)

**per_page**: Number of items per page. (Optional; default: 10)

> Example responses

> 200 Response

```json
[
  {
    "cover_photo": {
      "blur_hash": "string",
      "color": "string",
      "created_at": "2019-08-24T14:15:22Z",
      "current_user_collections": [
        {}
      ],
      "description": "string",
      "downloads": 0,
      "exif": {
        "make": "string",
        "model": "string",
        "exposure_time": "string",
        "aperture": 0,
        "focal_length": 0,
        "iso": 0
      },
      "height": 0,
      "id": "string",
      "liked_by_user": true,
      "likes": 0,
      "links": {
        "download": "string",
        "download_location": "string",
        "html": "string",
        "self": "string"
      },
      "location": {
        "city": "string",
        "country": "string",
        "name": "string",
        "position": {
          "latitude": 0,
          "longitude": 0
        }
      },
      "tags": [
        {
          "title": "string"
        }
      ],
      "updated_at": "2019-08-24T14:15:22Z",
      "urls": {
        "raw": "string",
        "full": "string",
        "regular": "string",
        "small": "string",
        "thumb": "string"
      },
      "user": {
        "badge": {
          "link": "string",
          "primary": true,
          "slug": "string",
          "title": "string"
        },
        "bio": "string",
        "downloads": 0,
        "first_name": "string",
        "followed_by_user": true,
        "followers_count": 0,
        "following_count": 0,
        "id": "string",
        "instagram_username": "string",
        "last_name": "string",
        "links": {
          "html": "string",
          "likes": "string",
          "photos": "string",
          "portfolio": "string",
          "self": "string"
        },
        "location": "string",
        "name": "string",
        "portfolio_url": "string",
        "profile_image": {
          "small": "string",
          "medium": "string",
          "large": "string"
        },
        "total_collections": 0,
        "total_likes": 0,
        "total_photos": 0,
        "twitter_username": "string",
        "updated_at": "2019-08-24T14:15:22Z",
        "username": "string"
      },
      "width": 0
    },
    "description": "string",
    "featured": true,
    "id": 0,
    "last_collected_at": "2019-08-24T14:15:22Z",
    "links": {
      "html": "string",
      "photos": "string",
      "related": "string",
      "self": "string"
    },
    "private": true,
    "published_at": "2019-08-24T14:15:22Z",
    "share_key": "string",
    "title": "string",
    "total_photos": true,
    "updated_at": "2019-08-24T14:15:22Z",
    "user": {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    }
  }
]
```

<h3 id="getusercollections-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="getusercollections-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Collection](#schemacollection)]|false|none|none|
|» cover_photo|[Photo](#schemaphoto)|false|none|none|
|»» blur_hash|string|false|none|none|
|»» color|string|false|none|none|
|»» created_at|string(date-time)|false|none|none|
|»» current_user_collections|[[Collection](#schemacollection)]|false|none|none|
|»» description|string|false|none|none|
|»» downloads|integer|false|none|none|
|»» exif|[Exif](#schemaexif)|false|none|none|
|»»» make|string|false|none|none|
|»»» model|string|false|none|none|
|»»» exposure_time|string|false|none|none|
|»»» aperture|number(double)|false|none|none|
|»»» focal_length|number(double)|false|none|none|
|»»» iso|integer|false|none|none|
|»» height|integer|false|none|none|
|»» id|string|false|none|none|
|»» liked_by_user|boolean|false|none|none|
|»» likes|integer|false|none|none|
|»» links|[PhotoLinks](#schemaphotolinks)|false|none|none|
|»»» download|string|false|none|none|
|»»» download_location|string|false|none|none|
|»»» html|string|false|none|none|
|»»» self|string|false|none|none|
|»» location|[Location](#schemalocation)|false|none|none|
|»»» city|string|false|none|none|
|»»» country|string|false|none|none|
|»»» name|string|false|none|none|
|»»» position|object|false|none|none|
|»»»» latitude|number(double)|false|none|none|
|»»»» longitude|number(double)|false|none|none|
|»» tags|[object]|false|none|none|
|»»» title|string|false|none|none|
|»» updated_at|string(date-time)|false|none|none|
|»» urls|[PhotoUrls](#schemaphotourls)|false|none|none|
|»»» raw|string|false|none|none|
|»»» full|string|false|none|none|
|»»» regular|string|false|none|none|
|»»» small|string|false|none|none|
|»»» thumb|string|false|none|none|
|»» user|[User](#schemauser)|false|none|none|
|»»» badge|object|false|none|none|
|»»»» link|string|false|none|none|
|»»»» primary|boolean|false|none|none|
|»»»» slug|string|false|none|none|
|»»»» title|string|false|none|none|
|»»» bio|string|false|none|none|
|»»» downloads|integer|false|none|none|
|»»» first_name|string|false|none|none|
|»»» followed_by_user|boolean|false|none|none|
|»»» followers_count|integer|false|none|none|
|»»» following_count|integer|false|none|none|
|»»» id|string|false|none|none|
|»»» instagram_username|string|false|none|none|
|»»» last_name|string|false|none|none|
|»»» links|[UserLinks](#schemauserlinks)|false|none|none|
|»»»» html|string|false|none|none|
|»»»» likes|string|false|none|none|
|»»»» photos|string|false|none|none|
|»»»» portfolio|string|false|none|none|
|»»»» self|string|false|none|none|
|»»» location|string|false|none|none|
|»»» name|string|false|none|none|
|»»» portfolio_url|string|false|none|none|
|»»» profile_image|[ProfileImage](#schemaprofileimage)|false|none|none|
|»»»» small|string|false|none|none|
|»»»» medium|string|false|none|none|
|»»»» large|string|false|none|none|
|»»» total_collections|integer|false|none|none|
|»»» total_likes|integer|false|none|none|
|»»» total_photos|integer|false|none|none|
|»»» twitter_username|string|false|none|none|
|»»» updated_at|string(date-time)|false|none|none|
|»»» username|string|false|none|none|
|»» width|integer|false|none|none|
|» description|string|false|none|none|
|» featured|boolean|false|none|none|
|» id|integer|false|none|none|
|» last_collected_at|string(date-time)|false|none|none|
|» links|[CollectionLinks](#schemacollectionlinks)|false|none|none|
|»» html|string|false|none|none|
|»» photos|string|false|none|none|
|»» related|string|false|none|none|
|»» self|string|false|none|none|
|» private|boolean|false|none|none|
|» published_at|string(date-time)|false|none|none|
|» share_key|string|false|none|none|
|» title|string|false|none|none|
|» total_photos|boolean|false|none|none|
|» updated_at|string(date-time)|false|none|none|
|» user|[User](#schemauser)|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
publicAuth
</aside>

## getUserStatistics

<a id="opIdgetUserStatistics"></a>

> Code samples

```shell
curl --request GET \
  --url https://api.unsplash.com//users/string/statistics \
  --header 'Accept: application/json' \
  --header 'Authorization: API_KEY'
```

`GET /users/{username}/statistics`

*Get a user’s statistics*

Retrieve the consolidated number of downloads, views and likes of all user’s photos, as well as the historical breakdown and average of these stats in a specific timeframe (default is 30 days).

<h3 id="getuserstatistics-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|The user’s username.|
|resolution|query|[StatResolution](#schemastatresolution)|false|The frequency of the stats. (Optional; default: “days”)|
|quantity|query|integer|false|	The amount of for each stat. (Optional; default: 30)|

#### Detailed descriptions

**resolution**: The frequency of the stats. (Optional; default: “days”)

**quantity**: 	The amount of for each stat. (Optional; default: 30)

#### Enumerated Values

|Parameter|Value|
|---|---|
|resolution|days|

> Example responses

> 200 Response

```json
{
  "downloads": {
    "total": 0,
    "historical": {
      "change": 0,
      "average": 0,
      "resolution": "days",
      "quantity": 0,
      "values": [
        {
          "date": "2019-08-24",
          "value": 0
        }
      ]
    }
  },
  "likes": {
    "total": 0,
    "historical": {
      "change": 0,
      "average": 0,
      "resolution": "days",
      "quantity": 0,
      "values": [
        {
          "date": "2019-08-24",
          "value": 0
        }
      ]
    }
  },
  "username": "string",
  "views": {
    "total": 0,
    "historical": {
      "change": 0,
      "average": 0,
      "resolution": "days",
      "quantity": 0,
      "values": [
        {
          "date": "2019-08-24",
          "value": 0
        }
      ]
    }
  }
}
```

<h3 id="getuserstatistics-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[UserStatistics](#schemauserstatistics)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
publicAuth
</aside>

<h1 id="unsplash-api-photos">Photos</h1>

<a href="https://unsplash.com/documentation#photos">Find out more</a>

## getPhotos

<a id="opIdgetPhotos"></a>

> Code samples

```shell
curl --request GET \
  --url https://api.unsplash.com//photos \
  --header 'Accept: application/json' \
  --header 'Authorization: API_KEY'
```

`GET /photos`

*List photos*

Get a single page from the list of all photos.

<h3 id="getphotos-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|Page number to retrieve. (Optional, default: 1)|
|per_page|query|integer|false|Number of items per page. (Optional; default: 10)|
|order_by|query|[OrderBy](#schemaorderby)|false|How to sort the photos. Optional. (Valid values: latest, oldest, popular; default: latest)|

#### Detailed descriptions

**page**: Page number to retrieve. (Optional, default: 1)

**per_page**: Number of items per page. (Optional; default: 10)

**order_by**: How to sort the photos. Optional. (Valid values: latest, oldest, popular; default: latest)

#### Enumerated Values

|Parameter|Value|
|---|---|
|order_by|latest|
|order_by|oldest|
|order_by|popular|

> Example responses

> 200 Response

```json
[
  {
    "blur_hash": "string",
    "color": "string",
    "created_at": "2019-08-24T14:15:22Z",
    "current_user_collections": [
      {
        "cover_photo": {},
        "description": "string",
        "featured": true,
        "id": 0,
        "last_collected_at": "2019-08-24T14:15:22Z",
        "links": {
          "html": "string",
          "photos": "string",
          "related": "string",
          "self": "string"
        },
        "private": true,
        "published_at": "2019-08-24T14:15:22Z",
        "share_key": "string",
        "title": "string",
        "total_photos": true,
        "updated_at": "2019-08-24T14:15:22Z",
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        }
      }
    ],
    "description": "string",
    "downloads": 0,
    "exif": {
      "make": "string",
      "model": "string",
      "exposure_time": "string",
      "aperture": 0,
      "focal_length": 0,
      "iso": 0
    },
    "height": 0,
    "id": "string",
    "liked_by_user": true,
    "likes": 0,
    "links": {
      "download": "string",
      "download_location": "string",
      "html": "string",
      "self": "string"
    },
    "location": {
      "city": "string",
      "country": "string",
      "name": "string",
      "position": {
        "latitude": 0,
        "longitude": 0
      }
    },
    "tags": [
      {
        "title": "string"
      }
    ],
    "updated_at": "2019-08-24T14:15:22Z",
    "urls": {
      "raw": "string",
      "full": "string",
      "regular": "string",
      "small": "string",
      "thumb": "string"
    },
    "user": {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    },
    "width": 0
  }
]
```

<h3 id="getphotos-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="getphotos-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Photo](#schemaphoto)]|false|none|none|
|» blur_hash|string|false|none|none|
|» color|string|false|none|none|
|» created_at|string(date-time)|false|none|none|
|» current_user_collections|[[Collection](#schemacollection)]|false|none|none|
|»» cover_photo|[Photo](#schemaphoto)|false|none|none|
|»» description|string|false|none|none|
|»» featured|boolean|false|none|none|
|»» id|integer|false|none|none|
|»» last_collected_at|string(date-time)|false|none|none|
|»» links|[CollectionLinks](#schemacollectionlinks)|false|none|none|
|»»» html|string|false|none|none|
|»»» photos|string|false|none|none|
|»»» related|string|false|none|none|
|»»» self|string|false|none|none|
|»» private|boolean|false|none|none|
|»» published_at|string(date-time)|false|none|none|
|»» share_key|string|false|none|none|
|»» title|string|false|none|none|
|»» total_photos|boolean|false|none|none|
|»» updated_at|string(date-time)|false|none|none|
|»» user|[User](#schemauser)|false|none|none|
|»»» badge|object|false|none|none|
|»»»» link|string|false|none|none|
|»»»» primary|boolean|false|none|none|
|»»»» slug|string|false|none|none|
|»»»» title|string|false|none|none|
|»»» bio|string|false|none|none|
|»»» downloads|integer|false|none|none|
|»»» first_name|string|false|none|none|
|»»» followed_by_user|boolean|false|none|none|
|»»» followers_count|integer|false|none|none|
|»»» following_count|integer|false|none|none|
|»»» id|string|false|none|none|
|»»» instagram_username|string|false|none|none|
|»»» last_name|string|false|none|none|
|»»» links|[UserLinks](#schemauserlinks)|false|none|none|
|»»»» html|string|false|none|none|
|»»»» likes|string|false|none|none|
|»»»» photos|string|false|none|none|
|»»»» portfolio|string|false|none|none|
|»»»» self|string|false|none|none|
|»»» location|string|false|none|none|
|»»» name|string|false|none|none|
|»»» portfolio_url|string|false|none|none|
|»»» profile_image|[ProfileImage](#schemaprofileimage)|false|none|none|
|»»»» small|string|false|none|none|
|»»»» medium|string|false|none|none|
|»»»» large|string|false|none|none|
|»»» total_collections|integer|false|none|none|
|»»» total_likes|integer|false|none|none|
|»»» total_photos|integer|false|none|none|
|»»» twitter_username|string|false|none|none|
|»»» updated_at|string(date-time)|false|none|none|
|»»» username|string|false|none|none|
|» description|string|false|none|none|
|» downloads|integer|false|none|none|
|» exif|[Exif](#schemaexif)|false|none|none|
|»» make|string|false|none|none|
|»» model|string|false|none|none|
|»» exposure_time|string|false|none|none|
|»» aperture|number(double)|false|none|none|
|»» focal_length|number(double)|false|none|none|
|»» iso|integer|false|none|none|
|» height|integer|false|none|none|
|» id|string|false|none|none|
|» liked_by_user|boolean|false|none|none|
|» likes|integer|false|none|none|
|» links|[PhotoLinks](#schemaphotolinks)|false|none|none|
|»» download|string|false|none|none|
|»» download_location|string|false|none|none|
|»» html|string|false|none|none|
|»» self|string|false|none|none|
|» location|[Location](#schemalocation)|false|none|none|
|»» city|string|false|none|none|
|»» country|string|false|none|none|
|»» name|string|false|none|none|
|»» position|object|false|none|none|
|»»» latitude|number(double)|false|none|none|
|»»» longitude|number(double)|false|none|none|
|» tags|[object]|false|none|none|
|»» title|string|false|none|none|
|» updated_at|string(date-time)|false|none|none|
|» urls|[PhotoUrls](#schemaphotourls)|false|none|none|
|»» raw|string|false|none|none|
|»» full|string|false|none|none|
|»» regular|string|false|none|none|
|»» small|string|false|none|none|
|»» thumb|string|false|none|none|
|» user|[User](#schemauser)|false|none|none|
|» width|integer|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
publicAuth
</aside>

## getPhotoById

<a id="opIdgetPhotoById"></a>

> Code samples

```shell
curl --request GET \
  --url https://api.unsplash.com//photos/string \
  --header 'Accept: application/json' \
  --header 'Authorization: API_KEY'
```

`GET /photos/{id}`

*Get a photo*

Retrieve a single photo.

<h3 id="getphotobyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The photo’s ID.|

> Example responses

> 200 Response

```json
{
  "blur_hash": "string",
  "color": "string",
  "created_at": "2019-08-24T14:15:22Z",
  "current_user_collections": [
    {
      "cover_photo": {
        "blur_hash": "string",
        "color": "string",
        "created_at": "2019-08-24T14:15:22Z",
        "current_user_collections": [],
        "description": "string",
        "downloads": 0,
        "exif": {
          "make": "string",
          "model": "string",
          "exposure_time": "string",
          "aperture": 0,
          "focal_length": 0,
          "iso": 0
        },
        "height": 0,
        "id": "string",
        "liked_by_user": true,
        "likes": 0,
        "links": {
          "download": "string",
          "download_location": "string",
          "html": "string",
          "self": "string"
        },
        "location": {
          "city": "string",
          "country": "string",
          "name": "string",
          "position": {
            "latitude": 0,
            "longitude": 0
          }
        },
        "tags": [
          {
            "title": "string"
          }
        ],
        "updated_at": "2019-08-24T14:15:22Z",
        "urls": {
          "raw": "string",
          "full": "string",
          "regular": "string",
          "small": "string",
          "thumb": "string"
        },
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        },
        "width": 0
      },
      "description": "string",
      "featured": true,
      "id": 0,
      "last_collected_at": "2019-08-24T14:15:22Z",
      "links": {
        "html": "string",
        "photos": "string",
        "related": "string",
        "self": "string"
      },
      "private": true,
      "published_at": "2019-08-24T14:15:22Z",
      "share_key": "string",
      "title": "string",
      "total_photos": true,
      "updated_at": "2019-08-24T14:15:22Z",
      "user": {
        "badge": {
          "link": "string",
          "primary": true,
          "slug": "string",
          "title": "string"
        },
        "bio": "string",
        "downloads": 0,
        "first_name": "string",
        "followed_by_user": true,
        "followers_count": 0,
        "following_count": 0,
        "id": "string",
        "instagram_username": "string",
        "last_name": "string",
        "links": {
          "html": "string",
          "likes": "string",
          "photos": "string",
          "portfolio": "string",
          "self": "string"
        },
        "location": "string",
        "name": "string",
        "portfolio_url": "string",
        "profile_image": {
          "small": "string",
          "medium": "string",
          "large": "string"
        },
        "total_collections": 0,
        "total_likes": 0,
        "total_photos": 0,
        "twitter_username": "string",
        "updated_at": "2019-08-24T14:15:22Z",
        "username": "string"
      }
    }
  ],
  "description": "string",
  "downloads": 0,
  "exif": {
    "make": "string",
    "model": "string",
    "exposure_time": "string",
    "aperture": 0,
    "focal_length": 0,
    "iso": 0
  },
  "height": 0,
  "id": "string",
  "liked_by_user": true,
  "likes": 0,
  "links": {
    "download": "string",
    "download_location": "string",
    "html": "string",
    "self": "string"
  },
  "location": {
    "city": "string",
    "country": "string",
    "name": "string",
    "position": {
      "latitude": 0,
      "longitude": 0
    }
  },
  "tags": [
    {
      "title": "string"
    }
  ],
  "updated_at": "2019-08-24T14:15:22Z",
  "urls": {
    "raw": "string",
    "full": "string",
    "regular": "string",
    "small": "string",
    "thumb": "string"
  },
  "user": {
    "badge": {
      "link": "string",
      "primary": true,
      "slug": "string",
      "title": "string"
    },
    "bio": "string",
    "downloads": 0,
    "first_name": "string",
    "followed_by_user": true,
    "followers_count": 0,
    "following_count": 0,
    "id": "string",
    "instagram_username": "string",
    "last_name": "string",
    "links": {
      "html": "string",
      "likes": "string",
      "photos": "string",
      "portfolio": "string",
      "self": "string"
    },
    "location": "string",
    "name": "string",
    "portfolio_url": "string",
    "profile_image": {
      "small": "string",
      "medium": "string",
      "large": "string"
    },
    "total_collections": 0,
    "total_likes": 0,
    "total_photos": 0,
    "twitter_username": "string",
    "updated_at": "2019-08-24T14:15:22Z",
    "username": "string"
  },
  "width": 0
}
```

<h3 id="getphotobyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Photo](#schemaphoto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
publicAuth
</aside>

## updatePhoto

<a id="opIdupdatePhoto"></a>

> Code samples

```shell
curl --request PUT \
  --url https://api.unsplash.com//photos/string \
  --header 'Accept: application/json' \
  --header 'Authorization: Bearer {access-token}'
```

`PUT /photos/{id}`

*Update a photo*

Update a photo on behalf of the logged-in user. This requires the write_photos scope.

<h3 id="updatephoto-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The photo’s ID.|
|description|query|string|false|The photo’s description (Optional).|
|show_on_profile|query|boolean|false|The photo’s visibility (Optional).|
|tags|query|string|false|The photo’s tags (Optional).|
|location[latitude]|query|number(double)|false|The photo location’s latitude rounded to 6 decimals. (Optional)|
|location[longitude]|query|number(double)|false|The photo location’s longitude rounded to 6 decimals. (Optional)|
|location[name]|query|string|false|The photo’s full location string (including city and country) (Optional)|
|location[city]|query|string|false|The photo location’s city (Optional)|
|location[country]|query|string|false|The photo location’s country (Optional)|
|exif[make]|query|string|false|Camera’s brand (Optional)|
|exif[model]|query|string|false|Camera’s model (Optional)|
|exif[exposure_time]|query|string|false|Camera’s exposure time (Optional)|
|exif[aperture_value]|query|string|false|Camera’s aperture value (Optional)|
|exif[focal_length]|query|string|false|Camera’s focal length (Optional)|
|exif[iso_speed_ratings]|query|string|false|Camera’s iso (Optional)|

> Example responses

> 200 Response

```json
{
  "blur_hash": "string",
  "color": "string",
  "created_at": "2019-08-24T14:15:22Z",
  "current_user_collections": [
    {
      "cover_photo": {
        "blur_hash": "string",
        "color": "string",
        "created_at": "2019-08-24T14:15:22Z",
        "current_user_collections": [],
        "description": "string",
        "downloads": 0,
        "exif": {
          "make": "string",
          "model": "string",
          "exposure_time": "string",
          "aperture": 0,
          "focal_length": 0,
          "iso": 0
        },
        "height": 0,
        "id": "string",
        "liked_by_user": true,
        "likes": 0,
        "links": {
          "download": "string",
          "download_location": "string",
          "html": "string",
          "self": "string"
        },
        "location": {
          "city": "string",
          "country": "string",
          "name": "string",
          "position": {
            "latitude": 0,
            "longitude": 0
          }
        },
        "tags": [
          {
            "title": "string"
          }
        ],
        "updated_at": "2019-08-24T14:15:22Z",
        "urls": {
          "raw": "string",
          "full": "string",
          "regular": "string",
          "small": "string",
          "thumb": "string"
        },
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        },
        "width": 0
      },
      "description": "string",
      "featured": true,
      "id": 0,
      "last_collected_at": "2019-08-24T14:15:22Z",
      "links": {
        "html": "string",
        "photos": "string",
        "related": "string",
        "self": "string"
      },
      "private": true,
      "published_at": "2019-08-24T14:15:22Z",
      "share_key": "string",
      "title": "string",
      "total_photos": true,
      "updated_at": "2019-08-24T14:15:22Z",
      "user": {
        "badge": {
          "link": "string",
          "primary": true,
          "slug": "string",
          "title": "string"
        },
        "bio": "string",
        "downloads": 0,
        "first_name": "string",
        "followed_by_user": true,
        "followers_count": 0,
        "following_count": 0,
        "id": "string",
        "instagram_username": "string",
        "last_name": "string",
        "links": {
          "html": "string",
          "likes": "string",
          "photos": "string",
          "portfolio": "string",
          "self": "string"
        },
        "location": "string",
        "name": "string",
        "portfolio_url": "string",
        "profile_image": {
          "small": "string",
          "medium": "string",
          "large": "string"
        },
        "total_collections": 0,
        "total_likes": 0,
        "total_photos": 0,
        "twitter_username": "string",
        "updated_at": "2019-08-24T14:15:22Z",
        "username": "string"
      }
    }
  ],
  "description": "string",
  "downloads": 0,
  "exif": {
    "make": "string",
    "model": "string",
    "exposure_time": "string",
    "aperture": 0,
    "focal_length": 0,
    "iso": 0
  },
  "height": 0,
  "id": "string",
  "liked_by_user": true,
  "likes": 0,
  "links": {
    "download": "string",
    "download_location": "string",
    "html": "string",
    "self": "string"
  },
  "location": {
    "city": "string",
    "country": "string",
    "name": "string",
    "position": {
      "latitude": 0,
      "longitude": 0
    }
  },
  "tags": [
    {
      "title": "string"
    }
  ],
  "updated_at": "2019-08-24T14:15:22Z",
  "urls": {
    "raw": "string",
    "full": "string",
    "regular": "string",
    "small": "string",
    "thumb": "string"
  },
  "user": {
    "badge": {
      "link": "string",
      "primary": true,
      "slug": "string",
      "title": "string"
    },
    "bio": "string",
    "downloads": 0,
    "first_name": "string",
    "followed_by_user": true,
    "followers_count": 0,
    "following_count": 0,
    "id": "string",
    "instagram_username": "string",
    "last_name": "string",
    "links": {
      "html": "string",
      "likes": "string",
      "photos": "string",
      "portfolio": "string",
      "self": "string"
    },
    "location": "string",
    "name": "string",
    "portfolio_url": "string",
    "profile_image": {
      "small": "string",
      "medium": "string",
      "large": "string"
    },
    "total_collections": 0,
    "total_likes": 0,
    "total_photos": 0,
    "twitter_username": "string",
    "updated_at": "2019-08-24T14:15:22Z",
    "username": "string"
  },
  "width": 0
}
```

<h3 id="updatephoto-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Photo](#schemaphoto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
userAuth ( Scopes: write_photos )
</aside>

## getRandomPhoto

<a id="opIdgetRandomPhoto"></a>

> Code samples

```shell
curl --request GET \
  --url https://api.unsplash.com//photos/random \
  --header 'Accept: application/json' \
  --header 'Authorization: API_KEY'
```

`GET /photos/random`

*Get a random photo*

Retrieve a single random photo, given optional filters.
You can’t use the collections and query parameters in the same request
When supplying a count parameter - and only then - the response will be an array of photos, even if the value of count is 1.

<h3 id="getrandomphoto-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|collections|query|string|false|Public collection ID(‘s) to filter selection. If multiple, comma-separated|
|featured|query|boolean|false|Limit selection to featured photos.|
|username|query|string|false|Limit selection to a single user.|
|query|query|string|false|Limit selection to photos matching a search term.|
|orientation|query|[Orientation](#schemaorientation)|false|Filter by photo orientation. (Valid values: landscape, portrait, squarish)|
|content_filter|query|[ContentFilter](#schemacontentfilter)|false|Limit results by content safety. Default: low. Valid values are low and high.|
|count|query|integer|false|The number of photos to return. (Default: 1; max: 30)|

#### Detailed descriptions

**orientation**: Filter by photo orientation. (Valid values: landscape, portrait, squarish)

**content_filter**: Limit results by content safety. Default: low. Valid values are low and high.

**count**: The number of photos to return. (Default: 1; max: 30)

#### Enumerated Values

|Parameter|Value|
|---|---|
|orientation|landscape|
|orientation|portrait|
|orientation|squarish|
|content_filter|low|
|content_filter|high|

> Example responses

> 200 Response

```json
{
  "blur_hash": "string",
  "color": "string",
  "created_at": "2019-08-24T14:15:22Z",
  "current_user_collections": [
    {
      "cover_photo": {
        "blur_hash": "string",
        "color": "string",
        "created_at": "2019-08-24T14:15:22Z",
        "current_user_collections": [],
        "description": "string",
        "downloads": 0,
        "exif": {
          "make": "string",
          "model": "string",
          "exposure_time": "string",
          "aperture": 0,
          "focal_length": 0,
          "iso": 0
        },
        "height": 0,
        "id": "string",
        "liked_by_user": true,
        "likes": 0,
        "links": {
          "download": "string",
          "download_location": "string",
          "html": "string",
          "self": "string"
        },
        "location": {
          "city": "string",
          "country": "string",
          "name": "string",
          "position": {
            "latitude": 0,
            "longitude": 0
          }
        },
        "tags": [
          {
            "title": "string"
          }
        ],
        "updated_at": "2019-08-24T14:15:22Z",
        "urls": {
          "raw": "string",
          "full": "string",
          "regular": "string",
          "small": "string",
          "thumb": "string"
        },
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        },
        "width": 0
      },
      "description": "string",
      "featured": true,
      "id": 0,
      "last_collected_at": "2019-08-24T14:15:22Z",
      "links": {
        "html": "string",
        "photos": "string",
        "related": "string",
        "self": "string"
      },
      "private": true,
      "published_at": "2019-08-24T14:15:22Z",
      "share_key": "string",
      "title": "string",
      "total_photos": true,
      "updated_at": "2019-08-24T14:15:22Z",
      "user": {
        "badge": {
          "link": "string",
          "primary": true,
          "slug": "string",
          "title": "string"
        },
        "bio": "string",
        "downloads": 0,
        "first_name": "string",
        "followed_by_user": true,
        "followers_count": 0,
        "following_count": 0,
        "id": "string",
        "instagram_username": "string",
        "last_name": "string",
        "links": {
          "html": "string",
          "likes": "string",
          "photos": "string",
          "portfolio": "string",
          "self": "string"
        },
        "location": "string",
        "name": "string",
        "portfolio_url": "string",
        "profile_image": {
          "small": "string",
          "medium": "string",
          "large": "string"
        },
        "total_collections": 0,
        "total_likes": 0,
        "total_photos": 0,
        "twitter_username": "string",
        "updated_at": "2019-08-24T14:15:22Z",
        "username": "string"
      }
    }
  ],
  "description": "string",
  "downloads": 0,
  "exif": {
    "make": "string",
    "model": "string",
    "exposure_time": "string",
    "aperture": 0,
    "focal_length": 0,
    "iso": 0
  },
  "height": 0,
  "id": "string",
  "liked_by_user": true,
  "likes": 0,
  "links": {
    "download": "string",
    "download_location": "string",
    "html": "string",
    "self": "string"
  },
  "location": {
    "city": "string",
    "country": "string",
    "name": "string",
    "position": {
      "latitude": 0,
      "longitude": 0
    }
  },
  "tags": [
    {
      "title": "string"
    }
  ],
  "updated_at": "2019-08-24T14:15:22Z",
  "urls": {
    "raw": "string",
    "full": "string",
    "regular": "string",
    "small": "string",
    "thumb": "string"
  },
  "user": {
    "badge": {
      "link": "string",
      "primary": true,
      "slug": "string",
      "title": "string"
    },
    "bio": "string",
    "downloads": 0,
    "first_name": "string",
    "followed_by_user": true,
    "followers_count": 0,
    "following_count": 0,
    "id": "string",
    "instagram_username": "string",
    "last_name": "string",
    "links": {
      "html": "string",
      "likes": "string",
      "photos": "string",
      "portfolio": "string",
      "self": "string"
    },
    "location": "string",
    "name": "string",
    "portfolio_url": "string",
    "profile_image": {
      "small": "string",
      "medium": "string",
      "large": "string"
    },
    "total_collections": 0,
    "total_likes": 0,
    "total_photos": 0,
    "twitter_username": "string",
    "updated_at": "2019-08-24T14:15:22Z",
    "username": "string"
  },
  "width": 0
}
```

<h3 id="getrandomphoto-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="getrandomphoto-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
publicAuth
</aside>

## getPhotoStatistics

<a id="opIdgetPhotoStatistics"></a>

> Code samples

```shell
curl --request GET \
  --url https://api.unsplash.com//photos/string/statistics \
  --header 'Accept: application/json' \
  --header 'Authorization: API_KEY'
```

`GET /photos/{id}/statistics`

*Get a photo’s statistics*

Retrieve total number of downloads, views and likes of a single photo, as well as the historical breakdown of these stats in a specific timeframe (default is 30 days).

<h3 id="getphotostatistics-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The public id of the photo.|
|resolution|query|[StatResolution](#schemastatresolution)|false|The frequency of the stats. (Optional; default: “days”)|
|quantity|query|integer|false|The amount of for each stat. (Optional; default: 30)|

#### Detailed descriptions

**resolution**: The frequency of the stats. (Optional; default: “days”)

**quantity**: The amount of for each stat. (Optional; default: 30)

#### Enumerated Values

|Parameter|Value|
|---|---|
|resolution|days|

> Example responses

> 200 Response

```json
{
  "downloads": {
    "total": 0,
    "historical": {
      "change": 0,
      "resolution": "days",
      "quantity": 0,
      "values": [
        {
          "date": "2019-08-24",
          "value": 0
        }
      ]
    }
  },
  "id": "string",
  "likes": {
    "total": 0,
    "historical": {
      "change": 0,
      "resolution": "days",
      "quantity": 0,
      "values": [
        {
          "date": "2019-08-24",
          "value": 0
        }
      ]
    }
  },
  "views": {
    "total": 0,
    "historical": {
      "change": 0,
      "resolution": "days",
      "quantity": 0,
      "values": [
        {
          "date": "2019-08-24",
          "value": 0
        }
      ]
    }
  }
}
```

<h3 id="getphotostatistics-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[PhotoStatistics](#schemaphotostatistics)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
publicAuth
</aside>

## trackPhotoDownload

<a id="opIdtrackPhotoDownload"></a>

> Code samples

```shell
curl --request GET \
  --url https://api.unsplash.com//photos/string/download \
  --header 'Accept: application/json' \
  --header 'Authorization: API_KEY'
```

`GET /photos/{id}/download`

*Track a photo download*

To abide by the API guidelines, you need to trigger a GET request to this endpoint every time your application performs a download of a photo. To understand what constitutes a download, please refer to the ‘Triggering a download’ guideline.

<h3 id="trackphotodownload-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The photo’s ID.|

> Example responses

> 200 Response

```json
{
  "blur_hash": "string",
  "color": "string",
  "created_at": "2019-08-24T14:15:22Z",
  "current_user_collections": [
    {
      "cover_photo": {
        "blur_hash": "string",
        "color": "string",
        "created_at": "2019-08-24T14:15:22Z",
        "current_user_collections": [],
        "description": "string",
        "downloads": 0,
        "exif": {
          "make": "string",
          "model": "string",
          "exposure_time": "string",
          "aperture": 0,
          "focal_length": 0,
          "iso": 0
        },
        "height": 0,
        "id": "string",
        "liked_by_user": true,
        "likes": 0,
        "links": {
          "download": "string",
          "download_location": "string",
          "html": "string",
          "self": "string"
        },
        "location": {
          "city": "string",
          "country": "string",
          "name": "string",
          "position": {
            "latitude": 0,
            "longitude": 0
          }
        },
        "tags": [
          {
            "title": "string"
          }
        ],
        "updated_at": "2019-08-24T14:15:22Z",
        "urls": {
          "raw": "string",
          "full": "string",
          "regular": "string",
          "small": "string",
          "thumb": "string"
        },
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        },
        "width": 0
      },
      "description": "string",
      "featured": true,
      "id": 0,
      "last_collected_at": "2019-08-24T14:15:22Z",
      "links": {
        "html": "string",
        "photos": "string",
        "related": "string",
        "self": "string"
      },
      "private": true,
      "published_at": "2019-08-24T14:15:22Z",
      "share_key": "string",
      "title": "string",
      "total_photos": true,
      "updated_at": "2019-08-24T14:15:22Z",
      "user": {
        "badge": {
          "link": "string",
          "primary": true,
          "slug": "string",
          "title": "string"
        },
        "bio": "string",
        "downloads": 0,
        "first_name": "string",
        "followed_by_user": true,
        "followers_count": 0,
        "following_count": 0,
        "id": "string",
        "instagram_username": "string",
        "last_name": "string",
        "links": {
          "html": "string",
          "likes": "string",
          "photos": "string",
          "portfolio": "string",
          "self": "string"
        },
        "location": "string",
        "name": "string",
        "portfolio_url": "string",
        "profile_image": {
          "small": "string",
          "medium": "string",
          "large": "string"
        },
        "total_collections": 0,
        "total_likes": 0,
        "total_photos": 0,
        "twitter_username": "string",
        "updated_at": "2019-08-24T14:15:22Z",
        "username": "string"
      }
    }
  ],
  "description": "string",
  "downloads": 0,
  "exif": {
    "make": "string",
    "model": "string",
    "exposure_time": "string",
    "aperture": 0,
    "focal_length": 0,
    "iso": 0
  },
  "height": 0,
  "id": "string",
  "liked_by_user": true,
  "likes": 0,
  "links": {
    "download": "string",
    "download_location": "string",
    "html": "string",
    "self": "string"
  },
  "location": {
    "city": "string",
    "country": "string",
    "name": "string",
    "position": {
      "latitude": 0,
      "longitude": 0
    }
  },
  "tags": [
    {
      "title": "string"
    }
  ],
  "updated_at": "2019-08-24T14:15:22Z",
  "urls": {
    "raw": "string",
    "full": "string",
    "regular": "string",
    "small": "string",
    "thumb": "string"
  },
  "user": {
    "badge": {
      "link": "string",
      "primary": true,
      "slug": "string",
      "title": "string"
    },
    "bio": "string",
    "downloads": 0,
    "first_name": "string",
    "followed_by_user": true,
    "followers_count": 0,
    "following_count": 0,
    "id": "string",
    "instagram_username": "string",
    "last_name": "string",
    "links": {
      "html": "string",
      "likes": "string",
      "photos": "string",
      "portfolio": "string",
      "self": "string"
    },
    "location": "string",
    "name": "string",
    "portfolio_url": "string",
    "profile_image": {
      "small": "string",
      "medium": "string",
      "large": "string"
    },
    "total_collections": 0,
    "total_likes": 0,
    "total_photos": 0,
    "twitter_username": "string",
    "updated_at": "2019-08-24T14:15:22Z",
    "username": "string"
  },
  "width": 0
}
```

<h3 id="trackphotodownload-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Photo](#schemaphoto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
publicAuth
</aside>

## likePhoto

<a id="opIdlikePhoto"></a>

> Code samples

```shell
curl --request POST \
  --url https://api.unsplash.com//photos/string/like \
  --header 'Accept: application/json' \
  --header 'Authorization: Bearer {access-token}'
```

`POST /photos/{id}/like`

*Like a photo on behalf of the logged-in user.*

This action is idempotent; sending the POST request to a single photo multiple times has no additional effect.

<h3 id="likephoto-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The photo’s ID.|

> Example responses

> 200 Response

```json
{
  "blur_hash": "string",
  "color": "string",
  "created_at": "2019-08-24T14:15:22Z",
  "current_user_collections": [
    {
      "cover_photo": {
        "blur_hash": "string",
        "color": "string",
        "created_at": "2019-08-24T14:15:22Z",
        "current_user_collections": [],
        "description": "string",
        "downloads": 0,
        "exif": {
          "make": "string",
          "model": "string",
          "exposure_time": "string",
          "aperture": 0,
          "focal_length": 0,
          "iso": 0
        },
        "height": 0,
        "id": "string",
        "liked_by_user": true,
        "likes": 0,
        "links": {
          "download": "string",
          "download_location": "string",
          "html": "string",
          "self": "string"
        },
        "location": {
          "city": "string",
          "country": "string",
          "name": "string",
          "position": {
            "latitude": 0,
            "longitude": 0
          }
        },
        "tags": [
          {
            "title": "string"
          }
        ],
        "updated_at": "2019-08-24T14:15:22Z",
        "urls": {
          "raw": "string",
          "full": "string",
          "regular": "string",
          "small": "string",
          "thumb": "string"
        },
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        },
        "width": 0
      },
      "description": "string",
      "featured": true,
      "id": 0,
      "last_collected_at": "2019-08-24T14:15:22Z",
      "links": {
        "html": "string",
        "photos": "string",
        "related": "string",
        "self": "string"
      },
      "private": true,
      "published_at": "2019-08-24T14:15:22Z",
      "share_key": "string",
      "title": "string",
      "total_photos": true,
      "updated_at": "2019-08-24T14:15:22Z",
      "user": {
        "badge": {
          "link": "string",
          "primary": true,
          "slug": "string",
          "title": "string"
        },
        "bio": "string",
        "downloads": 0,
        "first_name": "string",
        "followed_by_user": true,
        "followers_count": 0,
        "following_count": 0,
        "id": "string",
        "instagram_username": "string",
        "last_name": "string",
        "links": {
          "html": "string",
          "likes": "string",
          "photos": "string",
          "portfolio": "string",
          "self": "string"
        },
        "location": "string",
        "name": "string",
        "portfolio_url": "string",
        "profile_image": {
          "small": "string",
          "medium": "string",
          "large": "string"
        },
        "total_collections": 0,
        "total_likes": 0,
        "total_photos": 0,
        "twitter_username": "string",
        "updated_at": "2019-08-24T14:15:22Z",
        "username": "string"
      }
    }
  ],
  "description": "string",
  "downloads": 0,
  "exif": {
    "make": "string",
    "model": "string",
    "exposure_time": "string",
    "aperture": 0,
    "focal_length": 0,
    "iso": 0
  },
  "height": 0,
  "id": "string",
  "liked_by_user": true,
  "likes": 0,
  "links": {
    "download": "string",
    "download_location": "string",
    "html": "string",
    "self": "string"
  },
  "location": {
    "city": "string",
    "country": "string",
    "name": "string",
    "position": {
      "latitude": 0,
      "longitude": 0
    }
  },
  "tags": [
    {
      "title": "string"
    }
  ],
  "updated_at": "2019-08-24T14:15:22Z",
  "urls": {
    "raw": "string",
    "full": "string",
    "regular": "string",
    "small": "string",
    "thumb": "string"
  },
  "user": {
    "badge": {
      "link": "string",
      "primary": true,
      "slug": "string",
      "title": "string"
    },
    "bio": "string",
    "downloads": 0,
    "first_name": "string",
    "followed_by_user": true,
    "followers_count": 0,
    "following_count": 0,
    "id": "string",
    "instagram_username": "string",
    "last_name": "string",
    "links": {
      "html": "string",
      "likes": "string",
      "photos": "string",
      "portfolio": "string",
      "self": "string"
    },
    "location": "string",
    "name": "string",
    "portfolio_url": "string",
    "profile_image": {
      "small": "string",
      "medium": "string",
      "large": "string"
    },
    "total_collections": 0,
    "total_likes": 0,
    "total_photos": 0,
    "twitter_username": "string",
    "updated_at": "2019-08-24T14:15:22Z",
    "username": "string"
  },
  "width": 0
}
```

<h3 id="likephoto-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Photo](#schemaphoto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
userAuth ( Scopes: write_likes )
</aside>

## unlikePhoto

<a id="opIdunlikePhoto"></a>

> Code samples

```shell
curl --request DELETE \
  --url https://api.unsplash.com//photos/string/like \
  --header 'Accept: application/json' \
  --header 'Authorization: Bearer {access-token}'
```

`DELETE /photos/{id}/like`

*Remove a user’s like of a photo.*

This action is idempotent; sending the DELETE request to a single photo multiple times has no additional effect.

<h3 id="unlikephoto-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The photo’s ID.|

> Example responses

> 200 Response

```json
{
  "blur_hash": "string",
  "color": "string",
  "created_at": "2019-08-24T14:15:22Z",
  "current_user_collections": [
    {
      "cover_photo": {
        "blur_hash": "string",
        "color": "string",
        "created_at": "2019-08-24T14:15:22Z",
        "current_user_collections": [],
        "description": "string",
        "downloads": 0,
        "exif": {
          "make": "string",
          "model": "string",
          "exposure_time": "string",
          "aperture": 0,
          "focal_length": 0,
          "iso": 0
        },
        "height": 0,
        "id": "string",
        "liked_by_user": true,
        "likes": 0,
        "links": {
          "download": "string",
          "download_location": "string",
          "html": "string",
          "self": "string"
        },
        "location": {
          "city": "string",
          "country": "string",
          "name": "string",
          "position": {
            "latitude": 0,
            "longitude": 0
          }
        },
        "tags": [
          {
            "title": "string"
          }
        ],
        "updated_at": "2019-08-24T14:15:22Z",
        "urls": {
          "raw": "string",
          "full": "string",
          "regular": "string",
          "small": "string",
          "thumb": "string"
        },
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        },
        "width": 0
      },
      "description": "string",
      "featured": true,
      "id": 0,
      "last_collected_at": "2019-08-24T14:15:22Z",
      "links": {
        "html": "string",
        "photos": "string",
        "related": "string",
        "self": "string"
      },
      "private": true,
      "published_at": "2019-08-24T14:15:22Z",
      "share_key": "string",
      "title": "string",
      "total_photos": true,
      "updated_at": "2019-08-24T14:15:22Z",
      "user": {
        "badge": {
          "link": "string",
          "primary": true,
          "slug": "string",
          "title": "string"
        },
        "bio": "string",
        "downloads": 0,
        "first_name": "string",
        "followed_by_user": true,
        "followers_count": 0,
        "following_count": 0,
        "id": "string",
        "instagram_username": "string",
        "last_name": "string",
        "links": {
          "html": "string",
          "likes": "string",
          "photos": "string",
          "portfolio": "string",
          "self": "string"
        },
        "location": "string",
        "name": "string",
        "portfolio_url": "string",
        "profile_image": {
          "small": "string",
          "medium": "string",
          "large": "string"
        },
        "total_collections": 0,
        "total_likes": 0,
        "total_photos": 0,
        "twitter_username": "string",
        "updated_at": "2019-08-24T14:15:22Z",
        "username": "string"
      }
    }
  ],
  "description": "string",
  "downloads": 0,
  "exif": {
    "make": "string",
    "model": "string",
    "exposure_time": "string",
    "aperture": 0,
    "focal_length": 0,
    "iso": 0
  },
  "height": 0,
  "id": "string",
  "liked_by_user": true,
  "likes": 0,
  "links": {
    "download": "string",
    "download_location": "string",
    "html": "string",
    "self": "string"
  },
  "location": {
    "city": "string",
    "country": "string",
    "name": "string",
    "position": {
      "latitude": 0,
      "longitude": 0
    }
  },
  "tags": [
    {
      "title": "string"
    }
  ],
  "updated_at": "2019-08-24T14:15:22Z",
  "urls": {
    "raw": "string",
    "full": "string",
    "regular": "string",
    "small": "string",
    "thumb": "string"
  },
  "user": {
    "badge": {
      "link": "string",
      "primary": true,
      "slug": "string",
      "title": "string"
    },
    "bio": "string",
    "downloads": 0,
    "first_name": "string",
    "followed_by_user": true,
    "followers_count": 0,
    "following_count": 0,
    "id": "string",
    "instagram_username": "string",
    "last_name": "string",
    "links": {
      "html": "string",
      "likes": "string",
      "photos": "string",
      "portfolio": "string",
      "self": "string"
    },
    "location": "string",
    "name": "string",
    "portfolio_url": "string",
    "profile_image": {
      "small": "string",
      "medium": "string",
      "large": "string"
    },
    "total_collections": 0,
    "total_likes": 0,
    "total_photos": 0,
    "twitter_username": "string",
    "updated_at": "2019-08-24T14:15:22Z",
    "username": "string"
  },
  "width": 0
}
```

<h3 id="unlikephoto-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Photo](#schemaphoto)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
userAuth ( Scopes: write_likes )
</aside>

<h1 id="unsplash-api-search">Search</h1>

<a href="https://unsplash.com/documentation#search">Find out more</a>

## searchPhotos

<a id="opIdsearchPhotos"></a>

> Code samples

```shell
curl --request GET \
  --url 'https://api.unsplash.com//search/photos?query=string' \
  --header 'Accept: application/json' \
  --header 'Authorization: API_KEY'
```

`GET /search/photos`

*Search photos*

Get a single page of photo results for a query.

<h3 id="searchphotos-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|query|query|string|true|Search terms.|
|page|query|integer|false|Page number to retrieve. (Optional; default: 1)|
|per_page|query|integer|false|Number of items per page. (Optional; default: 10)|
|order_by|query|[OrderBy](#schemaorderby)|false|How to sort the photos. (Optional; default: relevant). Valid values are latest and relevant.|
|collections|query|string|false|Collection ID(‘s) to narrow search. Optional. If multiple, comma-separated.|
|content_filter|query|[ContentFilter](#schemacontentfilter)|false|Limit results by content safety. (Optional; default: low). Valid values are low and high.|
|color|query|[Color](#schemacolor)|false|Filter results by color. Optional. Valid values are: black_and_white, black, white, yellow, orange, red, purple, magenta, green, teal, and blue.|
|orientation|query|[Orientation](#schemaorientation)|false|Filter by photo orientation. Optional. (Valid values: landscape, portrait, squarish)|

#### Detailed descriptions

**page**: Page number to retrieve. (Optional; default: 1)

**per_page**: Number of items per page. (Optional; default: 10)

**order_by**: How to sort the photos. (Optional; default: relevant). Valid values are latest and relevant.

**collections**: Collection ID(‘s) to narrow search. Optional. If multiple, comma-separated.

**content_filter**: Limit results by content safety. (Optional; default: low). Valid values are low and high.

**color**: Filter results by color. Optional. Valid values are: black_and_white, black, white, yellow, orange, red, purple, magenta, green, teal, and blue.

**orientation**: Filter by photo orientation. Optional. (Valid values: landscape, portrait, squarish)

#### Enumerated Values

|Parameter|Value|
|---|---|
|order_by|latest|
|order_by|oldest|
|order_by|popular|
|content_filter|low|
|content_filter|high|
|color|black_and_white|
|color|black|
|color|white|
|color|yellow|
|color|orange|
|color|red|
|color|purple|
|color|magenta|
|color|green|
|color|teal|
|color|blue|
|orientation|landscape|
|orientation|portrait|
|orientation|squarish|

> Example responses

> 200 Response

```json
{
  "total": 0,
  "total_pages": 0,
  "results": [
    {
      "blur_hash": "string",
      "color": "string",
      "created_at": "2019-08-24T14:15:22Z",
      "current_user_collections": [
        {
          "cover_photo": {},
          "description": "string",
          "featured": true,
          "id": 0,
          "last_collected_at": "2019-08-24T14:15:22Z",
          "links": {
            "html": "string",
            "photos": "string",
            "related": "string",
            "self": "string"
          },
          "private": true,
          "published_at": "2019-08-24T14:15:22Z",
          "share_key": "string",
          "title": "string",
          "total_photos": true,
          "updated_at": "2019-08-24T14:15:22Z",
          "user": {
            "badge": {
              "link": "string",
              "primary": true,
              "slug": "string",
              "title": "string"
            },
            "bio": "string",
            "downloads": 0,
            "first_name": "string",
            "followed_by_user": true,
            "followers_count": 0,
            "following_count": 0,
            "id": "string",
            "instagram_username": "string",
            "last_name": "string",
            "links": {
              "html": "string",
              "likes": "string",
              "photos": "string",
              "portfolio": "string",
              "self": "string"
            },
            "location": "string",
            "name": "string",
            "portfolio_url": "string",
            "profile_image": {
              "small": "string",
              "medium": "string",
              "large": "string"
            },
            "total_collections": 0,
            "total_likes": 0,
            "total_photos": 0,
            "twitter_username": "string",
            "updated_at": "2019-08-24T14:15:22Z",
            "username": "string"
          }
        }
      ],
      "description": "string",
      "downloads": 0,
      "exif": {
        "make": "string",
        "model": "string",
        "exposure_time": "string",
        "aperture": 0,
        "focal_length": 0,
        "iso": 0
      },
      "height": 0,
      "id": "string",
      "liked_by_user": true,
      "likes": 0,
      "links": {
        "download": "string",
        "download_location": "string",
        "html": "string",
        "self": "string"
      },
      "location": {
        "city": "string",
        "country": "string",
        "name": "string",
        "position": {
          "latitude": 0,
          "longitude": 0
        }
      },
      "tags": [
        {
          "title": "string"
        }
      ],
      "updated_at": "2019-08-24T14:15:22Z",
      "urls": {
        "raw": "string",
        "full": "string",
        "regular": "string",
        "small": "string",
        "thumb": "string"
      },
      "user": {
        "badge": {
          "link": "string",
          "primary": true,
          "slug": "string",
          "title": "string"
        },
        "bio": "string",
        "downloads": 0,
        "first_name": "string",
        "followed_by_user": true,
        "followers_count": 0,
        "following_count": 0,
        "id": "string",
        "instagram_username": "string",
        "last_name": "string",
        "links": {
          "html": "string",
          "likes": "string",
          "photos": "string",
          "portfolio": "string",
          "self": "string"
        },
        "location": "string",
        "name": "string",
        "portfolio_url": "string",
        "profile_image": {
          "small": "string",
          "medium": "string",
          "large": "string"
        },
        "total_collections": 0,
        "total_likes": 0,
        "total_photos": 0,
        "twitter_username": "string",
        "updated_at": "2019-08-24T14:15:22Z",
        "username": "string"
      },
      "width": 0
    }
  ]
}
```

<h3 id="searchphotos-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[PhotoSearchResults](#schemaphotosearchresults)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
publicAuth
</aside>

## searchCollections

<a id="opIdsearchCollections"></a>

> Code samples

```shell
curl --request GET \
  --url 'https://api.unsplash.com//search/collections?query=string' \
  --header 'Accept: application/json' \
  --header 'Authorization: API_KEY'
```

`GET /search/collections`

*Search collections*

Get a single page of collection results for a query.

<h3 id="searchcollections-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|query|query|string|true|Search terms.|
|page|query|integer|false|Page number to retrieve. (Optional, default: 1)|
|per_page|query|integer|false|Number of items per page. (Optional; default: 10)|

#### Detailed descriptions

**page**: Page number to retrieve. (Optional, default: 1)

**per_page**: Number of items per page. (Optional; default: 10)

> Example responses

> 200 Response

```json
{
  "total": 0,
  "total_pages": 0,
  "results": [
    {
      "cover_photo": {
        "blur_hash": "string",
        "color": "string",
        "created_at": "2019-08-24T14:15:22Z",
        "current_user_collections": [
          {}
        ],
        "description": "string",
        "downloads": 0,
        "exif": {
          "make": "string",
          "model": "string",
          "exposure_time": "string",
          "aperture": 0,
          "focal_length": 0,
          "iso": 0
        },
        "height": 0,
        "id": "string",
        "liked_by_user": true,
        "likes": 0,
        "links": {
          "download": "string",
          "download_location": "string",
          "html": "string",
          "self": "string"
        },
        "location": {
          "city": "string",
          "country": "string",
          "name": "string",
          "position": {
            "latitude": 0,
            "longitude": 0
          }
        },
        "tags": [
          {
            "title": "string"
          }
        ],
        "updated_at": "2019-08-24T14:15:22Z",
        "urls": {
          "raw": "string",
          "full": "string",
          "regular": "string",
          "small": "string",
          "thumb": "string"
        },
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        },
        "width": 0
      },
      "description": "string",
      "featured": true,
      "id": 0,
      "last_collected_at": "2019-08-24T14:15:22Z",
      "links": {
        "html": "string",
        "photos": "string",
        "related": "string",
        "self": "string"
      },
      "private": true,
      "published_at": "2019-08-24T14:15:22Z",
      "share_key": "string",
      "title": "string",
      "total_photos": true,
      "updated_at": "2019-08-24T14:15:22Z",
      "user": {
        "badge": {
          "link": "string",
          "primary": true,
          "slug": "string",
          "title": "string"
        },
        "bio": "string",
        "downloads": 0,
        "first_name": "string",
        "followed_by_user": true,
        "followers_count": 0,
        "following_count": 0,
        "id": "string",
        "instagram_username": "string",
        "last_name": "string",
        "links": {
          "html": "string",
          "likes": "string",
          "photos": "string",
          "portfolio": "string",
          "self": "string"
        },
        "location": "string",
        "name": "string",
        "portfolio_url": "string",
        "profile_image": {
          "small": "string",
          "medium": "string",
          "large": "string"
        },
        "total_collections": 0,
        "total_likes": 0,
        "total_photos": 0,
        "twitter_username": "string",
        "updated_at": "2019-08-24T14:15:22Z",
        "username": "string"
      }
    }
  ]
}
```

<h3 id="searchcollections-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[CollectionSearchResults](#schemacollectionsearchresults)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
publicAuth
</aside>

## searchUsers

<a id="opIdsearchUsers"></a>

> Code samples

```shell
curl --request GET \
  --url 'https://api.unsplash.com//search/users?query=string' \
  --header 'Accept: application/json' \
  --header 'Authorization: API_KEY'
```

`GET /search/users`

*Search users*

Get a single page of user results for a query.

<h3 id="searchusers-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|query|query|string|true|Search terms.|
|page|query|integer|false|Page number to retrieve. (Optional, default: 1)|
|per_page|query|integer|false|Number of items per page. (Optional; default: 10)|

#### Detailed descriptions

**page**: Page number to retrieve. (Optional, default: 1)

**per_page**: Number of items per page. (Optional; default: 10)

> Example responses

> 200 Response

```json
{
  "total": 0,
  "total_pages": 0,
  "results": [
    {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    }
  ]
}
```

<h3 id="searchusers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[UserSearchResults](#schemausersearchresults)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
publicAuth
</aside>

<h1 id="unsplash-api-collections">Collections</h1>

<a href="https://unsplash.com/documentation#collections">Find out more</a>

## getCollections

<a id="opIdgetCollections"></a>

> Code samples

```shell
curl --request GET \
  --url https://api.unsplash.com//collections \
  --header 'Accept: application/json' \
  --header 'Authorization: API_KEY'
```

`GET /collections`

*List collections*

Get a single page from the list of all collections.

<h3 id="getcollections-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|page|query|integer|false|Page number to retrieve. (Optional, default: 1)|
|per_page|query|integer|false|Number of items per page. (Optional; default: 10)|

#### Detailed descriptions

**page**: Page number to retrieve. (Optional, default: 1)

**per_page**: Number of items per page. (Optional; default: 10)

> Example responses

> 200 Response

```json
[
  {
    "cover_photo": {
      "blur_hash": "string",
      "color": "string",
      "created_at": "2019-08-24T14:15:22Z",
      "current_user_collections": [
        {}
      ],
      "description": "string",
      "downloads": 0,
      "exif": {
        "make": "string",
        "model": "string",
        "exposure_time": "string",
        "aperture": 0,
        "focal_length": 0,
        "iso": 0
      },
      "height": 0,
      "id": "string",
      "liked_by_user": true,
      "likes": 0,
      "links": {
        "download": "string",
        "download_location": "string",
        "html": "string",
        "self": "string"
      },
      "location": {
        "city": "string",
        "country": "string",
        "name": "string",
        "position": {
          "latitude": 0,
          "longitude": 0
        }
      },
      "tags": [
        {
          "title": "string"
        }
      ],
      "updated_at": "2019-08-24T14:15:22Z",
      "urls": {
        "raw": "string",
        "full": "string",
        "regular": "string",
        "small": "string",
        "thumb": "string"
      },
      "user": {
        "badge": {
          "link": "string",
          "primary": true,
          "slug": "string",
          "title": "string"
        },
        "bio": "string",
        "downloads": 0,
        "first_name": "string",
        "followed_by_user": true,
        "followers_count": 0,
        "following_count": 0,
        "id": "string",
        "instagram_username": "string",
        "last_name": "string",
        "links": {
          "html": "string",
          "likes": "string",
          "photos": "string",
          "portfolio": "string",
          "self": "string"
        },
        "location": "string",
        "name": "string",
        "portfolio_url": "string",
        "profile_image": {
          "small": "string",
          "medium": "string",
          "large": "string"
        },
        "total_collections": 0,
        "total_likes": 0,
        "total_photos": 0,
        "twitter_username": "string",
        "updated_at": "2019-08-24T14:15:22Z",
        "username": "string"
      },
      "width": 0
    },
    "description": "string",
    "featured": true,
    "id": 0,
    "last_collected_at": "2019-08-24T14:15:22Z",
    "links": {
      "html": "string",
      "photos": "string",
      "related": "string",
      "self": "string"
    },
    "private": true,
    "published_at": "2019-08-24T14:15:22Z",
    "share_key": "string",
    "title": "string",
    "total_photos": true,
    "updated_at": "2019-08-24T14:15:22Z",
    "user": {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    }
  }
]
```

<h3 id="getcollections-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="getcollections-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Collection](#schemacollection)]|false|none|none|
|» cover_photo|[Photo](#schemaphoto)|false|none|none|
|»» blur_hash|string|false|none|none|
|»» color|string|false|none|none|
|»» created_at|string(date-time)|false|none|none|
|»» current_user_collections|[[Collection](#schemacollection)]|false|none|none|
|»» description|string|false|none|none|
|»» downloads|integer|false|none|none|
|»» exif|[Exif](#schemaexif)|false|none|none|
|»»» make|string|false|none|none|
|»»» model|string|false|none|none|
|»»» exposure_time|string|false|none|none|
|»»» aperture|number(double)|false|none|none|
|»»» focal_length|number(double)|false|none|none|
|»»» iso|integer|false|none|none|
|»» height|integer|false|none|none|
|»» id|string|false|none|none|
|»» liked_by_user|boolean|false|none|none|
|»» likes|integer|false|none|none|
|»» links|[PhotoLinks](#schemaphotolinks)|false|none|none|
|»»» download|string|false|none|none|
|»»» download_location|string|false|none|none|
|»»» html|string|false|none|none|
|»»» self|string|false|none|none|
|»» location|[Location](#schemalocation)|false|none|none|
|»»» city|string|false|none|none|
|»»» country|string|false|none|none|
|»»» name|string|false|none|none|
|»»» position|object|false|none|none|
|»»»» latitude|number(double)|false|none|none|
|»»»» longitude|number(double)|false|none|none|
|»» tags|[object]|false|none|none|
|»»» title|string|false|none|none|
|»» updated_at|string(date-time)|false|none|none|
|»» urls|[PhotoUrls](#schemaphotourls)|false|none|none|
|»»» raw|string|false|none|none|
|»»» full|string|false|none|none|
|»»» regular|string|false|none|none|
|»»» small|string|false|none|none|
|»»» thumb|string|false|none|none|
|»» user|[User](#schemauser)|false|none|none|
|»»» badge|object|false|none|none|
|»»»» link|string|false|none|none|
|»»»» primary|boolean|false|none|none|
|»»»» slug|string|false|none|none|
|»»»» title|string|false|none|none|
|»»» bio|string|false|none|none|
|»»» downloads|integer|false|none|none|
|»»» first_name|string|false|none|none|
|»»» followed_by_user|boolean|false|none|none|
|»»» followers_count|integer|false|none|none|
|»»» following_count|integer|false|none|none|
|»»» id|string|false|none|none|
|»»» instagram_username|string|false|none|none|
|»»» last_name|string|false|none|none|
|»»» links|[UserLinks](#schemauserlinks)|false|none|none|
|»»»» html|string|false|none|none|
|»»»» likes|string|false|none|none|
|»»»» photos|string|false|none|none|
|»»»» portfolio|string|false|none|none|
|»»»» self|string|false|none|none|
|»»» location|string|false|none|none|
|»»» name|string|false|none|none|
|»»» portfolio_url|string|false|none|none|
|»»» profile_image|[ProfileImage](#schemaprofileimage)|false|none|none|
|»»»» small|string|false|none|none|
|»»»» medium|string|false|none|none|
|»»»» large|string|false|none|none|
|»»» total_collections|integer|false|none|none|
|»»» total_likes|integer|false|none|none|
|»»» total_photos|integer|false|none|none|
|»»» twitter_username|string|false|none|none|
|»»» updated_at|string(date-time)|false|none|none|
|»»» username|string|false|none|none|
|»» width|integer|false|none|none|
|» description|string|false|none|none|
|» featured|boolean|false|none|none|
|» id|integer|false|none|none|
|» last_collected_at|string(date-time)|false|none|none|
|» links|[CollectionLinks](#schemacollectionlinks)|false|none|none|
|»» html|string|false|none|none|
|»» photos|string|false|none|none|
|»» related|string|false|none|none|
|»» self|string|false|none|none|
|» private|boolean|false|none|none|
|» published_at|string(date-time)|false|none|none|
|» share_key|string|false|none|none|
|» title|string|false|none|none|
|» total_photos|boolean|false|none|none|
|» updated_at|string(date-time)|false|none|none|
|» user|[User](#schemauser)|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
publicAuth
</aside>

## createNewCollection

<a id="opIdcreateNewCollection"></a>

> Code samples

```shell
curl --request POST \
  --url 'https://api.unsplash.com//collections?title=string' \
  --header 'Accept: application/json' \
  --header 'Authorization: Bearer {access-token}'
```

`POST /collections`

*Create a new collection*

Create a new collection. This requires the write_collections scope.

<h3 id="createnewcollection-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|title|query|string|true|The title of the collection.|
|description|query|string|false|The collection’s description. (Optional.)|
|private|query|boolean|false|Whether to make this collection private. (Optional; default false).|

> Example responses

> 201 Response

```json
{
  "cover_photo": {
    "blur_hash": "string",
    "color": "string",
    "created_at": "2019-08-24T14:15:22Z",
    "current_user_collections": [
      {
        "cover_photo": {},
        "description": "string",
        "featured": true,
        "id": 0,
        "last_collected_at": "2019-08-24T14:15:22Z",
        "links": {
          "html": "string",
          "photos": "string",
          "related": "string",
          "self": "string"
        },
        "private": true,
        "published_at": "2019-08-24T14:15:22Z",
        "share_key": "string",
        "title": "string",
        "total_photos": true,
        "updated_at": "2019-08-24T14:15:22Z",
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        }
      }
    ],
    "description": "string",
    "downloads": 0,
    "exif": {
      "make": "string",
      "model": "string",
      "exposure_time": "string",
      "aperture": 0,
      "focal_length": 0,
      "iso": 0
    },
    "height": 0,
    "id": "string",
    "liked_by_user": true,
    "likes": 0,
    "links": {
      "download": "string",
      "download_location": "string",
      "html": "string",
      "self": "string"
    },
    "location": {
      "city": "string",
      "country": "string",
      "name": "string",
      "position": {
        "latitude": 0,
        "longitude": 0
      }
    },
    "tags": [
      {
        "title": "string"
      }
    ],
    "updated_at": "2019-08-24T14:15:22Z",
    "urls": {
      "raw": "string",
      "full": "string",
      "regular": "string",
      "small": "string",
      "thumb": "string"
    },
    "user": {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    },
    "width": 0
  },
  "description": "string",
  "featured": true,
  "id": 0,
  "last_collected_at": "2019-08-24T14:15:22Z",
  "links": {
    "html": "string",
    "photos": "string",
    "related": "string",
    "self": "string"
  },
  "private": true,
  "published_at": "2019-08-24T14:15:22Z",
  "share_key": "string",
  "title": "string",
  "total_photos": true,
  "updated_at": "2019-08-24T14:15:22Z",
  "user": {
    "badge": {
      "link": "string",
      "primary": true,
      "slug": "string",
      "title": "string"
    },
    "bio": "string",
    "downloads": 0,
    "first_name": "string",
    "followed_by_user": true,
    "followers_count": 0,
    "following_count": 0,
    "id": "string",
    "instagram_username": "string",
    "last_name": "string",
    "links": {
      "html": "string",
      "likes": "string",
      "photos": "string",
      "portfolio": "string",
      "self": "string"
    },
    "location": "string",
    "name": "string",
    "portfolio_url": "string",
    "profile_image": {
      "small": "string",
      "medium": "string",
      "large": "string"
    },
    "total_collections": 0,
    "total_likes": 0,
    "total_photos": 0,
    "twitter_username": "string",
    "updated_at": "2019-08-24T14:15:22Z",
    "username": "string"
  }
}
```

<h3 id="createnewcollection-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[Collection](#schemacollection)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
userAuth ( Scopes: write_collections )
</aside>

## getCollectionById

<a id="opIdgetCollectionById"></a>

> Code samples

```shell
curl --request GET \
  --url https://api.unsplash.com//collections/string \
  --header 'Accept: application/json' \
  --header 'Authorization: API_KEY'
```

`GET /collections/{id}`

*Get a collection*

Retrieve a single collection. To view a user’s private collections, the read_collections scope is required.

<h3 id="getcollectionbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The collections’s ID.|

> Example responses

> 200 Response

```json
{
  "cover_photo": {
    "blur_hash": "string",
    "color": "string",
    "created_at": "2019-08-24T14:15:22Z",
    "current_user_collections": [
      {
        "cover_photo": {},
        "description": "string",
        "featured": true,
        "id": 0,
        "last_collected_at": "2019-08-24T14:15:22Z",
        "links": {
          "html": "string",
          "photos": "string",
          "related": "string",
          "self": "string"
        },
        "private": true,
        "published_at": "2019-08-24T14:15:22Z",
        "share_key": "string",
        "title": "string",
        "total_photos": true,
        "updated_at": "2019-08-24T14:15:22Z",
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        }
      }
    ],
    "description": "string",
    "downloads": 0,
    "exif": {
      "make": "string",
      "model": "string",
      "exposure_time": "string",
      "aperture": 0,
      "focal_length": 0,
      "iso": 0
    },
    "height": 0,
    "id": "string",
    "liked_by_user": true,
    "likes": 0,
    "links": {
      "download": "string",
      "download_location": "string",
      "html": "string",
      "self": "string"
    },
    "location": {
      "city": "string",
      "country": "string",
      "name": "string",
      "position": {
        "latitude": 0,
        "longitude": 0
      }
    },
    "tags": [
      {
        "title": "string"
      }
    ],
    "updated_at": "2019-08-24T14:15:22Z",
    "urls": {
      "raw": "string",
      "full": "string",
      "regular": "string",
      "small": "string",
      "thumb": "string"
    },
    "user": {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    },
    "width": 0
  },
  "description": "string",
  "featured": true,
  "id": 0,
  "last_collected_at": "2019-08-24T14:15:22Z",
  "links": {
    "html": "string",
    "photos": "string",
    "related": "string",
    "self": "string"
  },
  "private": true,
  "published_at": "2019-08-24T14:15:22Z",
  "share_key": "string",
  "title": "string",
  "total_photos": true,
  "updated_at": "2019-08-24T14:15:22Z",
  "user": {
    "badge": {
      "link": "string",
      "primary": true,
      "slug": "string",
      "title": "string"
    },
    "bio": "string",
    "downloads": 0,
    "first_name": "string",
    "followed_by_user": true,
    "followers_count": 0,
    "following_count": 0,
    "id": "string",
    "instagram_username": "string",
    "last_name": "string",
    "links": {
      "html": "string",
      "likes": "string",
      "photos": "string",
      "portfolio": "string",
      "self": "string"
    },
    "location": "string",
    "name": "string",
    "portfolio_url": "string",
    "profile_image": {
      "small": "string",
      "medium": "string",
      "large": "string"
    },
    "total_collections": 0,
    "total_likes": 0,
    "total_photos": 0,
    "twitter_username": "string",
    "updated_at": "2019-08-24T14:15:22Z",
    "username": "string"
  }
}
```

<h3 id="getcollectionbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Collection](#schemacollection)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
publicAuth, userAuth ( Scopes: read_collections )
</aside>

## updateCollection

<a id="opIdupdateCollection"></a>

> Code samples

```shell
curl --request PUT \
  --url https://api.unsplash.com//collections/string \
  --header 'Accept: application/json' \
  --header 'Authorization: Bearer {access-token}'
```

`PUT /collections/{id}`

*Update an existing collection*

Update an existing collection belonging to the logged-in user. This requires the write_collections scope.

<h3 id="updatecollection-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The collection’s ID.|
|title|query|string|false|The title of the collection. (Optional.)|
|description|query|string|false|The collection’s description. (Optional.)|
|private|query|boolean|false|Whether to make this collection private. (Optional.)|

> Example responses

> 200 Response

```json
{
  "cover_photo": {
    "blur_hash": "string",
    "color": "string",
    "created_at": "2019-08-24T14:15:22Z",
    "current_user_collections": [
      {
        "cover_photo": {},
        "description": "string",
        "featured": true,
        "id": 0,
        "last_collected_at": "2019-08-24T14:15:22Z",
        "links": {
          "html": "string",
          "photos": "string",
          "related": "string",
          "self": "string"
        },
        "private": true,
        "published_at": "2019-08-24T14:15:22Z",
        "share_key": "string",
        "title": "string",
        "total_photos": true,
        "updated_at": "2019-08-24T14:15:22Z",
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        }
      }
    ],
    "description": "string",
    "downloads": 0,
    "exif": {
      "make": "string",
      "model": "string",
      "exposure_time": "string",
      "aperture": 0,
      "focal_length": 0,
      "iso": 0
    },
    "height": 0,
    "id": "string",
    "liked_by_user": true,
    "likes": 0,
    "links": {
      "download": "string",
      "download_location": "string",
      "html": "string",
      "self": "string"
    },
    "location": {
      "city": "string",
      "country": "string",
      "name": "string",
      "position": {
        "latitude": 0,
        "longitude": 0
      }
    },
    "tags": [
      {
        "title": "string"
      }
    ],
    "updated_at": "2019-08-24T14:15:22Z",
    "urls": {
      "raw": "string",
      "full": "string",
      "regular": "string",
      "small": "string",
      "thumb": "string"
    },
    "user": {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    },
    "width": 0
  },
  "description": "string",
  "featured": true,
  "id": 0,
  "last_collected_at": "2019-08-24T14:15:22Z",
  "links": {
    "html": "string",
    "photos": "string",
    "related": "string",
    "self": "string"
  },
  "private": true,
  "published_at": "2019-08-24T14:15:22Z",
  "share_key": "string",
  "title": "string",
  "total_photos": true,
  "updated_at": "2019-08-24T14:15:22Z",
  "user": {
    "badge": {
      "link": "string",
      "primary": true,
      "slug": "string",
      "title": "string"
    },
    "bio": "string",
    "downloads": 0,
    "first_name": "string",
    "followed_by_user": true,
    "followers_count": 0,
    "following_count": 0,
    "id": "string",
    "instagram_username": "string",
    "last_name": "string",
    "links": {
      "html": "string",
      "likes": "string",
      "photos": "string",
      "portfolio": "string",
      "self": "string"
    },
    "location": "string",
    "name": "string",
    "portfolio_url": "string",
    "profile_image": {
      "small": "string",
      "medium": "string",
      "large": "string"
    },
    "total_collections": 0,
    "total_likes": 0,
    "total_photos": 0,
    "twitter_username": "string",
    "updated_at": "2019-08-24T14:15:22Z",
    "username": "string"
  }
}
```

<h3 id="updatecollection-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Collection](#schemacollection)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
userAuth ( Scopes: write_collections )
</aside>

## deleteCollectionById

<a id="opIddeleteCollectionById"></a>

> Code samples

```shell
curl --request DELETE \
  --url https://api.unsplash.com//collections/string \
  --header 'Authorization: Bearer {access-token}'
```

`DELETE /collections/{id}`

*Delete a collection*

Delete a collection belonging to the logged-in user. This requires the write_collections scope.

<h3 id="deletecollectionbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The collection’s ID.|

<h3 id="deletecollectionbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|204|[No Content](https://tools.ietf.org/html/rfc7231#section-6.3.5)|No Content|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
userAuth ( Scopes: write_collections )
</aside>

## getCollectionPhotos

<a id="opIdgetCollectionPhotos"></a>

> Code samples

```shell
curl --request GET \
  --url https://api.unsplash.com//collections/string/photos \
  --header 'Accept: application/json' \
  --header 'Authorization: API_KEY'
```

`GET /collections/{id}/photos`

*Get a collection’s photos*

Retrieve a collection’s photos.

<h3 id="getcollectionphotos-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The collection’s ID.|
|page|query|integer|false|Page number to retrieve. (Optional, default: 1)|
|per_page|query|integer|false|Number of items per page. (Optional; default: 10)|
|orientation|query|[Orientation](#schemaorientation)|false|Filter by photo orientation. Optional. (Valid values: landscape, portrait, squarish)|

#### Detailed descriptions

**page**: Page number to retrieve. (Optional, default: 1)

**per_page**: Number of items per page. (Optional; default: 10)

**orientation**: Filter by photo orientation. Optional. (Valid values: landscape, portrait, squarish)

#### Enumerated Values

|Parameter|Value|
|---|---|
|orientation|landscape|
|orientation|portrait|
|orientation|squarish|

> Example responses

> 200 Response

```json
[
  {
    "blur_hash": "string",
    "color": "string",
    "created_at": "2019-08-24T14:15:22Z",
    "current_user_collections": [
      {
        "cover_photo": {},
        "description": "string",
        "featured": true,
        "id": 0,
        "last_collected_at": "2019-08-24T14:15:22Z",
        "links": {
          "html": "string",
          "photos": "string",
          "related": "string",
          "self": "string"
        },
        "private": true,
        "published_at": "2019-08-24T14:15:22Z",
        "share_key": "string",
        "title": "string",
        "total_photos": true,
        "updated_at": "2019-08-24T14:15:22Z",
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        }
      }
    ],
    "description": "string",
    "downloads": 0,
    "exif": {
      "make": "string",
      "model": "string",
      "exposure_time": "string",
      "aperture": 0,
      "focal_length": 0,
      "iso": 0
    },
    "height": 0,
    "id": "string",
    "liked_by_user": true,
    "likes": 0,
    "links": {
      "download": "string",
      "download_location": "string",
      "html": "string",
      "self": "string"
    },
    "location": {
      "city": "string",
      "country": "string",
      "name": "string",
      "position": {
        "latitude": 0,
        "longitude": 0
      }
    },
    "tags": [
      {
        "title": "string"
      }
    ],
    "updated_at": "2019-08-24T14:15:22Z",
    "urls": {
      "raw": "string",
      "full": "string",
      "regular": "string",
      "small": "string",
      "thumb": "string"
    },
    "user": {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    },
    "width": 0
  }
]
```

<h3 id="getcollectionphotos-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="getcollectionphotos-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Photo](#schemaphoto)]|false|none|none|
|» blur_hash|string|false|none|none|
|» color|string|false|none|none|
|» created_at|string(date-time)|false|none|none|
|» current_user_collections|[[Collection](#schemacollection)]|false|none|none|
|»» cover_photo|[Photo](#schemaphoto)|false|none|none|
|»» description|string|false|none|none|
|»» featured|boolean|false|none|none|
|»» id|integer|false|none|none|
|»» last_collected_at|string(date-time)|false|none|none|
|»» links|[CollectionLinks](#schemacollectionlinks)|false|none|none|
|»»» html|string|false|none|none|
|»»» photos|string|false|none|none|
|»»» related|string|false|none|none|
|»»» self|string|false|none|none|
|»» private|boolean|false|none|none|
|»» published_at|string(date-time)|false|none|none|
|»» share_key|string|false|none|none|
|»» title|string|false|none|none|
|»» total_photos|boolean|false|none|none|
|»» updated_at|string(date-time)|false|none|none|
|»» user|[User](#schemauser)|false|none|none|
|»»» badge|object|false|none|none|
|»»»» link|string|false|none|none|
|»»»» primary|boolean|false|none|none|
|»»»» slug|string|false|none|none|
|»»»» title|string|false|none|none|
|»»» bio|string|false|none|none|
|»»» downloads|integer|false|none|none|
|»»» first_name|string|false|none|none|
|»»» followed_by_user|boolean|false|none|none|
|»»» followers_count|integer|false|none|none|
|»»» following_count|integer|false|none|none|
|»»» id|string|false|none|none|
|»»» instagram_username|string|false|none|none|
|»»» last_name|string|false|none|none|
|»»» links|[UserLinks](#schemauserlinks)|false|none|none|
|»»»» html|string|false|none|none|
|»»»» likes|string|false|none|none|
|»»»» photos|string|false|none|none|
|»»»» portfolio|string|false|none|none|
|»»»» self|string|false|none|none|
|»»» location|string|false|none|none|
|»»» name|string|false|none|none|
|»»» portfolio_url|string|false|none|none|
|»»» profile_image|[ProfileImage](#schemaprofileimage)|false|none|none|
|»»»» small|string|false|none|none|
|»»»» medium|string|false|none|none|
|»»»» large|string|false|none|none|
|»»» total_collections|integer|false|none|none|
|»»» total_likes|integer|false|none|none|
|»»» total_photos|integer|false|none|none|
|»»» twitter_username|string|false|none|none|
|»»» updated_at|string(date-time)|false|none|none|
|»»» username|string|false|none|none|
|» description|string|false|none|none|
|» downloads|integer|false|none|none|
|» exif|[Exif](#schemaexif)|false|none|none|
|»» make|string|false|none|none|
|»» model|string|false|none|none|
|»» exposure_time|string|false|none|none|
|»» aperture|number(double)|false|none|none|
|»» focal_length|number(double)|false|none|none|
|»» iso|integer|false|none|none|
|» height|integer|false|none|none|
|» id|string|false|none|none|
|» liked_by_user|boolean|false|none|none|
|» likes|integer|false|none|none|
|» links|[PhotoLinks](#schemaphotolinks)|false|none|none|
|»» download|string|false|none|none|
|»» download_location|string|false|none|none|
|»» html|string|false|none|none|
|»» self|string|false|none|none|
|» location|[Location](#schemalocation)|false|none|none|
|»» city|string|false|none|none|
|»» country|string|false|none|none|
|»» name|string|false|none|none|
|»» position|object|false|none|none|
|»»» latitude|number(double)|false|none|none|
|»»» longitude|number(double)|false|none|none|
|» tags|[object]|false|none|none|
|»» title|string|false|none|none|
|» updated_at|string(date-time)|false|none|none|
|» urls|[PhotoUrls](#schemaphotourls)|false|none|none|
|»» raw|string|false|none|none|
|»» full|string|false|none|none|
|»» regular|string|false|none|none|
|»» small|string|false|none|none|
|»» thumb|string|false|none|none|
|» user|[User](#schemauser)|false|none|none|
|» width|integer|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
publicAuth
</aside>

## getRelatedCollections

<a id="opIdgetRelatedCollections"></a>

> Code samples

```shell
curl --request GET \
  --url https://api.unsplash.com//collections/string/related \
  --header 'Accept: application/json' \
  --header 'Authorization: API_KEY'
```

`GET /collections/{id}/related`

*List a collection’s related collections*

Retrieve a list of collections related to this one.

<h3 id="getrelatedcollections-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The collection’s ID.|

> Example responses

> 200 Response

```json
[
  {
    "cover_photo": {
      "blur_hash": "string",
      "color": "string",
      "created_at": "2019-08-24T14:15:22Z",
      "current_user_collections": [
        {}
      ],
      "description": "string",
      "downloads": 0,
      "exif": {
        "make": "string",
        "model": "string",
        "exposure_time": "string",
        "aperture": 0,
        "focal_length": 0,
        "iso": 0
      },
      "height": 0,
      "id": "string",
      "liked_by_user": true,
      "likes": 0,
      "links": {
        "download": "string",
        "download_location": "string",
        "html": "string",
        "self": "string"
      },
      "location": {
        "city": "string",
        "country": "string",
        "name": "string",
        "position": {
          "latitude": 0,
          "longitude": 0
        }
      },
      "tags": [
        {
          "title": "string"
        }
      ],
      "updated_at": "2019-08-24T14:15:22Z",
      "urls": {
        "raw": "string",
        "full": "string",
        "regular": "string",
        "small": "string",
        "thumb": "string"
      },
      "user": {
        "badge": {
          "link": "string",
          "primary": true,
          "slug": "string",
          "title": "string"
        },
        "bio": "string",
        "downloads": 0,
        "first_name": "string",
        "followed_by_user": true,
        "followers_count": 0,
        "following_count": 0,
        "id": "string",
        "instagram_username": "string",
        "last_name": "string",
        "links": {
          "html": "string",
          "likes": "string",
          "photos": "string",
          "portfolio": "string",
          "self": "string"
        },
        "location": "string",
        "name": "string",
        "portfolio_url": "string",
        "profile_image": {
          "small": "string",
          "medium": "string",
          "large": "string"
        },
        "total_collections": 0,
        "total_likes": 0,
        "total_photos": 0,
        "twitter_username": "string",
        "updated_at": "2019-08-24T14:15:22Z",
        "username": "string"
      },
      "width": 0
    },
    "description": "string",
    "featured": true,
    "id": 0,
    "last_collected_at": "2019-08-24T14:15:22Z",
    "links": {
      "html": "string",
      "photos": "string",
      "related": "string",
      "self": "string"
    },
    "private": true,
    "published_at": "2019-08-24T14:15:22Z",
    "share_key": "string",
    "title": "string",
    "total_photos": true,
    "updated_at": "2019-08-24T14:15:22Z",
    "user": {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    }
  }
]
```

<h3 id="getrelatedcollections-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="getrelatedcollections-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Collection](#schemacollection)]|false|none|none|
|» cover_photo|[Photo](#schemaphoto)|false|none|none|
|»» blur_hash|string|false|none|none|
|»» color|string|false|none|none|
|»» created_at|string(date-time)|false|none|none|
|»» current_user_collections|[[Collection](#schemacollection)]|false|none|none|
|»» description|string|false|none|none|
|»» downloads|integer|false|none|none|
|»» exif|[Exif](#schemaexif)|false|none|none|
|»»» make|string|false|none|none|
|»»» model|string|false|none|none|
|»»» exposure_time|string|false|none|none|
|»»» aperture|number(double)|false|none|none|
|»»» focal_length|number(double)|false|none|none|
|»»» iso|integer|false|none|none|
|»» height|integer|false|none|none|
|»» id|string|false|none|none|
|»» liked_by_user|boolean|false|none|none|
|»» likes|integer|false|none|none|
|»» links|[PhotoLinks](#schemaphotolinks)|false|none|none|
|»»» download|string|false|none|none|
|»»» download_location|string|false|none|none|
|»»» html|string|false|none|none|
|»»» self|string|false|none|none|
|»» location|[Location](#schemalocation)|false|none|none|
|»»» city|string|false|none|none|
|»»» country|string|false|none|none|
|»»» name|string|false|none|none|
|»»» position|object|false|none|none|
|»»»» latitude|number(double)|false|none|none|
|»»»» longitude|number(double)|false|none|none|
|»» tags|[object]|false|none|none|
|»»» title|string|false|none|none|
|»» updated_at|string(date-time)|false|none|none|
|»» urls|[PhotoUrls](#schemaphotourls)|false|none|none|
|»»» raw|string|false|none|none|
|»»» full|string|false|none|none|
|»»» regular|string|false|none|none|
|»»» small|string|false|none|none|
|»»» thumb|string|false|none|none|
|»» user|[User](#schemauser)|false|none|none|
|»»» badge|object|false|none|none|
|»»»» link|string|false|none|none|
|»»»» primary|boolean|false|none|none|
|»»»» slug|string|false|none|none|
|»»»» title|string|false|none|none|
|»»» bio|string|false|none|none|
|»»» downloads|integer|false|none|none|
|»»» first_name|string|false|none|none|
|»»» followed_by_user|boolean|false|none|none|
|»»» followers_count|integer|false|none|none|
|»»» following_count|integer|false|none|none|
|»»» id|string|false|none|none|
|»»» instagram_username|string|false|none|none|
|»»» last_name|string|false|none|none|
|»»» links|[UserLinks](#schemauserlinks)|false|none|none|
|»»»» html|string|false|none|none|
|»»»» likes|string|false|none|none|
|»»»» photos|string|false|none|none|
|»»»» portfolio|string|false|none|none|
|»»»» self|string|false|none|none|
|»»» location|string|false|none|none|
|»»» name|string|false|none|none|
|»»» portfolio_url|string|false|none|none|
|»»» profile_image|[ProfileImage](#schemaprofileimage)|false|none|none|
|»»»» small|string|false|none|none|
|»»»» medium|string|false|none|none|
|»»»» large|string|false|none|none|
|»»» total_collections|integer|false|none|none|
|»»» total_likes|integer|false|none|none|
|»»» total_photos|integer|false|none|none|
|»»» twitter_username|string|false|none|none|
|»»» updated_at|string(date-time)|false|none|none|
|»»» username|string|false|none|none|
|»» width|integer|false|none|none|
|» description|string|false|none|none|
|» featured|boolean|false|none|none|
|» id|integer|false|none|none|
|» last_collected_at|string(date-time)|false|none|none|
|» links|[CollectionLinks](#schemacollectionlinks)|false|none|none|
|»» html|string|false|none|none|
|»» photos|string|false|none|none|
|»» related|string|false|none|none|
|»» self|string|false|none|none|
|» private|boolean|false|none|none|
|» published_at|string(date-time)|false|none|none|
|» share_key|string|false|none|none|
|» title|string|false|none|none|
|» total_photos|boolean|false|none|none|
|» updated_at|string(date-time)|false|none|none|
|» user|[User](#schemauser)|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
publicAuth
</aside>

## addPhotoToCollection

<a id="opIdaddPhotoToCollection"></a>

> Code samples

```shell
curl --request POST \
  --url 'https://api.unsplash.com//collections/string/add?photo_id=string' \
  --header 'Accept: application/json' \
  --header 'Authorization: Bearer {access-token}'
```

`POST /collections/{collection_id}/add`

*Add a photo to a collection*

Add a photo to one of the logged-in user’s collections. Requires the write_collections scope. If the photo is already in the collection, this action has no effect.

<h3 id="addphototocollection-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|collection_id|path|string|true|The collection’s ID.|
|photo_id|query|string|true|The photo's ID.|

> Example responses

> 201 Response

```json
{
  "photo": {
    "blur_hash": "string",
    "color": "string",
    "created_at": "2019-08-24T14:15:22Z",
    "current_user_collections": [
      {
        "cover_photo": {},
        "description": "string",
        "featured": true,
        "id": 0,
        "last_collected_at": "2019-08-24T14:15:22Z",
        "links": {
          "html": "string",
          "photos": "string",
          "related": "string",
          "self": "string"
        },
        "private": true,
        "published_at": "2019-08-24T14:15:22Z",
        "share_key": "string",
        "title": "string",
        "total_photos": true,
        "updated_at": "2019-08-24T14:15:22Z",
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        }
      }
    ],
    "description": "string",
    "downloads": 0,
    "exif": {
      "make": "string",
      "model": "string",
      "exposure_time": "string",
      "aperture": 0,
      "focal_length": 0,
      "iso": 0
    },
    "height": 0,
    "id": "string",
    "liked_by_user": true,
    "likes": 0,
    "links": {
      "download": "string",
      "download_location": "string",
      "html": "string",
      "self": "string"
    },
    "location": {
      "city": "string",
      "country": "string",
      "name": "string",
      "position": {
        "latitude": 0,
        "longitude": 0
      }
    },
    "tags": [
      {
        "title": "string"
      }
    ],
    "updated_at": "2019-08-24T14:15:22Z",
    "urls": {
      "raw": "string",
      "full": "string",
      "regular": "string",
      "small": "string",
      "thumb": "string"
    },
    "user": {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    },
    "width": 0
  },
  "collection": {
    "cover_photo": {
      "blur_hash": "string",
      "color": "string",
      "created_at": "2019-08-24T14:15:22Z",
      "current_user_collections": [
        {}
      ],
      "description": "string",
      "downloads": 0,
      "exif": {
        "make": "string",
        "model": "string",
        "exposure_time": "string",
        "aperture": 0,
        "focal_length": 0,
        "iso": 0
      },
      "height": 0,
      "id": "string",
      "liked_by_user": true,
      "likes": 0,
      "links": {
        "download": "string",
        "download_location": "string",
        "html": "string",
        "self": "string"
      },
      "location": {
        "city": "string",
        "country": "string",
        "name": "string",
        "position": {
          "latitude": 0,
          "longitude": 0
        }
      },
      "tags": [
        {
          "title": "string"
        }
      ],
      "updated_at": "2019-08-24T14:15:22Z",
      "urls": {
        "raw": "string",
        "full": "string",
        "regular": "string",
        "small": "string",
        "thumb": "string"
      },
      "user": {
        "badge": {
          "link": "string",
          "primary": true,
          "slug": "string",
          "title": "string"
        },
        "bio": "string",
        "downloads": 0,
        "first_name": "string",
        "followed_by_user": true,
        "followers_count": 0,
        "following_count": 0,
        "id": "string",
        "instagram_username": "string",
        "last_name": "string",
        "links": {
          "html": "string",
          "likes": "string",
          "photos": "string",
          "portfolio": "string",
          "self": "string"
        },
        "location": "string",
        "name": "string",
        "portfolio_url": "string",
        "profile_image": {
          "small": "string",
          "medium": "string",
          "large": "string"
        },
        "total_collections": 0,
        "total_likes": 0,
        "total_photos": 0,
        "twitter_username": "string",
        "updated_at": "2019-08-24T14:15:22Z",
        "username": "string"
      },
      "width": 0
    },
    "description": "string",
    "featured": true,
    "id": 0,
    "last_collected_at": "2019-08-24T14:15:22Z",
    "links": {
      "html": "string",
      "photos": "string",
      "related": "string",
      "self": "string"
    },
    "private": true,
    "published_at": "2019-08-24T14:15:22Z",
    "share_key": "string",
    "title": "string",
    "total_photos": true,
    "updated_at": "2019-08-24T14:15:22Z",
    "user": {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    }
  },
  "user": {
    "badge": {
      "link": "string",
      "primary": true,
      "slug": "string",
      "title": "string"
    },
    "bio": "string",
    "downloads": 0,
    "first_name": "string",
    "followed_by_user": true,
    "followers_count": 0,
    "following_count": 0,
    "id": "string",
    "instagram_username": "string",
    "last_name": "string",
    "links": {
      "html": "string",
      "likes": "string",
      "photos": "string",
      "portfolio": "string",
      "self": "string"
    },
    "location": "string",
    "name": "string",
    "portfolio_url": "string",
    "profile_image": {
      "small": "string",
      "medium": "string",
      "large": "string"
    },
    "total_collections": 0,
    "total_likes": 0,
    "total_photos": 0,
    "twitter_username": "string",
    "updated_at": "2019-08-24T14:15:22Z",
    "username": "string"
  },
  "created_at": "2019-08-24T14:15:22Z"
}
```

<h3 id="addphototocollection-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Created|[OperationResponse](#schemaoperationresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
userAuth ( Scopes: write_collections )
</aside>

## removePhotoFromCollection

<a id="opIdremovePhotoFromCollection"></a>

> Code samples

```shell
curl --request DELETE \
  --url 'https://api.unsplash.com//collections/string/remove?photo_id=string' \
  --header 'Accept: application/json' \
  --header 'Authorization: Bearer {access-token}'
```

`DELETE /collections/{collection_id}/remove`

*Remove a photo from a collection*

Remove a photo from one of the logged-in user’s collections. Requires the write_collections scope.

<h3 id="removephotofromcollection-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|collection_id|path|string|true|The collection’s ID.|
|photo_id|query|string|true|The photo's ID.|

> Example responses

> 200 Response

```json
{
  "photo": {
    "blur_hash": "string",
    "color": "string",
    "created_at": "2019-08-24T14:15:22Z",
    "current_user_collections": [
      {
        "cover_photo": {},
        "description": "string",
        "featured": true,
        "id": 0,
        "last_collected_at": "2019-08-24T14:15:22Z",
        "links": {
          "html": "string",
          "photos": "string",
          "related": "string",
          "self": "string"
        },
        "private": true,
        "published_at": "2019-08-24T14:15:22Z",
        "share_key": "string",
        "title": "string",
        "total_photos": true,
        "updated_at": "2019-08-24T14:15:22Z",
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        }
      }
    ],
    "description": "string",
    "downloads": 0,
    "exif": {
      "make": "string",
      "model": "string",
      "exposure_time": "string",
      "aperture": 0,
      "focal_length": 0,
      "iso": 0
    },
    "height": 0,
    "id": "string",
    "liked_by_user": true,
    "likes": 0,
    "links": {
      "download": "string",
      "download_location": "string",
      "html": "string",
      "self": "string"
    },
    "location": {
      "city": "string",
      "country": "string",
      "name": "string",
      "position": {
        "latitude": 0,
        "longitude": 0
      }
    },
    "tags": [
      {
        "title": "string"
      }
    ],
    "updated_at": "2019-08-24T14:15:22Z",
    "urls": {
      "raw": "string",
      "full": "string",
      "regular": "string",
      "small": "string",
      "thumb": "string"
    },
    "user": {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    },
    "width": 0
  },
  "collection": {
    "cover_photo": {
      "blur_hash": "string",
      "color": "string",
      "created_at": "2019-08-24T14:15:22Z",
      "current_user_collections": [
        {}
      ],
      "description": "string",
      "downloads": 0,
      "exif": {
        "make": "string",
        "model": "string",
        "exposure_time": "string",
        "aperture": 0,
        "focal_length": 0,
        "iso": 0
      },
      "height": 0,
      "id": "string",
      "liked_by_user": true,
      "likes": 0,
      "links": {
        "download": "string",
        "download_location": "string",
        "html": "string",
        "self": "string"
      },
      "location": {
        "city": "string",
        "country": "string",
        "name": "string",
        "position": {
          "latitude": 0,
          "longitude": 0
        }
      },
      "tags": [
        {
          "title": "string"
        }
      ],
      "updated_at": "2019-08-24T14:15:22Z",
      "urls": {
        "raw": "string",
        "full": "string",
        "regular": "string",
        "small": "string",
        "thumb": "string"
      },
      "user": {
        "badge": {
          "link": "string",
          "primary": true,
          "slug": "string",
          "title": "string"
        },
        "bio": "string",
        "downloads": 0,
        "first_name": "string",
        "followed_by_user": true,
        "followers_count": 0,
        "following_count": 0,
        "id": "string",
        "instagram_username": "string",
        "last_name": "string",
        "links": {
          "html": "string",
          "likes": "string",
          "photos": "string",
          "portfolio": "string",
          "self": "string"
        },
        "location": "string",
        "name": "string",
        "portfolio_url": "string",
        "profile_image": {
          "small": "string",
          "medium": "string",
          "large": "string"
        },
        "total_collections": 0,
        "total_likes": 0,
        "total_photos": 0,
        "twitter_username": "string",
        "updated_at": "2019-08-24T14:15:22Z",
        "username": "string"
      },
      "width": 0
    },
    "description": "string",
    "featured": true,
    "id": 0,
    "last_collected_at": "2019-08-24T14:15:22Z",
    "links": {
      "html": "string",
      "photos": "string",
      "related": "string",
      "self": "string"
    },
    "private": true,
    "published_at": "2019-08-24T14:15:22Z",
    "share_key": "string",
    "title": "string",
    "total_photos": true,
    "updated_at": "2019-08-24T14:15:22Z",
    "user": {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    }
  },
  "user": {
    "badge": {
      "link": "string",
      "primary": true,
      "slug": "string",
      "title": "string"
    },
    "bio": "string",
    "downloads": 0,
    "first_name": "string",
    "followed_by_user": true,
    "followers_count": 0,
    "following_count": 0,
    "id": "string",
    "instagram_username": "string",
    "last_name": "string",
    "links": {
      "html": "string",
      "likes": "string",
      "photos": "string",
      "portfolio": "string",
      "self": "string"
    },
    "location": "string",
    "name": "string",
    "portfolio_url": "string",
    "profile_image": {
      "small": "string",
      "medium": "string",
      "large": "string"
    },
    "total_collections": 0,
    "total_likes": 0,
    "total_photos": 0,
    "twitter_username": "string",
    "updated_at": "2019-08-24T14:15:22Z",
    "username": "string"
  },
  "created_at": "2019-08-24T14:15:22Z"
}
```

<h3 id="removephotofromcollection-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[OperationResponse](#schemaoperationresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
userAuth ( Scopes: write_collections )
</aside>

<h1 id="unsplash-api-topics">Topics</h1>

<a href="https://unsplash.com/documentation#topics">Find out more</a>

## getTopicPhotos

<a id="opIdgetTopicPhotos"></a>

> Code samples

```shell
curl --request GET \
  --url https://api.unsplash.com//topics/string/photos \
  --header 'Accept: application/json' \
  --header 'Authorization: API_KEY'
```

`GET /topics/{id_or_slug}/photos`

*Get a topic’s photos*

Retrieve a topic’s photos.

<h3 id="gettopicphotos-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id_or_slug|path|string|true|The topics’s ID or slug.|
|page|query|integer|false|Page number to retrieve. (Optional, default: 1)|
|per_page|query|integer|false|Number of items per page. (Optional; default: 10)|
|orientation|query|[Orientation](#schemaorientation)|false|Filter by photo orientation. (Optional; Valid values: landscape, portrait, squarish)|
|order_by|query|[OrderBy](#schemaorderby)|false|How to sort the photos. Optional. (Valid values: latest, oldest, popular; default: latest)|

#### Detailed descriptions

**page**: Page number to retrieve. (Optional, default: 1)

**per_page**: Number of items per page. (Optional; default: 10)

**orientation**: Filter by photo orientation. (Optional; Valid values: landscape, portrait, squarish)

**order_by**: How to sort the photos. Optional. (Valid values: latest, oldest, popular; default: latest)

#### Enumerated Values

|Parameter|Value|
|---|---|
|orientation|landscape|
|orientation|portrait|
|orientation|squarish|
|order_by|latest|
|order_by|oldest|
|order_by|popular|

> Example responses

> 200 Response

```json
[
  {
    "blur_hash": "string",
    "color": "string",
    "created_at": "2019-08-24T14:15:22Z",
    "current_user_collections": [
      {
        "cover_photo": {},
        "description": "string",
        "featured": true,
        "id": 0,
        "last_collected_at": "2019-08-24T14:15:22Z",
        "links": {
          "html": "string",
          "photos": "string",
          "related": "string",
          "self": "string"
        },
        "private": true,
        "published_at": "2019-08-24T14:15:22Z",
        "share_key": "string",
        "title": "string",
        "total_photos": true,
        "updated_at": "2019-08-24T14:15:22Z",
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        }
      }
    ],
    "description": "string",
    "downloads": 0,
    "exif": {
      "make": "string",
      "model": "string",
      "exposure_time": "string",
      "aperture": 0,
      "focal_length": 0,
      "iso": 0
    },
    "height": 0,
    "id": "string",
    "liked_by_user": true,
    "likes": 0,
    "links": {
      "download": "string",
      "download_location": "string",
      "html": "string",
      "self": "string"
    },
    "location": {
      "city": "string",
      "country": "string",
      "name": "string",
      "position": {
        "latitude": 0,
        "longitude": 0
      }
    },
    "tags": [
      {
        "title": "string"
      }
    ],
    "updated_at": "2019-08-24T14:15:22Z",
    "urls": {
      "raw": "string",
      "full": "string",
      "regular": "string",
      "small": "string",
      "thumb": "string"
    },
    "user": {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    },
    "width": 0
  }
]
```

<h3 id="gettopicphotos-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="gettopicphotos-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Photo](#schemaphoto)]|false|none|none|
|» blur_hash|string|false|none|none|
|» color|string|false|none|none|
|» created_at|string(date-time)|false|none|none|
|» current_user_collections|[[Collection](#schemacollection)]|false|none|none|
|»» cover_photo|[Photo](#schemaphoto)|false|none|none|
|»» description|string|false|none|none|
|»» featured|boolean|false|none|none|
|»» id|integer|false|none|none|
|»» last_collected_at|string(date-time)|false|none|none|
|»» links|[CollectionLinks](#schemacollectionlinks)|false|none|none|
|»»» html|string|false|none|none|
|»»» photos|string|false|none|none|
|»»» related|string|false|none|none|
|»»» self|string|false|none|none|
|»» private|boolean|false|none|none|
|»» published_at|string(date-time)|false|none|none|
|»» share_key|string|false|none|none|
|»» title|string|false|none|none|
|»» total_photos|boolean|false|none|none|
|»» updated_at|string(date-time)|false|none|none|
|»» user|[User](#schemauser)|false|none|none|
|»»» badge|object|false|none|none|
|»»»» link|string|false|none|none|
|»»»» primary|boolean|false|none|none|
|»»»» slug|string|false|none|none|
|»»»» title|string|false|none|none|
|»»» bio|string|false|none|none|
|»»» downloads|integer|false|none|none|
|»»» first_name|string|false|none|none|
|»»» followed_by_user|boolean|false|none|none|
|»»» followers_count|integer|false|none|none|
|»»» following_count|integer|false|none|none|
|»»» id|string|false|none|none|
|»»» instagram_username|string|false|none|none|
|»»» last_name|string|false|none|none|
|»»» links|[UserLinks](#schemauserlinks)|false|none|none|
|»»»» html|string|false|none|none|
|»»»» likes|string|false|none|none|
|»»»» photos|string|false|none|none|
|»»»» portfolio|string|false|none|none|
|»»»» self|string|false|none|none|
|»»» location|string|false|none|none|
|»»» name|string|false|none|none|
|»»» portfolio_url|string|false|none|none|
|»»» profile_image|[ProfileImage](#schemaprofileimage)|false|none|none|
|»»»» small|string|false|none|none|
|»»»» medium|string|false|none|none|
|»»»» large|string|false|none|none|
|»»» total_collections|integer|false|none|none|
|»»» total_likes|integer|false|none|none|
|»»» total_photos|integer|false|none|none|
|»»» twitter_username|string|false|none|none|
|»»» updated_at|string(date-time)|false|none|none|
|»»» username|string|false|none|none|
|» description|string|false|none|none|
|» downloads|integer|false|none|none|
|» exif|[Exif](#schemaexif)|false|none|none|
|»» make|string|false|none|none|
|»» model|string|false|none|none|
|»» exposure_time|string|false|none|none|
|»» aperture|number(double)|false|none|none|
|»» focal_length|number(double)|false|none|none|
|»» iso|integer|false|none|none|
|» height|integer|false|none|none|
|» id|string|false|none|none|
|» liked_by_user|boolean|false|none|none|
|» likes|integer|false|none|none|
|» links|[PhotoLinks](#schemaphotolinks)|false|none|none|
|»» download|string|false|none|none|
|»» download_location|string|false|none|none|
|»» html|string|false|none|none|
|»» self|string|false|none|none|
|» location|[Location](#schemalocation)|false|none|none|
|»» city|string|false|none|none|
|»» country|string|false|none|none|
|»» name|string|false|none|none|
|»» position|object|false|none|none|
|»»» latitude|number(double)|false|none|none|
|»»» longitude|number(double)|false|none|none|
|» tags|[object]|false|none|none|
|»» title|string|false|none|none|
|» updated_at|string(date-time)|false|none|none|
|» urls|[PhotoUrls](#schemaphotourls)|false|none|none|
|»» raw|string|false|none|none|
|»» full|string|false|none|none|
|»» regular|string|false|none|none|
|»» small|string|false|none|none|
|»» thumb|string|false|none|none|
|» user|[User](#schemauser)|false|none|none|
|» width|integer|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
publicAuth
</aside>

# Schemas

<h2 id="tocS_Badge">Badge</h2>
<!-- backwards compatibility -->
<a id="schemabadge"></a>
<a id="schema_Badge"></a>
<a id="tocSbadge"></a>
<a id="tocsbadge"></a>

```json
{
  "link": "string",
  "primary": true,
  "slug": "string",
  "title": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|link|string|false|none|none|
|primary|boolean|false|none|none|
|slug|string|false|none|none|
|title|string|false|none|none|

<h2 id="tocS_Collection">Collection</h2>
<!-- backwards compatibility -->
<a id="schemacollection"></a>
<a id="schema_Collection"></a>
<a id="tocScollection"></a>
<a id="tocscollection"></a>

```json
{
  "cover_photo": {
    "blur_hash": "string",
    "color": "string",
    "created_at": "2019-08-24T14:15:22Z",
    "current_user_collections": [
      {
        "cover_photo": {},
        "description": "string",
        "featured": true,
        "id": 0,
        "last_collected_at": "2019-08-24T14:15:22Z",
        "links": {
          "html": "string",
          "photos": "string",
          "related": "string",
          "self": "string"
        },
        "private": true,
        "published_at": "2019-08-24T14:15:22Z",
        "share_key": "string",
        "title": "string",
        "total_photos": true,
        "updated_at": "2019-08-24T14:15:22Z",
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        }
      }
    ],
    "description": "string",
    "downloads": 0,
    "exif": {
      "make": "string",
      "model": "string",
      "exposure_time": "string",
      "aperture": 0,
      "focal_length": 0,
      "iso": 0
    },
    "height": 0,
    "id": "string",
    "liked_by_user": true,
    "likes": 0,
    "links": {
      "download": "string",
      "download_location": "string",
      "html": "string",
      "self": "string"
    },
    "location": {
      "city": "string",
      "country": "string",
      "name": "string",
      "position": {
        "latitude": 0,
        "longitude": 0
      }
    },
    "tags": [
      {
        "title": "string"
      }
    ],
    "updated_at": "2019-08-24T14:15:22Z",
    "urls": {
      "raw": "string",
      "full": "string",
      "regular": "string",
      "small": "string",
      "thumb": "string"
    },
    "user": {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    },
    "width": 0
  },
  "description": "string",
  "featured": true,
  "id": 0,
  "last_collected_at": "2019-08-24T14:15:22Z",
  "links": {
    "html": "string",
    "photos": "string",
    "related": "string",
    "self": "string"
  },
  "private": true,
  "published_at": "2019-08-24T14:15:22Z",
  "share_key": "string",
  "title": "string",
  "total_photos": true,
  "updated_at": "2019-08-24T14:15:22Z",
  "user": {
    "badge": {
      "link": "string",
      "primary": true,
      "slug": "string",
      "title": "string"
    },
    "bio": "string",
    "downloads": 0,
    "first_name": "string",
    "followed_by_user": true,
    "followers_count": 0,
    "following_count": 0,
    "id": "string",
    "instagram_username": "string",
    "last_name": "string",
    "links": {
      "html": "string",
      "likes": "string",
      "photos": "string",
      "portfolio": "string",
      "self": "string"
    },
    "location": "string",
    "name": "string",
    "portfolio_url": "string",
    "profile_image": {
      "small": "string",
      "medium": "string",
      "large": "string"
    },
    "total_collections": 0,
    "total_likes": 0,
    "total_photos": 0,
    "twitter_username": "string",
    "updated_at": "2019-08-24T14:15:22Z",
    "username": "string"
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|cover_photo|[Photo](#schemaphoto)|false|none|none|
|description|string|false|none|none|
|featured|boolean|false|none|none|
|id|integer|false|none|none|
|last_collected_at|string(date-time)|false|none|none|
|links|[CollectionLinks](#schemacollectionlinks)|false|none|none|
|private|boolean|false|none|none|
|published_at|string(date-time)|false|none|none|
|share_key|string|false|none|none|
|title|string|false|none|none|
|total_photos|boolean|false|none|none|
|updated_at|string(date-time)|false|none|none|
|user|[User](#schemauser)|false|none|none|

<h2 id="tocS_CollectionLinks">CollectionLinks</h2>
<!-- backwards compatibility -->
<a id="schemacollectionlinks"></a>
<a id="schema_CollectionLinks"></a>
<a id="tocScollectionlinks"></a>
<a id="tocscollectionlinks"></a>

```json
{
  "html": "string",
  "photos": "string",
  "related": "string",
  "self": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|html|string|false|none|none|
|photos|string|false|none|none|
|related|string|false|none|none|
|self|string|false|none|none|

<h2 id="tocS_CollectionSearchResults">CollectionSearchResults</h2>
<!-- backwards compatibility -->
<a id="schemacollectionsearchresults"></a>
<a id="schema_CollectionSearchResults"></a>
<a id="tocScollectionsearchresults"></a>
<a id="tocscollectionsearchresults"></a>

```json
{
  "total": 0,
  "total_pages": 0,
  "results": [
    {
      "cover_photo": {
        "blur_hash": "string",
        "color": "string",
        "created_at": "2019-08-24T14:15:22Z",
        "current_user_collections": [
          {}
        ],
        "description": "string",
        "downloads": 0,
        "exif": {
          "make": "string",
          "model": "string",
          "exposure_time": "string",
          "aperture": 0,
          "focal_length": 0,
          "iso": 0
        },
        "height": 0,
        "id": "string",
        "liked_by_user": true,
        "likes": 0,
        "links": {
          "download": "string",
          "download_location": "string",
          "html": "string",
          "self": "string"
        },
        "location": {
          "city": "string",
          "country": "string",
          "name": "string",
          "position": {
            "latitude": 0,
            "longitude": 0
          }
        },
        "tags": [
          {
            "title": "string"
          }
        ],
        "updated_at": "2019-08-24T14:15:22Z",
        "urls": {
          "raw": "string",
          "full": "string",
          "regular": "string",
          "small": "string",
          "thumb": "string"
        },
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        },
        "width": 0
      },
      "description": "string",
      "featured": true,
      "id": 0,
      "last_collected_at": "2019-08-24T14:15:22Z",
      "links": {
        "html": "string",
        "photos": "string",
        "related": "string",
        "self": "string"
      },
      "private": true,
      "published_at": "2019-08-24T14:15:22Z",
      "share_key": "string",
      "title": "string",
      "total_photos": true,
      "updated_at": "2019-08-24T14:15:22Z",
      "user": {
        "badge": {
          "link": "string",
          "primary": true,
          "slug": "string",
          "title": "string"
        },
        "bio": "string",
        "downloads": 0,
        "first_name": "string",
        "followed_by_user": true,
        "followers_count": 0,
        "following_count": 0,
        "id": "string",
        "instagram_username": "string",
        "last_name": "string",
        "links": {
          "html": "string",
          "likes": "string",
          "photos": "string",
          "portfolio": "string",
          "self": "string"
        },
        "location": "string",
        "name": "string",
        "portfolio_url": "string",
        "profile_image": {
          "small": "string",
          "medium": "string",
          "large": "string"
        },
        "total_collections": 0,
        "total_likes": 0,
        "total_photos": 0,
        "twitter_username": "string",
        "updated_at": "2019-08-24T14:15:22Z",
        "username": "string"
      }
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|total|integer|false|none|none|
|total_pages|integer|false|none|none|
|results|[[Collection](#schemacollection)]|false|none|none|

<h2 id="tocS_CurrentUser">CurrentUser</h2>
<!-- backwards compatibility -->
<a id="schemacurrentuser"></a>
<a id="schema_CurrentUser"></a>
<a id="tocScurrentuser"></a>
<a id="tocscurrentuser"></a>

```json
{
  "bio": "string",
  "downloads": 0,
  "email": "string",
  "first_name": "string",
  "followed_by_user": true,
  "id": "string",
  "instagram_username": "string",
  "last_name": "string",
  "links": {
    "html": "string",
    "likes": "string",
    "photos": "string",
    "portfolio": "string",
    "self": "string"
  },
  "location": "string",
  "portfolio_url": "string",
  "total_collections": 0,
  "total_likes": 0,
  "total_photos": 0,
  "twitter_username": "string",
  "updated_at": "string",
  "uploads_remaining": 0,
  "username": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|bio|string|false|none|none|
|downloads|integer|false|none|none|
|email|string|false|none|none|
|first_name|string|false|none|none|
|followed_by_user|boolean|false|none|none|
|id|string|false|none|none|
|instagram_username|string|false|none|none|
|last_name|string|false|none|none|
|links|[UserLinks](#schemauserlinks)|false|none|none|
|location|string|false|none|none|
|portfolio_url|string|false|none|none|
|total_collections|integer|false|none|none|
|total_likes|integer|false|none|none|
|total_photos|integer|false|none|none|
|twitter_username|string|false|none|none|
|updated_at|string|false|none|none|
|uploads_remaining|integer|false|none|none|
|username|string|false|none|none|

<h2 id="tocS_Photo">Photo</h2>
<!-- backwards compatibility -->
<a id="schemaphoto"></a>
<a id="schema_Photo"></a>
<a id="tocSphoto"></a>
<a id="tocsphoto"></a>

```json
{
  "blur_hash": "string",
  "color": "string",
  "created_at": "2019-08-24T14:15:22Z",
  "current_user_collections": [
    {
      "cover_photo": {
        "blur_hash": "string",
        "color": "string",
        "created_at": "2019-08-24T14:15:22Z",
        "current_user_collections": [],
        "description": "string",
        "downloads": 0,
        "exif": {
          "make": "string",
          "model": "string",
          "exposure_time": "string",
          "aperture": 0,
          "focal_length": 0,
          "iso": 0
        },
        "height": 0,
        "id": "string",
        "liked_by_user": true,
        "likes": 0,
        "links": {
          "download": "string",
          "download_location": "string",
          "html": "string",
          "self": "string"
        },
        "location": {
          "city": "string",
          "country": "string",
          "name": "string",
          "position": {
            "latitude": 0,
            "longitude": 0
          }
        },
        "tags": [
          {
            "title": "string"
          }
        ],
        "updated_at": "2019-08-24T14:15:22Z",
        "urls": {
          "raw": "string",
          "full": "string",
          "regular": "string",
          "small": "string",
          "thumb": "string"
        },
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        },
        "width": 0
      },
      "description": "string",
      "featured": true,
      "id": 0,
      "last_collected_at": "2019-08-24T14:15:22Z",
      "links": {
        "html": "string",
        "photos": "string",
        "related": "string",
        "self": "string"
      },
      "private": true,
      "published_at": "2019-08-24T14:15:22Z",
      "share_key": "string",
      "title": "string",
      "total_photos": true,
      "updated_at": "2019-08-24T14:15:22Z",
      "user": {
        "badge": {
          "link": "string",
          "primary": true,
          "slug": "string",
          "title": "string"
        },
        "bio": "string",
        "downloads": 0,
        "first_name": "string",
        "followed_by_user": true,
        "followers_count": 0,
        "following_count": 0,
        "id": "string",
        "instagram_username": "string",
        "last_name": "string",
        "links": {
          "html": "string",
          "likes": "string",
          "photos": "string",
          "portfolio": "string",
          "self": "string"
        },
        "location": "string",
        "name": "string",
        "portfolio_url": "string",
        "profile_image": {
          "small": "string",
          "medium": "string",
          "large": "string"
        },
        "total_collections": 0,
        "total_likes": 0,
        "total_photos": 0,
        "twitter_username": "string",
        "updated_at": "2019-08-24T14:15:22Z",
        "username": "string"
      }
    }
  ],
  "description": "string",
  "downloads": 0,
  "exif": {
    "make": "string",
    "model": "string",
    "exposure_time": "string",
    "aperture": 0,
    "focal_length": 0,
    "iso": 0
  },
  "height": 0,
  "id": "string",
  "liked_by_user": true,
  "likes": 0,
  "links": {
    "download": "string",
    "download_location": "string",
    "html": "string",
    "self": "string"
  },
  "location": {
    "city": "string",
    "country": "string",
    "name": "string",
    "position": {
      "latitude": 0,
      "longitude": 0
    }
  },
  "tags": [
    {
      "title": "string"
    }
  ],
  "updated_at": "2019-08-24T14:15:22Z",
  "urls": {
    "raw": "string",
    "full": "string",
    "regular": "string",
    "small": "string",
    "thumb": "string"
  },
  "user": {
    "badge": {
      "link": "string",
      "primary": true,
      "slug": "string",
      "title": "string"
    },
    "bio": "string",
    "downloads": 0,
    "first_name": "string",
    "followed_by_user": true,
    "followers_count": 0,
    "following_count": 0,
    "id": "string",
    "instagram_username": "string",
    "last_name": "string",
    "links": {
      "html": "string",
      "likes": "string",
      "photos": "string",
      "portfolio": "string",
      "self": "string"
    },
    "location": "string",
    "name": "string",
    "portfolio_url": "string",
    "profile_image": {
      "small": "string",
      "medium": "string",
      "large": "string"
    },
    "total_collections": 0,
    "total_likes": 0,
    "total_photos": 0,
    "twitter_username": "string",
    "updated_at": "2019-08-24T14:15:22Z",
    "username": "string"
  },
  "width": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|blur_hash|string|false|none|none|
|color|string|false|none|none|
|created_at|string(date-time)|false|none|none|
|current_user_collections|[[Collection](#schemacollection)]|false|none|none|
|description|string|false|none|none|
|downloads|integer|false|none|none|
|exif|[Exif](#schemaexif)|false|none|none|
|height|integer|false|none|none|
|id|string|false|none|none|
|liked_by_user|boolean|false|none|none|
|likes|integer|false|none|none|
|links|[PhotoLinks](#schemaphotolinks)|false|none|none|
|location|[Location](#schemalocation)|false|none|none|
|tags|[object]|false|none|none|
|» title|string|false|none|none|
|updated_at|string(date-time)|false|none|none|
|urls|[PhotoUrls](#schemaphotourls)|false|none|none|
|user|[User](#schemauser)|false|none|none|
|width|integer|false|none|none|

<h2 id="tocS_PhotoStatistics">PhotoStatistics</h2>
<!-- backwards compatibility -->
<a id="schemaphotostatistics"></a>
<a id="schema_PhotoStatistics"></a>
<a id="tocSphotostatistics"></a>
<a id="tocsphotostatistics"></a>

```json
{
  "downloads": {
    "total": 0,
    "historical": {
      "change": 0,
      "resolution": "days",
      "quantity": 0,
      "values": [
        {
          "date": "2019-08-24",
          "value": 0
        }
      ]
    }
  },
  "id": "string",
  "likes": {
    "total": 0,
    "historical": {
      "change": 0,
      "resolution": "days",
      "quantity": 0,
      "values": [
        {
          "date": "2019-08-24",
          "value": 0
        }
      ]
    }
  },
  "views": {
    "total": 0,
    "historical": {
      "change": 0,
      "resolution": "days",
      "quantity": 0,
      "values": [
        {
          "date": "2019-08-24",
          "value": 0
        }
      ]
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|downloads|object|false|none|none|
|» total|integer|false|none|none|
|» historical|[PhotoHistoricalData](#schemaphotohistoricaldata)|false|none|none|
|id|string|false|none|none|
|likes|object|false|none|none|
|» total|integer|false|none|none|
|» historical|[PhotoHistoricalData](#schemaphotohistoricaldata)|false|none|none|
|views|object|false|none|none|
|» total|integer|false|none|none|
|» historical|[PhotoHistoricalData](#schemaphotohistoricaldata)|false|none|none|

<h2 id="tocS_PhotoHistoricalData">PhotoHistoricalData</h2>
<!-- backwards compatibility -->
<a id="schemaphotohistoricaldata"></a>
<a id="schema_PhotoHistoricalData"></a>
<a id="tocSphotohistoricaldata"></a>
<a id="tocsphotohistoricaldata"></a>

```json
{
  "change": 0,
  "resolution": "days",
  "quantity": 0,
  "values": [
    {
      "date": "2019-08-24",
      "value": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|change|integer|false|none|none|
|resolution|[StatResolution](#schemastatresolution)|false|none|none|
|quantity|integer|false|none|none|
|values|[object]|false|none|none|
|» date|string(date)|false|none|none|
|» value|integer|false|none|none|

<h2 id="tocS_PhotoSearchResults">PhotoSearchResults</h2>
<!-- backwards compatibility -->
<a id="schemaphotosearchresults"></a>
<a id="schema_PhotoSearchResults"></a>
<a id="tocSphotosearchresults"></a>
<a id="tocsphotosearchresults"></a>

```json
{
  "total": 0,
  "total_pages": 0,
  "results": [
    {
      "blur_hash": "string",
      "color": "string",
      "created_at": "2019-08-24T14:15:22Z",
      "current_user_collections": [
        {
          "cover_photo": {},
          "description": "string",
          "featured": true,
          "id": 0,
          "last_collected_at": "2019-08-24T14:15:22Z",
          "links": {
            "html": "string",
            "photos": "string",
            "related": "string",
            "self": "string"
          },
          "private": true,
          "published_at": "2019-08-24T14:15:22Z",
          "share_key": "string",
          "title": "string",
          "total_photos": true,
          "updated_at": "2019-08-24T14:15:22Z",
          "user": {
            "badge": {
              "link": "string",
              "primary": true,
              "slug": "string",
              "title": "string"
            },
            "bio": "string",
            "downloads": 0,
            "first_name": "string",
            "followed_by_user": true,
            "followers_count": 0,
            "following_count": 0,
            "id": "string",
            "instagram_username": "string",
            "last_name": "string",
            "links": {
              "html": "string",
              "likes": "string",
              "photos": "string",
              "portfolio": "string",
              "self": "string"
            },
            "location": "string",
            "name": "string",
            "portfolio_url": "string",
            "profile_image": {
              "small": "string",
              "medium": "string",
              "large": "string"
            },
            "total_collections": 0,
            "total_likes": 0,
            "total_photos": 0,
            "twitter_username": "string",
            "updated_at": "2019-08-24T14:15:22Z",
            "username": "string"
          }
        }
      ],
      "description": "string",
      "downloads": 0,
      "exif": {
        "make": "string",
        "model": "string",
        "exposure_time": "string",
        "aperture": 0,
        "focal_length": 0,
        "iso": 0
      },
      "height": 0,
      "id": "string",
      "liked_by_user": true,
      "likes": 0,
      "links": {
        "download": "string",
        "download_location": "string",
        "html": "string",
        "self": "string"
      },
      "location": {
        "city": "string",
        "country": "string",
        "name": "string",
        "position": {
          "latitude": 0,
          "longitude": 0
        }
      },
      "tags": [
        {
          "title": "string"
        }
      ],
      "updated_at": "2019-08-24T14:15:22Z",
      "urls": {
        "raw": "string",
        "full": "string",
        "regular": "string",
        "small": "string",
        "thumb": "string"
      },
      "user": {
        "badge": {
          "link": "string",
          "primary": true,
          "slug": "string",
          "title": "string"
        },
        "bio": "string",
        "downloads": 0,
        "first_name": "string",
        "followed_by_user": true,
        "followers_count": 0,
        "following_count": 0,
        "id": "string",
        "instagram_username": "string",
        "last_name": "string",
        "links": {
          "html": "string",
          "likes": "string",
          "photos": "string",
          "portfolio": "string",
          "self": "string"
        },
        "location": "string",
        "name": "string",
        "portfolio_url": "string",
        "profile_image": {
          "small": "string",
          "medium": "string",
          "large": "string"
        },
        "total_collections": 0,
        "total_likes": 0,
        "total_photos": 0,
        "twitter_username": "string",
        "updated_at": "2019-08-24T14:15:22Z",
        "username": "string"
      },
      "width": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|total|integer|false|none|none|
|total_pages|integer|false|none|none|
|results|[[Photo](#schemaphoto)]|false|none|none|

<h2 id="tocS_User">User</h2>
<!-- backwards compatibility -->
<a id="schemauser"></a>
<a id="schema_User"></a>
<a id="tocSuser"></a>
<a id="tocsuser"></a>

```json
{
  "badge": {
    "link": "string",
    "primary": true,
    "slug": "string",
    "title": "string"
  },
  "bio": "string",
  "downloads": 0,
  "first_name": "string",
  "followed_by_user": true,
  "followers_count": 0,
  "following_count": 0,
  "id": "string",
  "instagram_username": "string",
  "last_name": "string",
  "links": {
    "html": "string",
    "likes": "string",
    "photos": "string",
    "portfolio": "string",
    "self": "string"
  },
  "location": "string",
  "name": "string",
  "portfolio_url": "string",
  "profile_image": {
    "small": "string",
    "medium": "string",
    "large": "string"
  },
  "total_collections": 0,
  "total_likes": 0,
  "total_photos": 0,
  "twitter_username": "string",
  "updated_at": "2019-08-24T14:15:22Z",
  "username": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|badge|[Badge](#schemabadge)|false|none|none|
|bio|string|false|none|none|
|downloads|integer|false|none|none|
|first_name|string|false|none|none|
|followed_by_user|boolean|false|none|none|
|followers_count|integer|false|none|none|
|following_count|integer|false|none|none|
|id|string|false|none|none|
|instagram_username|string|false|none|none|
|last_name|string|false|none|none|
|links|[UserLinks](#schemauserlinks)|false|none|none|
|location|string|false|none|none|
|name|string|false|none|none|
|portfolio_url|string|false|none|none|
|profile_image|[ProfileImage](#schemaprofileimage)|false|none|none|
|total_collections|integer|false|none|none|
|total_likes|integer|false|none|none|
|total_photos|integer|false|none|none|
|twitter_username|string|false|none|none|
|updated_at|string(date-time)|false|none|none|
|username|string|false|none|none|

<h2 id="tocS_UserStatistics">UserStatistics</h2>
<!-- backwards compatibility -->
<a id="schemauserstatistics"></a>
<a id="schema_UserStatistics"></a>
<a id="tocSuserstatistics"></a>
<a id="tocsuserstatistics"></a>

```json
{
  "downloads": {
    "total": 0,
    "historical": {
      "change": 0,
      "average": 0,
      "resolution": "days",
      "quantity": 0,
      "values": [
        {
          "date": "2019-08-24",
          "value": 0
        }
      ]
    }
  },
  "likes": {
    "total": 0,
    "historical": {
      "change": 0,
      "average": 0,
      "resolution": "days",
      "quantity": 0,
      "values": [
        {
          "date": "2019-08-24",
          "value": 0
        }
      ]
    }
  },
  "username": "string",
  "views": {
    "total": 0,
    "historical": {
      "change": 0,
      "average": 0,
      "resolution": "days",
      "quantity": 0,
      "values": [
        {
          "date": "2019-08-24",
          "value": 0
        }
      ]
    }
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|downloads|object|false|none|none|
|» total|integer|false|none|none|
|» historical|[UserHistoricalData](#schemauserhistoricaldata)|false|none|none|
|likes|object|false|none|none|
|» total|integer|false|none|none|
|» historical|[UserHistoricalData](#schemauserhistoricaldata)|false|none|none|
|username|string|false|none|none|
|views|object|false|none|none|
|» total|integer|false|none|none|
|» historical|[UserHistoricalData](#schemauserhistoricaldata)|false|none|none|

<h2 id="tocS_UserHistoricalData">UserHistoricalData</h2>
<!-- backwards compatibility -->
<a id="schemauserhistoricaldata"></a>
<a id="schema_UserHistoricalData"></a>
<a id="tocSuserhistoricaldata"></a>
<a id="tocsuserhistoricaldata"></a>

```json
{
  "change": 0,
  "average": 0,
  "resolution": "days",
  "quantity": 0,
  "values": [
    {
      "date": "2019-08-24",
      "value": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|change|integer|false|none|none|
|average|integer|false|none|none|
|resolution|[StatResolution](#schemastatresolution)|false|none|none|
|quantity|integer|false|none|none|
|values|[object]|false|none|none|
|» date|string(date)|false|none|none|
|» value|integer|false|none|none|

<h2 id="tocS_UserSearchResults">UserSearchResults</h2>
<!-- backwards compatibility -->
<a id="schemausersearchresults"></a>
<a id="schema_UserSearchResults"></a>
<a id="tocSusersearchresults"></a>
<a id="tocsusersearchresults"></a>

```json
{
  "total": 0,
  "total_pages": 0,
  "results": [
    {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|total|integer|false|none|none|
|total_pages|integer|false|none|none|
|results|[[User](#schemauser)]|false|none|none|

<h2 id="tocS_ProfileImage">ProfileImage</h2>
<!-- backwards compatibility -->
<a id="schemaprofileimage"></a>
<a id="schema_ProfileImage"></a>
<a id="tocSprofileimage"></a>
<a id="tocsprofileimage"></a>

```json
{
  "small": "string",
  "medium": "string",
  "large": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|small|string|false|none|none|
|medium|string|false|none|none|
|large|string|false|none|none|

<h2 id="tocS_UserLinks">UserLinks</h2>
<!-- backwards compatibility -->
<a id="schemauserlinks"></a>
<a id="schema_UserLinks"></a>
<a id="tocSuserlinks"></a>
<a id="tocsuserlinks"></a>

```json
{
  "html": "string",
  "likes": "string",
  "photos": "string",
  "portfolio": "string",
  "self": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|html|string|false|none|none|
|likes|string|false|none|none|
|photos|string|false|none|none|
|portfolio|string|false|none|none|
|self|string|false|none|none|

<h2 id="tocS_PhotoUrls">PhotoUrls</h2>
<!-- backwards compatibility -->
<a id="schemaphotourls"></a>
<a id="schema_PhotoUrls"></a>
<a id="tocSphotourls"></a>
<a id="tocsphotourls"></a>

```json
{
  "raw": "string",
  "full": "string",
  "regular": "string",
  "small": "string",
  "thumb": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|raw|string|false|none|none|
|full|string|false|none|none|
|regular|string|false|none|none|
|small|string|false|none|none|
|thumb|string|false|none|none|

<h2 id="tocS_PhotoLinks">PhotoLinks</h2>
<!-- backwards compatibility -->
<a id="schemaphotolinks"></a>
<a id="schema_PhotoLinks"></a>
<a id="tocSphotolinks"></a>
<a id="tocsphotolinks"></a>

```json
{
  "download": "string",
  "download_location": "string",
  "html": "string",
  "self": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|download|string|false|none|none|
|download_location|string|false|none|none|
|html|string|false|none|none|
|self|string|false|none|none|

<h2 id="tocS_ErrorResponse">ErrorResponse</h2>
<!-- backwards compatibility -->
<a id="schemaerrorresponse"></a>
<a id="schema_ErrorResponse"></a>
<a id="tocSerrorresponse"></a>
<a id="tocserrorresponse"></a>

```json
{
  "errors": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|errors|[string]|false|none|none|

<h2 id="tocS_PortfolioLink">PortfolioLink</h2>
<!-- backwards compatibility -->
<a id="schemaportfoliolink"></a>
<a id="schema_PortfolioLink"></a>
<a id="tocSportfoliolink"></a>
<a id="tocsportfoliolink"></a>

```json
{
  "url": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|url|string|false|none|none|

<h2 id="tocS_Exif">Exif</h2>
<!-- backwards compatibility -->
<a id="schemaexif"></a>
<a id="schema_Exif"></a>
<a id="tocSexif"></a>
<a id="tocsexif"></a>

```json
{
  "make": "string",
  "model": "string",
  "exposure_time": "string",
  "aperture": 0,
  "focal_length": 0,
  "iso": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|make|string|false|none|none|
|model|string|false|none|none|
|exposure_time|string|false|none|none|
|aperture|number(double)|false|none|none|
|focal_length|number(double)|false|none|none|
|iso|integer|false|none|none|

<h2 id="tocS_Location">Location</h2>
<!-- backwards compatibility -->
<a id="schemalocation"></a>
<a id="schema_Location"></a>
<a id="tocSlocation"></a>
<a id="tocslocation"></a>

```json
{
  "city": "string",
  "country": "string",
  "name": "string",
  "position": {
    "latitude": 0,
    "longitude": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|city|string|false|none|none|
|country|string|false|none|none|
|name|string|false|none|none|
|position|object|false|none|none|
|» latitude|number(double)|false|none|none|
|» longitude|number(double)|false|none|none|

<h2 id="tocS_OperationResponse">OperationResponse</h2>
<!-- backwards compatibility -->
<a id="schemaoperationresponse"></a>
<a id="schema_OperationResponse"></a>
<a id="tocSoperationresponse"></a>
<a id="tocsoperationresponse"></a>

```json
{
  "photo": {
    "blur_hash": "string",
    "color": "string",
    "created_at": "2019-08-24T14:15:22Z",
    "current_user_collections": [
      {
        "cover_photo": {},
        "description": "string",
        "featured": true,
        "id": 0,
        "last_collected_at": "2019-08-24T14:15:22Z",
        "links": {
          "html": "string",
          "photos": "string",
          "related": "string",
          "self": "string"
        },
        "private": true,
        "published_at": "2019-08-24T14:15:22Z",
        "share_key": "string",
        "title": "string",
        "total_photos": true,
        "updated_at": "2019-08-24T14:15:22Z",
        "user": {
          "badge": {
            "link": "string",
            "primary": true,
            "slug": "string",
            "title": "string"
          },
          "bio": "string",
          "downloads": 0,
          "first_name": "string",
          "followed_by_user": true,
          "followers_count": 0,
          "following_count": 0,
          "id": "string",
          "instagram_username": "string",
          "last_name": "string",
          "links": {
            "html": "string",
            "likes": "string",
            "photos": "string",
            "portfolio": "string",
            "self": "string"
          },
          "location": "string",
          "name": "string",
          "portfolio_url": "string",
          "profile_image": {
            "small": "string",
            "medium": "string",
            "large": "string"
          },
          "total_collections": 0,
          "total_likes": 0,
          "total_photos": 0,
          "twitter_username": "string",
          "updated_at": "2019-08-24T14:15:22Z",
          "username": "string"
        }
      }
    ],
    "description": "string",
    "downloads": 0,
    "exif": {
      "make": "string",
      "model": "string",
      "exposure_time": "string",
      "aperture": 0,
      "focal_length": 0,
      "iso": 0
    },
    "height": 0,
    "id": "string",
    "liked_by_user": true,
    "likes": 0,
    "links": {
      "download": "string",
      "download_location": "string",
      "html": "string",
      "self": "string"
    },
    "location": {
      "city": "string",
      "country": "string",
      "name": "string",
      "position": {
        "latitude": 0,
        "longitude": 0
      }
    },
    "tags": [
      {
        "title": "string"
      }
    ],
    "updated_at": "2019-08-24T14:15:22Z",
    "urls": {
      "raw": "string",
      "full": "string",
      "regular": "string",
      "small": "string",
      "thumb": "string"
    },
    "user": {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    },
    "width": 0
  },
  "collection": {
    "cover_photo": {
      "blur_hash": "string",
      "color": "string",
      "created_at": "2019-08-24T14:15:22Z",
      "current_user_collections": [
        {}
      ],
      "description": "string",
      "downloads": 0,
      "exif": {
        "make": "string",
        "model": "string",
        "exposure_time": "string",
        "aperture": 0,
        "focal_length": 0,
        "iso": 0
      },
      "height": 0,
      "id": "string",
      "liked_by_user": true,
      "likes": 0,
      "links": {
        "download": "string",
        "download_location": "string",
        "html": "string",
        "self": "string"
      },
      "location": {
        "city": "string",
        "country": "string",
        "name": "string",
        "position": {
          "latitude": 0,
          "longitude": 0
        }
      },
      "tags": [
        {
          "title": "string"
        }
      ],
      "updated_at": "2019-08-24T14:15:22Z",
      "urls": {
        "raw": "string",
        "full": "string",
        "regular": "string",
        "small": "string",
        "thumb": "string"
      },
      "user": {
        "badge": {
          "link": "string",
          "primary": true,
          "slug": "string",
          "title": "string"
        },
        "bio": "string",
        "downloads": 0,
        "first_name": "string",
        "followed_by_user": true,
        "followers_count": 0,
        "following_count": 0,
        "id": "string",
        "instagram_username": "string",
        "last_name": "string",
        "links": {
          "html": "string",
          "likes": "string",
          "photos": "string",
          "portfolio": "string",
          "self": "string"
        },
        "location": "string",
        "name": "string",
        "portfolio_url": "string",
        "profile_image": {
          "small": "string",
          "medium": "string",
          "large": "string"
        },
        "total_collections": 0,
        "total_likes": 0,
        "total_photos": 0,
        "twitter_username": "string",
        "updated_at": "2019-08-24T14:15:22Z",
        "username": "string"
      },
      "width": 0
    },
    "description": "string",
    "featured": true,
    "id": 0,
    "last_collected_at": "2019-08-24T14:15:22Z",
    "links": {
      "html": "string",
      "photos": "string",
      "related": "string",
      "self": "string"
    },
    "private": true,
    "published_at": "2019-08-24T14:15:22Z",
    "share_key": "string",
    "title": "string",
    "total_photos": true,
    "updated_at": "2019-08-24T14:15:22Z",
    "user": {
      "badge": {
        "link": "string",
        "primary": true,
        "slug": "string",
        "title": "string"
      },
      "bio": "string",
      "downloads": 0,
      "first_name": "string",
      "followed_by_user": true,
      "followers_count": 0,
      "following_count": 0,
      "id": "string",
      "instagram_username": "string",
      "last_name": "string",
      "links": {
        "html": "string",
        "likes": "string",
        "photos": "string",
        "portfolio": "string",
        "self": "string"
      },
      "location": "string",
      "name": "string",
      "portfolio_url": "string",
      "profile_image": {
        "small": "string",
        "medium": "string",
        "large": "string"
      },
      "total_collections": 0,
      "total_likes": 0,
      "total_photos": 0,
      "twitter_username": "string",
      "updated_at": "2019-08-24T14:15:22Z",
      "username": "string"
    }
  },
  "user": {
    "badge": {
      "link": "string",
      "primary": true,
      "slug": "string",
      "title": "string"
    },
    "bio": "string",
    "downloads": 0,
    "first_name": "string",
    "followed_by_user": true,
    "followers_count": 0,
    "following_count": 0,
    "id": "string",
    "instagram_username": "string",
    "last_name": "string",
    "links": {
      "html": "string",
      "likes": "string",
      "photos": "string",
      "portfolio": "string",
      "self": "string"
    },
    "location": "string",
    "name": "string",
    "portfolio_url": "string",
    "profile_image": {
      "small": "string",
      "medium": "string",
      "large": "string"
    },
    "total_collections": 0,
    "total_likes": 0,
    "total_photos": 0,
    "twitter_username": "string",
    "updated_at": "2019-08-24T14:15:22Z",
    "username": "string"
  },
  "created_at": "2019-08-24T14:15:22Z"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|photo|[Photo](#schemaphoto)|false|none|none|
|collection|[Collection](#schemacollection)|false|none|none|
|user|[User](#schemauser)|false|none|none|
|created_at|string(date-time)|false|none|none|

<h2 id="tocS_Color">Color</h2>
<!-- backwards compatibility -->
<a id="schemacolor"></a>
<a id="schema_Color"></a>
<a id="tocScolor"></a>
<a id="tocscolor"></a>

```json
"black_and_white"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|black_and_white|
|*anonymous*|black|
|*anonymous*|white|
|*anonymous*|yellow|
|*anonymous*|orange|
|*anonymous*|red|
|*anonymous*|purple|
|*anonymous*|magenta|
|*anonymous*|green|
|*anonymous*|teal|
|*anonymous*|blue|

<h2 id="tocS_OrderBy">OrderBy</h2>
<!-- backwards compatibility -->
<a id="schemaorderby"></a>
<a id="schema_OrderBy"></a>
<a id="tocSorderby"></a>
<a id="tocsorderby"></a>

```json
"latest"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|latest|
|*anonymous*|oldest|
|*anonymous*|popular|

<h2 id="tocS_Orientation">Orientation</h2>
<!-- backwards compatibility -->
<a id="schemaorientation"></a>
<a id="schema_Orientation"></a>
<a id="tocSorientation"></a>
<a id="tocsorientation"></a>

```json
"landscape"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|landscape|
|*anonymous*|portrait|
|*anonymous*|squarish|

<h2 id="tocS_ContentFilter">ContentFilter</h2>
<!-- backwards compatibility -->
<a id="schemacontentfilter"></a>
<a id="schema_ContentFilter"></a>
<a id="tocScontentfilter"></a>
<a id="tocscontentfilter"></a>

```json
"low"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|low|
|*anonymous*|high|

<h2 id="tocS_StatResolution">StatResolution</h2>
<!-- backwards compatibility -->
<a id="schemastatresolution"></a>
<a id="schema_StatResolution"></a>
<a id="tocSstatresolution"></a>
<a id="tocsstatresolution"></a>

```json
"days"

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|*anonymous*|days|

