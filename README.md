[![Build Status](https://travis-ci.com/telemark/minelev-elevmappa-api.svg?branch=master)](https://travis-ci.com/telemark/minelev-elevmappa-api)
[![js-standard-style](https://img.shields.io/badge/code%20style-standard-brightgreen.svg?style=flat)](https://github.com/feross/standard)

# minelev-elevmappa-api

Lambda for returning all your students

## API

All calls requires a valid bearer token from Azure

### ```GET /api/students```

Returns an array of students

```JavaScript
[
 {
    "firstName": "Helga",
    "middleName": null,
    "lastName": "Durk",
    "fullName": "Helga Durk",
    "personalIdNumber": "02059711111",
    "mobilePhone": "+4798888888",
    "mail": "helgad@hotmail.com",
    "userName": "0205helgdurk",
    "contactTeacher": false,
    "unitId": "BAMVS",
    "unitName": "Bamble vgs. avd. Grasmyr",
    "organizationNumber": "NO974568098",
    "mainGroupName": "BAMVS:3ST",
    "groups": [
      {
        "id": "BAMVS:3ST/151FSP5098",
        "description": "Spansk I+II",
        "unitId": "BAMVS",
        "unitName": "Bamble vgs. avd. Grasmyr",
        "organizationNumber": "NO974568098",
        "contactTeacher": false
      }
    ]
 },
 {
    "firstName": "Halgrim",
    "middleName": "",
    "lastName": "Durk",
    "fullName": "Halgrim Durk",
    "personalIdNumber": "02109911111",
    "mobilePhone": "+4741111111",
    "mail": "halgrimdurk@gmail.com",
    "userName": "0101durk",
    "contactTeacher": true,
    "unitId": "BAMVS",
    "unitName": "Bamble vgs. avd. Grasmyr",
    "organizationNumber": "NO974568098",
    "mainGroupName": "BAMVS:1ST",
    "groups": [
      {
        "id": "BAMVS:1ST/151FSP5091",
        "description": "Spansk I, 1. år",
        "unitId": "BAMVS",
        "unitName": "Bamble vgs. avd. Grasmyr",
        "organizationNumber": "NO974568098",
        "contactTeacher": true
      }
    ]
  }
]
```

### ```GET /api/students/:id```

Returns an object of given student with available documents

```JavaScript
{
  "firstName": "Helge Grim",
  "middleName": null,
  "lastName": "Grim",
  "fullName": "Helge Grim",
  "personalIdNumber": "02059711111",
  "mobilePhone": "+4798888888",
  "mail": "helgeg@hotmail.com",
  "userName": "0205helgeg",
  "contactTeacher": false,
  "unitId": "BAMVS",
  "unitName": "Bamble vgs. avd. Grasmyr",
  "organizationNumber": "NO974568098",
  "mainGroupName": "BAMVS:3ST",
  "groups": [
    {
      "id": "BAMVS:3ST/151FSP5098",
      "description": "Spansk I+II",
      "unitId": "BAMVS",
      "unitName": "Bamble vgs. avd. Grasmyr",
      "organizationNumber": "NO974568098",
      "contactTeacher": false
    }
  ],
  "documents": [
    {
      "id": "16/03875-1",
      "title": "Lullabies from the edge",
      "files": [
        {
          "from": "PPT",
          "to": "Bamble Videregående skole",
          "title": "Sakkyndig vurdering.pdf",
          "file": "1234"
        }
      ]
    },
    {
      "id": "16/03875-2",
      "title": "Salige reker",
      "files": [
        {
          "from": "PPT",
          "to": "Bamble Videregående skole",
          "title": "Sakkyndig vurdering.pdf",
          "file": "1234"
        }
      ]
    },
    {
      "id": "16/03875-3",
      "title": "It came from Søre Ål",
      "files": [
        {
          "from": "PPT",
          "to": "Bamble Videregående skole",
          "title": "Sakkyndig vurdering.pdf",
          "file": "1234"
        }
      ]
    }
  ]
}
```

## Setup

You'll need an azure tenant and a jwt and endpoint url for your Buddy service.

Environment

```
BUDDY_SERVICE_URL=https://buddy.service.io
BUDDY_JWT_SECRET=Louie Louie, oh no, I got to go Louie Louie, oh no, I got to go
MOA_TENANT_ID=your-azure-tenant
P360_WS_BASE_URL=http://siweb.domain.no:8088/SI.WS.Core/SIF/
P360_WS_USERNAME=domain/username
P360_WS_PASSWORD=password
PAPERTRAIL_HOST=example.papertrailapp.com
PAPERTRAIL_PORT=port
PAPERTRAIL_HOSTNAME=minelev-elevmappa
```

## Related

- [minelev-buddy](https://github.com/telemark/minelev-buddy) - Buddy service for MinElev

## License

[MIT](LICENSE)
