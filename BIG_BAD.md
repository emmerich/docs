# Description

## Get the hotel description

Use this operation to get the hotel description matching the session context.

### Request

| Path parameter | Type   |       Mandatory      | Description                       |
| -------------- | ------ | :------------------: | --------------------------------- |
| `sessionId`    | string | :white\_check\_mark: | Unique identifier of the session. |
| `hotelId`      | string | :white\_check\_mark: | Unique identifier of the hotel.   |

| Header parameter         | Type                                              | Mandatory | Description                                                          |
| ------------------------ | ------------------------------------------------- | :-------: | -------------------------------------------------------------------- |
| `X-AVP-Properties`       | string from [Properties](broken-reference)        |           | The properties required in the response separated with \| character. |
| `X-AVP-DescriptionType`  | string from [Description types](broken-reference) |           | Mime type of the descriptions separated with \| character.           |
| `X-AVP-PictureTemplates` | string from [Picture templates](broken-reference) |           | The picture templates separated with \| character.                   |

#### Properties

* `Information` : corresponds to descriptions of the hotel (room count, rating, summary...).
* `Contact` : corresponds to contact information of the hotel (emails, phones, websites...).
* `Location` : corresponds to location information of the hotel (city, country, GPS position...).
* `Booking` : corresponds to booking parameters of the hotel (children age, supported card types...).
* `Reception` : corresponds to reception information of the hotel (opening hours, check-in time...).
* `Services` : corresponds to service details of the hotel (amenities...).
* `CancelConditions` : corresponds to details regarding cancel conditions of the hotel.
* `Rooms` : list of room identifiers of the hotel.
* `Rates` : list of rate identifiers of the hotel.
* `Extras` : list of extra identifiers of the hotel.
* `Occupancies` : list of occupancy identifiers of the hotel.
* `OfferCodes` : corresponds to offer codes information of the hotel (code, description...).

#### Description types

* `text/html` (default)
* `text/plain`
* `text/x-markdown`

#### Picture templates

* `Small`&#x20;
* `Medium`&#x20;
* `Large`&#x20;
* `Original`&#x20;
* `Touch_Image_Extra`&#x20;
* `Touch_Image_Extra@2x`&#x20;
* `Touch_Image_Gallery`&#x20;
* `Touch_Image_Gallery@2x`&#x20;
* `Touch_Image_Hotel`&#x20;
* `Touch_Image_Hotel@2x`&#x20;
* `Touch_Image_Rate`&#x20;
* `Touch_Image_Rate@2x`&#x20;
* `Touch_Image_Room`&#x20;
* `Touch_Image_Room@2x`&#x20;
* `Touch_Image_RoomRate`&#x20;
* `Touch_Image_RoomRate@2x`&#x20;
* `Smart_Gallery_Preview`&#x20;
* `Smart_Image_Zoom`&#x20;
* `Smart_Package_Principal`&#x20;
* `Smart_Room_Principal`

`GET > https://api-be.availpro.com/v1/{sessionId}/description/hotels/{hotelId}`

### Response

```javascript
{
  "hotelId": 9454,
  "name": "Hôtel J&N",
  "information": {
    "roomCount": 35,
    "rating": 4,
    "accommodation": {
      "text": "Hotel",
      "value": "Hotel"
    },
    "summary": [
      {
        "text": "<p>Please come in, let Magic, Pleasure and Dreams greet you. The SEVEN HOTEL welcomes you to a totally innovative concept where emotions and delight will turn your nights with us into a fabulous story to tell.  \n<br />  \nThe magic starts as you pursue into the lobby where a versatile bar, changing setting, atmosphere and sound lets you check in and mingle at your own pace. Choose among the 28 Levitation rooms, bed floating like a feather and bathtub raised above the ground as if suspended in outer space, each one of them equipped with gadgets and designed to lift your spirits to cloud nine! Or maybe you will prefer one of the incredible suites. There are seven to choose from, each one is unique, surprising, astonishing; every single one suggests a mythical, sensual mood.  \n</p><p></p><p>  \n</p><p>  \nPrepare your stay: Simplify your arrival by booking now your breakfast, personalize your room to your taste ... For now discover all the services offered on the concierge of the Hotel Seven, click the following link: http: // seven.thehostcloud.co/page/3038?item  \n</p>",
        "value": "Html"
      }
    ],
    "pictures": [
      {
        "templates": [
          {
            "name": "Original",
            "url": "https://i.1pic.co/files/images/Original/8f40744c-3aa7-42c5-bba8-948dbff0e8a7"
          },
        ],
        "sortOrder": 1
      },
      {...}
    ]
  },
  "location": {
    "timeZone": "Europe/Paris",
    "addressLines": [
      "20 Rue Berthollet"
    ],
    "postalCode": "75005",
    "city": "Paris",
    "country": {
      "code": "FR",
      "name": "France"
    },
    "gpsPosition": {
      "latitude": 48.8390007019043,
      "longitude": 2.3455681800842285
    },
    "directions": [
      {
        "text": "<p>\nPUBLIC TRANSPORT\n<br />\nMetro: Censier Daubenton (line 7).\n<br />\nRapid Transport RER (nearby): Port Royal (line B).\n<br />\nBus: Port-Royal Berthollet (lines 21, 83, 91), Monge-Claude Bernard (line 27).\n<br />\nPUBLIC PARKING\n<br />\nParking Patriarches (4, rue du March&#233; des Patriarches – open 24H)\n<br />\nParispark 5&#232;me (15, rue Censier - open 24H)\n<br />\nACCESS FROM THE AIRPORTS\n<br />\n from Roissy - Charles de Gaulle (40 minutes drive)\n<br />\n from Orly (30 minutes drive)\n</p>\n",
        "value": "Html"
      }
    ]
  },
  "booking": {
    "adults": {
      "maxCount": 10,
      "minAge": 12,
      "maxAge": 2147483647
    },
    "children": {
      "maxCount": 10,
      "minAge": 3,
      "maxAge": 12
    },
    "infants": {
      "maxCount": 1,
      "minAge": 0,
      "maxAge": 3
    },
    "cardTypes": [
      "Visa",
      "MasterCard",
      "AmericanExpress",
      "DinersClub",
      "Jcb"
    ],
    "paymentMethods": {
      "supportedCardTypes": [
        "AmericanExpress",
        "DinersClub",
        "Jcb",
        "MasterCard",
        "Visa"
      ],
      "supportedPaymentMethods": []
    },
    "currencies": [
      "EUR"
    ],
    "defaultCurrency": "EUR"
  },
  "services": [
    {
      "category": {
        "text": "Main services",
        "value": "General"
      },
      "amenities": [
        {
          "text": "Local taxes to be paid on-site",
          "value": "LocalTaxNotIncluded"
        },
        {
          "text": "Wheelchair access",
          "value": "WheelchairAccess"
        },
        {
          "text": "Terrace",
          "value": "Terrace"
        },
        {
          "text": "Elevator",
          "value": "Elevator"
        },
        {
          "text": "Towels included",
          "value": "TowelIncluded"
        },
        {
          "text": "Air conditioning",
          "value": "AirConditioning"
        }
      ]
    },
    {
      "category": {
        "text": "Services",
        "value": "Services"
      },
      "amenities": [
        {
          "text": "Laundry service",
          "value": "Laundry"
        },
        {
          "text": "Free internet access",
          "value": "FreeInternetAccess"
        }
      ]
    },
    {
      "category": {
        "text": "Catering",
        "value": "Catering"
      },
      "amenities": [
        {
          "text": "Bar (no alcohol)",
          "value": "NoAlcoholBar"
        },
        {
          "text": "Bar (serving alcohol)",
          "value": "Bar"
        },
        {
          "text": "Nearby food shop",
          "value": "FoodStore"
        }
      ]
    },
    {
      "category": {
        "text": "Other facilities or services",
        "value": "Other"
      },
      "amenities": [
        {
          "text": "Safe",
          "value": "SafetyBox"
        }
      ]
    },
    {
      "category": {
        "text": "Custom",
        "value": "Custom"
      },
      "amenities": [
        {
          "text": "Laptop on demand",
          "value": "CustomService5"
        }
      ]
    }
  ],
  "reception": {
    "amenities": [
      {
        "text": "Reception open 24 hours a day",
        "value": "ReceptionAvailable24Hours"
      }
    ],
    "checkInTime": {
      "text": "16:00",
      "value": "16:00:00"
    },
    "checkOutTime": {
      "text": "12:00",
      "value": "12:00:00"
    },
    "openingHours": {
      "text": "",
      "value": {}
    }
  },
  "contact": {
    "managerName": "Jonathan Dedge",
    "emails": [
      "contact@hoteljnn.com"
    ],
    "phones": [
      "00 33 (0)1 43 31 47 52"
    ],
    "faxes": [
      "00 33 (0)1 43 36 41 40"
    ],
    "webSites": [
      "http://www.hoteljnn.com/"
    ]
  },
  "cancelConditions": {
    "planningCancelConditions": {
      "A": [],
      "B": []
    },
    "description": []
  },
  "roomIds": [
    25628,
    25629,
    25630,
    30020,
    95612,
    95613,
    95614,
    25637,
    25634,
    25635,
    25638,
    94973
  ],
  "rateIds": [
    28473,
    239428,
    239429,
    177169,
    242145,
    239424,
    239425,
    256917,
    278882,
    298915,
    298916
  ],
  "hotelExtraIds": [
    14360,
    15565,
    16373,
    16377,
    17634,
    22767,
    26980,
    27487,
    33961,
    39382,
    45560,
    45561
  ],
  "roomExtraIds": [
    28799,
    37168
  ],
  "occupancyIds": [],
  "offerCodes": [
    {
      "offerCodeId": "bd5c4ee8-be33-4e43-b0e3-167ec4245ebc",
      "code": "SAVE",
      "description": "SAVE",
      "showAllRates": false,
      "rateIds": [
        239424
      ],
      "discount": {
        "nominal": {
          "amount": 0.0,
          "currency": null
        },
        "percent": 0.0,
        "calculationMode": "None"
      }
    },
    {...}
  ],
  "salesTermsAndConditions": {}
}
```

| Property                  | Type                                           | Mandatory | Description                                                             |
| ------------------------- | ---------------------------------------------- | :-------: | ----------------------------------------------------------------------- |
| `hotelId`                 | string                                         |           | Unique identifier of the hotel.                                         |
| `name`                    | string                                         |           | Name of the hotel.                                                      |
| `information`             | [Information](broken-reference)                |           | Contains the hotel's information.                                       |
| `location`                | [Location](broken-reference)                   |           | Contains the information regarding the hotel's location.                |
| `booking`                 | [Booking](broken-reference)                    |           | Contains details regarding the booking properties of the hotel.         |
| `services`                | array of [Service](broken-reference)           |           | Contains the list of the hotel's services.                              |
| `reception`               | [Reception](broken-reference)                  |           | Contains details regarding the reception of the hotel.                  |
| `contact`                 | [Contact](broken-reference)                    |           | Contains details regarding contact information of the hotel.            |
| `cancelConditions`        | [Cancel conditions](broken-reference)          |           | Contains details regarding the cancel conditions of the hotel.          |
| `roomIds`                 | array of string                                |           | The room ids of the hotel.                                              |
| `rateIds`                 | array of string                                |           | The rate ids of the hotel.                                              |
| `hotelExtraIds`           | array of string                                |           | The extra ids of the hotel.                                             |
| `roomExtraIds`            | array of string                                |           | The room extra ids of the hotel.                                        |
| `occupancyIds`            | array of string                                |           | The occupancy ids of the hotel.                                         |
| `offerCodes`              | array of [Offer code](broken-reference)        |           | Contains details regarding the offer codes of the hotel.                |
| `salesTermsAndConditions` | [Sales terms and conditions](broken-reference) |           | Contains details regarding the sales terms and conditions of the hotel. |

#### Information

| Property        | Type                                 | Mandatory | Description                                                    |
| --------------- | ------------------------------------ | :-------: | -------------------------------------------------------------- |
| `roomCount`     | integer _int32_                      |           | The number of rooms of the hotel.                              |
| `rating`        | integer _int32_                      |           | The number of stars of the hotel.                              |
| `accommodation` | [Accommodation](broken-reference)    |           | Contains the information regarding the hotel's accommodations. |
| `summary`       | array of [Summary](broken-reference) |           | Contains the hotel's formatted summary.                        |
| `pictures`      | array of [Picture](broken-reference) |           | Contains information regarding the hotel's pictures.           |

#### Accommodation

| Property | Type   | Mandatory | Description                                                                                                               |
| -------- | ------ | --------- | ------------------------------------------------------------------------------------------------------------------------- |
| `text`   | string |           | The accommodation text.                                                                                                   |
| `value`  | string |           | The accommodation value. May contain `Apartment`, `GuestHouse`, `HotelRental`, `Hostel`, `Hotel`, `Residence` or `Villa`. |

#### Summary

| Property | Type   | Mandatory | Description                                                                   |
| -------- | ------ | --------- | ----------------------------------------------------------------------------- |
| `text`   | string |           | The hotel's formatted summary.                                                |
| `value`  | string |           | The mime type of the summary. May contain `Html`, `Markdown` or  `PlainText`. |

#### Picture

| Property    | Type                                  | Mandatory | Description                                                                                          |
| ----------- | ------------------------------------- | --------- | ---------------------------------------------------------------------------------------------------- |
| `templates` | array of [Template](broken-reference) |           | Contains information from picture templates requested by the [appropriate header](broken-reference). |
| `sortOrder` | integer _int32_                       |           | The display order of pictures on the D-Edge booking engine.                                          |

#### Template

| Property | Type   | Mandatory | Description          |
| -------- | ------ | --------- | -------------------- |
| `name`   | string |           | The template's name. |
| `url`    | string |           | The url's picture.   |

#### Location

| Property       | Type                                   | Mandatory | Description                                        |
| -------------- | -------------------------------------- | :-------: | -------------------------------------------------- |
| `timeZone`     | string                                 |           | The hotel's time zone.                             |
| `addressLines` | array of string                        |           | Contains the address lines of the hotel.           |
| `postalCode`   | string                                 |           | The hotel's postal code.                           |
| `city`         | string                                 |           | The hotel's city.                                  |
| `district`     | string                                 |           | The hotel's district.                              |
| `country`      | [Country](broken-reference)            |           | Contains the hotel's country information.          |
| `gpsPosition`  | [GPS position](broken-reference)       |           | Contains the hotel's GPS position information.     |
| `directions`   | array of [Direction](broken-reference) |           | Contains information about how to reach the hotel. |

#### Country

| Property | Type   | Mandatory | Description       |
| -------- | ------ | :-------: | ----------------- |
| `code`   | string |           | The country code. |
| `name`   | string |           | The country name. |

#### GPS position

| Property    | Type            | Mandatory | Description      |
| ----------- | --------------- | :-------: | ---------------- |
| `latitude`  | number _double_ |           | Latitude value.  |
| `longitude` | number _double_ |           | Longitude value. |

#### Direction

| Property | Type   | Mandatory | Description                                                                          |
| -------- | ------ | :-------: | ------------------------------------------------------------------------------------ |
| `text`   | string |           | The formatted text about how to reach the hotel.                                     |
| `value`  | string |           | The mime type of the direction text. May contain `Html`, `Markdown` or  `PlainText`. |

#### Booking

| Property          | Type                                | Mandatory | Description                                                                        |
| ----------------- | ----------------------------------- | :-------: | ---------------------------------------------------------------------------------- |
| `adults`          | [Adults](broken-reference)          |           | Contains details regarding the adults properties.                                  |
| `children`        | [Children](broken-reference)        |           | Contains details regarding the children properties.                                |
| `infants`         | [Infants](broken-reference)         |           | Contains details regarding the infants properties.                                 |
| `cardTypes`       | array of string                     |           | :warning:Deprecated, use the property [Payment methods](broken-reference) instead. |
| `paymentMethods`  | [Payment methods](broken-reference) |           | Contains information regarding the payment methods supported by the hotel.         |
| `currencies`      | array of string                     |           | Contains the currencies supported by the hotel.                                    |
| `defaultCurrency` | string                              |           | Default currency of the hotel.                                                     |

#### Adults

| Property   | Type            | Mandatory | Description                                         |
| ---------- | --------------- | :-------: | --------------------------------------------------- |
| `maxCount` | integer _int32_ |           | Maximum number of adults allowed for a reservation. |
| `minAge`   | integer _int32_ |           | Minimum age to be considered as an adult.           |
| `maxAge`   | integer _int32_ |           | Maximum age to be considered as an adult.           |

#### Children

| Property   | Type            | Mandatory | Description                                           |
| ---------- | --------------- | :-------: | ----------------------------------------------------- |
| `maxCount` | integer _int32_ |           | Maximum number of children allowed for a reservation. |
| `minAge`   | integer _int32_ |           | Minimum age to be considered as a child.              |
| `maxAge`   | integer _int32_ |           | Maximum age to be considered as a child.              |

#### Infants

| Property   | Type            | Mandatory | Description                                          |
| ---------- | --------------- | :-------: | ---------------------------------------------------- |
| `maxCount` | integer _int32_ |           | Maximum number of infants allowed for a reservation. |
| `minAge`   | integer _int32_ |           | Minimum age to be considered as a infant.            |
| `maxAge`   | integer _int32_ |           | Maximum age to be considered as a infant.            |

#### Payment methods

| Property                  | Type            | Mandatory | Description                                                                                                                                                                                                                              |
| ------------------------- | --------------- | :-------: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `supportedCardTypes`      | array of string |           | Contains the card types supported by the hotel. May contain `Undefined`, `Visa`, `MasterCard`, `AmericanExpress`, `DinersClub`, `Jcb`, `UnionPay`, `Tunion`, `Discover`, `RuPay`, `InterPayment`, `Maestro`, `Dankort`, `Mir` or `Uatp`. |
| `supportedPaymentMethods` | array of string |           | Contains the payment methods supported by the hotel. May contain `Paypal` or `IDeal`.                                                                                                                                                    |

#### Service

| Property    | Type                                 | Mandatory | Description                                        |
| ----------- | ------------------------------------ | :-------: | -------------------------------------------------- |
| `category`  | [Category](broken-reference)         |           | Contains details regarding the amenities category. |
| `amenities` | array of [Amenity](broken-reference) |           | Contains the list of the hotel's amenities.        |

#### Category

| Property | Type   | Mandatory | Description                                                                                                                                                        |
| -------- | ------ | --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `text`   | string |           | The text of the amenities category expressed in the culture defined in the current session.                                                                        |
| `value`  | string |           | The value of the amenities category. May contain `Payment`, `General`, `Comfort`, `Leisure`, `Communication`, `Tour`, `Custom`, `Catering`, `Services` or `Other`. |

#### Amenity

| Property | Type   | Mandatory | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| -------- | ------ | :-------: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `text`   | string |           | The amenity's name expressed in the culture defined in the current session.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `value`  | string |           | The amenity's value. May contain `MoneyExchange`, `ReceptionAvailable24Hours`, `LocalTaxNotIncluded`, `PetsWelcome`, `WheelchairAccess`, `MembershipCardRequired`, `MembershipCardSoldOnSite`, `Garden`, `Terrace`, `Elevator`, `CentralHeating`, `LinenIncluded`, `LinenAvailable`, `TowelIncluded`, `TowelAvailable`, `Laundry`, `BreakfastFacilities`, `MealFacilities`, `TakeAway`, `Cafeteria`, `Restaurant`, `NoAlcoholBar`, `BarbecueAvailable`, `Bar`, `FoodStore`, `AirConditioning`, `HotShower`, `BilliardRoom`, `TelevisionRoom`, `GamesRoom`, `Playground`, `ReadingRoom`, `BooksAvailable`, `NightClub`, `Excursions`, `Tennis`, `IndoorSwimmingPool`, `OutdoorSwimmingPool`, `Sauna`, `Jacuzzi`, `FitnessRoom`, `PosteRestante`, `MessageBoard`, `InternationalPhone`, `LocalPhone`, `Fax`, `InternetAccess`, `FreeInternetAccess`, `InternetCafe`, `LuggageRoom`, `SecureCarPark`, `TwoWheelerCarPark`, `CoachStationShuttle`, `TrainStationShuttle`, `AirportShuttle`, `BicycleRental`, `MotorbikeRental`, `CarRental`, `CustomService1`, `CustomService2`, `CustomService3`, `CustomService4`, `CustomService5` or `SafetyBox`. |

#### Reception

| Property       | Type                                 | Mandatory | Description                                     |
| -------------- | ------------------------------------ | --------- | ----------------------------------------------- |
| `amenities`    | array of [Amenity](broken-reference) |           | Contains the list of the reception's amenities. |
| `checkInTime`  | [Check-in time](broken-reference)    |           | Contains the hotel's check-in time.             |
| `checkOutTime` | [Check-out time](broken-reference)   |           | Contains the hotel's check-out time.            |
| `openingHours` | [Opening hours](broken-reference)    |           | Contains the hotel's opening hours.             |

#### Amenity

| Property | Type   | Mandatory | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| -------- | ------ | :-------: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `text`   | string |           | The amenity's name expressed in the culture defined in the current session.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| `value`  | string |           | The amenity's value. May contain `MoneyExchange`, `ReceptionAvailable24Hours`, `LocalTaxNotIncluded`, `PetsWelcome`, `WheelchairAccess`, `MembershipCardRequired`, `MembershipCardSoldOnSite`, `Garden`, `Terrace`, `Elevator`, `CentralHeating`, `LinenIncluded`, `LinenAvailable`, `TowelIncluded`, `TowelAvailable`, `Laundry`, `BreakfastFacilities`, `MealFacilities`, `TakeAway`, `Cafeteria`, `Restaurant`, `NoAlcoholBar`, `BarbecueAvailable`, `Bar`, `FoodStore`, `AirConditioning`, `HotShower`, `BilliardRoom`, `TelevisionRoom`, `GamesRoom`, `Playground`, `ReadingRoom`, `BooksAvailable`, `NightClub`, `Excursions`, `Tennis`, `IndoorSwimmingPool`, `OutdoorSwimmingPool`, `Sauna`, `Jacuzzi`, `FitnessRoom`, `PosteRestante`, `MessageBoard`, `InternationalPhone`, `LocalPhone`, `Fax`, `InternetAccess`, `FreeInternetAccess`, `InternetCafe`, `LuggageRoom`, `SecureCarPark`, `TwoWheelerCarPark`, `CoachStationShuttle`, `TrainStationShuttle`, `AirportShuttle`, `BicycleRental`, `MotorbikeRental`, `CarRental`, `CustomService1`, `CustomService2`, `CustomService3`, `CustomService4`, `CustomService5` or `SafetyBox`. |

#### Check-in time

| Property | Type              | Mandatory | Description                                                                |
| -------- | ----------------- | :-------: | -------------------------------------------------------------------------- |
| `text`   | string _datetime_ |           | The check-in time expressed in the culture defined in the current session. |
| `value`  | string _datetime_ |           | The check-in time expressed in hh:mm:ss.                                   |

#### Check-out time

| Property | Type              | Mandatory | Description                                                                 |
| -------- | ----------------- | :-------: | --------------------------------------------------------------------------- |
| `text`   | string _datetime_ |           | The check-out time expressed in the culture defined in the current session. |
| `value`  | string _datetime_ |           | The check-out time expressed in hh:mm:ss.                                   |

#### Opening hours

| Property | Type                      | Mandatory | Description                                                        |
| -------- | ------------------------- | :-------: | ------------------------------------------------------------------ |
| `text`   | string                    |           | The text displayed for opening hours on the D-Edge booking engine. |
| `value`  | [Value](broken-reference) |           | Contains informations regarding the opening and closure time.      |

#### Value

| Property      | Type              | Mandatory | Description                             |
| ------------- | ----------------- | :-------: | --------------------------------------- |
| `openingTime` | string _datetime_ |           | The opening time expressed in hh:mm:ss. |
| `closureTime` | string _datetime_ |           | The closure time expressed in hh:mm:ss. |

#### Contact

| Property      | Type            | Mandatory | Description                               |
| ------------- | --------------- | :-------: | ----------------------------------------- |
| `managerName` | string          |           | Contains the name of the hotel's manager. |
| `emails`      | array of string |           | Contains the email contacts of the hotel. |
| `phones`      | array of string |           | Contains the phone numbers of the hotel . |
| `faxes`       | array of string |           | Contains the fax numbers of the hotel .   |
| `webSites`    | array of string |           | Contains the website urls of the hotel.   |

#### Cancel conditions

| Property                   | Type                                           | Mandatory | Description                                                    |
| -------------------------- | ---------------------------------------------- | :-------: | -------------------------------------------------------------- |
| `planningCancelConditions` | [Planning cancel conditions](broken-reference) |           | Contains the rules applied to the hotel's planning.            |
| `description`              | [Description](broken-reference)                |           | Contains information about the cancel conditions of the hotel. |

#### Planning cancel conditions

| Property                  | Type                     | Mandatory | Description                                      |
| ------------------------- | ------------------------ | :-------: | ------------------------------------------------ |
| `{cancelConditionLetter}` | [Rule](broken-reference) |           | Contains a rule applied to the hotel's planning. |

#### Rule

| Property     | Type            | Mandatory | Description                                          |
| ------------ | --------------- | :-------: | ---------------------------------------------------- |
| `delay`      | integer _int32_ |           | The cancellation delay (x days before arrival).      |
| `nightCount` | integer _int32_ |           | The cancellation fees expressed in number of nights. |
| `nominal`    | number _double_ |           | The cancellation fees expressed as a fixed rate.     |
| `percent`    | string          |           | The cancellation fees expressed as a percentage.     |
| `hour`       | string          |           | The time of the cancellation delay.                  |

#### Description

| Property | Type   | Mandatory | Description                                                                            |
| -------- | ------ | :-------: | -------------------------------------------------------------------------------------- |
| `text`   | string |           | The formatted text about cancel conditions.                                            |
| `value`  | string |           | The mime type of the description text. May contain `Html`, `Markdown` or  `PlainText`. |

#### Offer code

| Property       | Type                         | Mandatory | Description                                                              |
| -------------- | ---------------------------- | :-------: | ------------------------------------------------------------------------ |
| `offerCodeId`  | string                       |           | Unique identifier of the offer code.                                     |
| `code`         | string                       |           | The code of the offer code.                                              |
| `description`  | string                       |           | The description expressed in the culture defined in the current session. |
| `showAllRates` | boolean                      |           | :warning: Deprecated.                                                    |
| `rateIds`      | array of string              |           | The rate ids linked to the offer code.                                   |
| `discount`     | [Discount](broken-reference) |           | The details regarding the discount applied.                              |

#### Discount

| Property          | Type                        | Mandatory | Description                                                                                                             |
| ----------------- | --------------------------- | :-------: | ----------------------------------------------------------------------------------------------------------------------- |
| `nominal`         | [Nominal](broken-reference) |           | If there has been a nominal discount, which means a reduction in absolute value, contains the nominal discount details. |
| `percent`         | string                      |           | If there has been a percentage discount, contains the percentage discount.                                              |
| `calculationMode` | string                      |           | The calculation mode applied. May contain `None`, `PercentageWithoutExtras`, `Percentage` or `Nominal`.                 |

#### Nominal

| Property   | Type            | Mandatory | Description                                       |
| ---------- | --------------- | :-------: | ------------------------------------------------- |
| `amount`   | number _double_ |           | The amount of the nominal discount.               |
| `currency` | string          |           | The ISO code of the currency matching the amount. |

#### Sales terms and conditions

| Property | Type   | Mandatory | Description                                                       |
| -------- | ------ | :-------: | ----------------------------------------------------------------- |
| `name`   | string |           | The name expressed in the culture defined in the current session. |
| `url`    | string |           | The url directing to custom, detailed sales terms conditions.     |

## Get the hotels descriptions

Use this operation to get the hotels descriptions matching the session context.

### Request

| Path parameter | Type   |       Mandatory      | Description                       |
| -------------- | ------ | :------------------: | --------------------------------- |
| `sessionId`    | string | :white\_check\_mark: | Unique identifier of the session. |

| Header parameter         | Type                                              | Mandatory | Description                                                          |
| ------------------------ | ------------------------------------------------- | :-------: | -------------------------------------------------------------------- |
| `X-AVP-Properties`       | string from [Properties](broken-reference)        |           | The properties required in the response separated with \| character. |
| `X-AVP-DescriptionType`  | string from [Description types](broken-reference) |           | Mime type of the descriptions separated with \| character.           |
| `X-AVP-PictureTemplates` | string from [Picture templates](broken-reference) |           | The picture templates separated with \| character.                   |

#### Properties

* `Information` : corresponds to descriptions of the hotels (room count, rating, summary...).
* `Contact` : corresponds to contact information of the hotels (emails, phones, websites...).
* `Location` : corresponds to location information of the hotels (city, country, GPS position...).
* `Booking` : corresponds to booking parameters of the hotels (children age, supported card types...).
* `Reception` : corresponds to reception information of the hotels (opening hours, check-in time...).
* `Services` : corresponds to service details of the hotels (amenities...).
* `CancelConditions` : corresponds to details regarding cancel conditions of the hotels.
* `Rooms` : list of room identifiers of the hotels.
* `Rates` : list of rate identifiers of the hotels.
* `Extras` : list of extra identifiers of the hotels.
* `Occupancies` : list of occupancy identifiers of the hotels.
* `OfferCodes` : corresponds to offer codes information of the hotels (code, description...).

#### Description types

* `text/html` (default)
* `text/plain`
* `text/x-markdown`

#### Picture templates

* `Small`&#x20;
* `Medium`&#x20;
* `Large`&#x20;
* `Original`&#x20;
* `Touch_Image_Extra`&#x20;
* `Touch_Image_Extra@2x`&#x20;
* `Touch_Image_Gallery`&#x20;
* `Touch_Image_Gallery@2x`&#x20;
* `Touch_Image_Hotel`&#x20;
* `Touch_Image_Hotel@2x`&#x20;
* `Touch_Image_Rate`&#x20;
* `Touch_Image_Rate@2x`&#x20;
* `Touch_Image_Room`&#x20;
* `Touch_Image_Room@2x`&#x20;
* `Touch_Image_RoomRate`&#x20;
* `Touch_Image_RoomRate@2x`&#x20;
* `Smart_Gallery_Preview`&#x20;
* `Smart_Image_Zoom`&#x20;
* `Smart_Package_Principal`&#x20;
* `Smart_Room_Principal`

`GET > https://api-be.availpro.com/v1/{sessionId}/description/hotels`

### Response

```javascript
{
  "hotels": [
    {
      "hotelId": 9454,
      "name": "Hôtel J&N",
      "information": {...},
      "location": {...},
      "booking": {...},
      "services": [...],
      "reception": {...},
      "cancelConditions": {...},
      "roomIds": [...],
      "rateIds": [...],
      "hotelExtraIds": [...],
      "roomExtraIds": [...],
      "occupancyIds": [...],
      "offerCodes": [...],
      "salesTermsAndConditions": {...},
    },
    {...}
  ]
}
```

| Property | Type                               | Mandatory | Description                       |
| -------- | ---------------------------------- | :-------: | --------------------------------- |
| `hotels` | array of [Hotel](broken-reference) |           | Contains the hotels' information. |

#### Hotel

Same structure as the [Hotel](broken-reference) object in [Get the hotel description](broken-reference) operation.

## Get the room description

{% hint style="info" %}
Room description could be searched only if a `selectedHotelId` has been specified in the session context.
{% endhint %}

Use this operation to get the room description matching the session context.

### Request

| Path parameter | Type   |       Mandatory      | Description                       |
| -------------- | ------ | :------------------: | --------------------------------- |
| `sessionId`    | string | :white\_check\_mark: | Unique identifier of the session. |
| `roomId`       | string | :white\_check\_mark: | Unique identifier of the room.    |

| Header parameter         | Type                                              | Mandatory | Description                                                          |
| ------------------------ | ------------------------------------------------- | :-------: | -------------------------------------------------------------------- |
| `X-AVP-Properties`       | string from [Properties](broken-reference)        |           | The properties required in the response separated with \| character. |
| `X-AVP-DescriptionType`  | string from [Description types](broken-reference) |           | Mime type of the descriptions separated with \| character.           |
| `X-AVP-PictureTemplates` | string from [Picture templates](broken-reference) |           | The picture templates separated with \| character.                   |

#### Properties

* `Information` : corresponds to descriptions of the room (bedding, surface area...).
* `Booking` : corresponds to booking parameters of the room (children age...).
* `Rates` : list of rate identifiers of the room.
* `Extras` : list of extra identifiers of the room.
* `Occupancies` : list of occupancy identifiers of the room.

#### Description types

* `text/html` (default)
* `text/plain`
* `text/x-markdown`

#### Picture templates

* `Small`&#x20;
* `Medium`&#x20;
* `Large`&#x20;
* `Original`&#x20;
* `Touch_Image_Extra`&#x20;
* `Touch_Image_Extra@2x`&#x20;
* `Touch_Image_Gallery`&#x20;
* `Touch_Image_Gallery@2x`&#x20;
* `Touch_Image_Hotel`&#x20;
* `Touch_Image_Hotel@2x`&#x20;
* `Touch_Image_Rate`&#x20;
* `Touch_Image_Rate@2x`&#x20;
* `Touch_Image_Room`&#x20;
* `Touch_Image_Room@2x`&#x20;
* `Touch_Image_RoomRate`&#x20;
* `Touch_Image_RoomRate@2x`&#x20;
* `Smart_Gallery_Preview`&#x20;
* `Smart_Image_Zoom`&#x20;
* `Smart_Package_Principal`&#x20;
* `Smart_Room_Principal`

`GET > https://api-be.availpro.com/v1/{sessionId}/description/rooms/{roomId}`

### Response

```javascript
{
  "roomId": 48454,
  "hotelId": 14188,
  "name": "J&N Room",
  "information": {
    "totalCount": 4,
    "type": {
      "text": "Double room",
      "value": "Double"
    },
    "category": {
      "value": "None"
    },
    "qualifier": {
      "value": "None"
    },
    "surfaceArea": {
      "text": "182.99 ft²",
      "value": 17.00
    },
    "bedding": {
      "beds": [
        {
          "type": {
            "text": "Single bed",
            "value": "Single"
          },
          "count": 2,
          "twoPersonConvertible": false
        },
        {
          "type": {
            "text": "Double bed",
            "value": "Double"
          },
          "count": 1,
          "twoPersonConvertible": false
        }
      ],
      "singleBedCount": 2,
      "doubleBedCount": 1,
      "sofaCount": 0
    },
    "summary": [
      {
        "text": "<p>\nDouble room - 2 people - 1 double bed OR 2 single beds\n<br />\nThe Cosmopolite room includes a bathroom, opening intothe night area.\n<br />\nIts sourish colours and unobstructed view of the Banque de France will provide you with a sensation of freedom.\n</p>\n",
        "value": "Html"
      },
      {
        "text": "Double room - 2 people - 1 double bed OR 2 single beds\nThe Cosmopolite room includes a bathroom, opening intothe night area.\nIts sourish colours and unobstructed view of the Banque de France will provide you with a sensation of freedom.",
        "value": "PlainText"
      }
    ],
    "pictures": [
      {
        "templates": [
          {
            "name": "Original",
            "url": "https://i.1pic.co/files/images/Availpro-BookingEngines-Preview/ba21906c-a593-4bd9-afbe-6e9f99eb372d"
          },
        ],
        "sortOrder": 1
      },
      {...}
    ]
    "displayedPersonCount": 2,
    "sortOrder": 4
  },
  "services": [
    {
      "category": {
        "text": "General",
        "value": "General"
      },
      "amenities": [
        {
          "text": "No smoking",
          "value": "NonSmoking"
        },
        {
          "text": "Air conditioning",
          "value": "AirConditioning"
        },
        {
          "text": "Safe",
          "value": "SafeBox"
        },
        {
          "text": "Telephone",
          "value": "Phone"
        }
      ]
    },
    {
      "category": {
        "text": "Bathroom",
        "value": "Bathroom"
      },
      "amenities": [
        {
          "text": "Hair dryer",
          "value": "HairDryer"
        },
        {
          "text": "Shower",
          "value": "Shower"
        }
      ]
    },
    {
      "category": {
        "text": "Hi-tech",
        "value": "Appliances"
      },
      "amenities": [
        {
          "text": "Flatscreen TV",
          "value": "FlatScreenTelevision"
        },
        {
          "text": "Themed TV channels",
          "value": "ThemedTelevisionChannels"
        },
        {
          "text": "Wireless Internet access",
          "value": "WirelessInternetAccess"
        }
      ]
    }
  ],
  "occupancies": [
    {
      "occupancyId": 0,
      "isDefault": true,
      "definition": {
        "text": "2 people",
        "value": {
          "isDetailed": false,
          "personCount": 2,
          "adultCount": 0,
          "childCount": 0,
          "infantCount": 0
        }
      }
    }
  ],
  "extraIds": [
    34473,
    30143
  ],
  "rateIds": [
    57152,
    57162,
    298840,
    298858,
    63060,
    230791,
    57432,
    58526,
    292072,
    292058,
  ]
}

          
```

| Property      | Type                                   | Mandatory | Description                                                 |
| ------------- | -------------------------------------- | :-------: | ----------------------------------------------------------- |
| `roomId`      | string                                 |           | Unique identifier of the room.                              |
| `hotelId`     | string                                 |           | Unique identifier of the hotel.                             |
| `name`        | string                                 |           | Name of the room.                                           |
| `information` | [Information](broken-reference)        |           | Contains information on the room.                           |
| `services`    | array of [Service](broken-reference)   |           | Contains the list of the room's services.                   |
| `occupancies` | array of [Occupancy](broken-reference) |           | Contains information regarding the occupancies of the room. |
| `extraIds`    | array of string                        |           | The extra ids of the room.                                  |
| `rateIds`     | array of string                        |           | The rate ids of the room.                                   |

#### Information

| Property               | Type                                 | Mandatory | Description                                                          |
| ---------------------- | ------------------------------------ | :-------: | -------------------------------------------------------------------- |
| `totalCount`           | integer _int32_                      |           | The number of this type of room.                                     |
| `code`                 | string                               |           | Code of the room.                                                    |
| `type`                 | [Type](broken-reference)             |           | Contains details regarding the room's type.                          |
| `category`             | [Category](broken-reference)         |           | Contains details regarding the room's category.                      |
| `qualifier`            | [Qualifier](broken-reference)        |           | Contains details regarding the room's qualifier.                     |
| `surfaceArea`          | [Surface Area](broken-reference)     |           | Contains details regarding the room's surface area.                  |
| `bedding`              | [Bedding](broken-reference)          |           | Contains information regarding the room's bedding.                   |
| `summary`              | array of [Summary](broken-reference) |           | Contains the room's formatted summary.                               |
| `pictures`             | array of [Picture](broken-reference) |           | Contains information regarding the room's pictures.                  |
| `displayedPersonCount` | integer _int32_                      |           | The displayed person count of the room on the D-Edge booking engine. |
| `sortOrder`            | integer _int32_                      |           | The display order of the room on the D-Edge booking engine.          |

#### Type

| Property | Type   | Mandatory | Description                                                                                                                                                              |
| -------- | ------ | :-------: | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `text`   | string |           | The type expressed in the culture defined in the current session.                                                                                                        |
| `value`  | string |           | The room's type. May contain `None`, `Single`, `Double`, `Twin`, `Triple`, `Quadruple`, `FamilyRoom`, `JuniorSuite`, `Suite`, `Apartment`, `Studio`, `Villa` or `Other`. |

#### Category

| Property | Type   | Mandatory | Description                                                                                                                                                                                                             |
| -------- | ------ | :-------: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `text`   | string |           | The category expressed in the culture defined in the current session.                                                                                                                                                   |
| `value`  | string |           | The room's category. May contain `None`, `Small`, `Standard`, `Classical`, `Superior`, `Club`, `Deluxe`, `Princely`, `Majestic`, `Presidential`, `Imperial`, `Tradition`, `Prestige`, `Romantic`, `Comfort` or `Other`. |

#### Qualifier

| Property | Type   | Mandatory | Description                                                                                                                                                                                                                                                                        |
| -------- | ------ | :-------: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `text`   | string |           | The text regarding the name of the room qualifier displayed on the D-Edge booking engine expressed in the culture defined in the current session.                                                                                                                                  |
| `value`  | string |           | The qualifier value. May contain `None`, `WithBath`, `WithShower`, `Sight`, `SeaSight`, `OceanSight`, `GardenSight`, `SwimmingPoolSight`, `KingSizeBed`, `Jacuzzi`, `WithSundeck`, `WithBalcony`, `WithShowerAndBath`, `WithShowerOrBath`, `WithGarden` or `WithSundeckAndGarden`. |

#### Surface Area

| Property | Type            | Mandatory | Description                                                                                                                                |
| -------- | --------------- | :-------: | ------------------------------------------------------------------------------------------------------------------------------------------ |
| `text`   | string          |           | The text regarding the room's surface area displayed on the D-Edge booking engine expressed in the culture defined in the current session. |
| `value`  | number _double_ |           | The surface area value expressed in m².                                                                                                    |

#### Bedding

| Property         | Type                             | Mandatory | Description                                     |
| ---------------- | -------------------------------- | --------- | ----------------------------------------------- |
| `beds`           | array of [Bed](broken-reference) |           | Contains information regarding the room's beds. |
| `singleBedCount` | integer _int32_                  |           | Number of single bed(s).                        |
| `doubleBedCount` | integer _int32_                  |           | Number of double bed(s).                        |
| `sofaCount`      | integer _int32_                  |           | Number of sofa(s).                              |

#### Bed

| Property               | Type                     | Mandatory | Description                                             |
| ---------------------- | ------------------------ | :-------: | ------------------------------------------------------- |
| `type`                 | [Type](broken-reference) |           | Contains the details about the bed type of the room.    |
| `size`                 | [Size](broken-reference) |           | Contains the details about the bed size of the room.    |
| `count`                | integer _int32_          |           | The number of this type of bed.                         |
| `twoPersonConvertible` | boolean                  |           | If true, this type of bed is convertible for 2 persons. |

#### Type

| Property | Type   | Mandatory | Description                                                                                                                                               |
| -------- | ------ | :-------: | --------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `text`   | string |           | The text regarding the bed type displayed on the D-Edge booking engine expressed in the culture defined in the current session.                           |
| `value`  | string |           | The type of bed. May contain `SingleSofa`, `Single`, `SmallDouble`, `DoubleSofa`, `Double`, `QueenSize`, `KingSize`, `SuperKingSize` or `SingleKingSize`. |

#### Size

| Property |                           | Mandatory | Description                                                                                                                     |
| -------- | ------------------------- | :-------: | ------------------------------------------------------------------------------------------------------------------------------- |
| `text`   | string                    |           | The text regarding the bed size displayed on the D-Edge booking engine expressed in the culture defined in the current session. |
| `value`  | [Value](broken-reference) |           | Contains the details about the bed size of the room.                                                                            |

#### Value

| Property | Type            | Mandatory | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| -------- | --------------- | :-------: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`   | string          |           | The type of bed size for the room. May contain `Custom`, `Size80By190Cm`, `Size90By190Cm`, `Size90By200Cm`, `Size91By188Cm`, `Size91By191Cm`, `Size99By191Cm`, `Size100By190Cm`, `Size100By200Cm`, `Size120By190Cm`, `Size120By200Cm`, `Size135By200Cm`, `Size137By188Cm`, `Size137By191Cm`, `Size140By190Cm`, `Size140By195Cm`, `Size140By200Cm`, `Size150By200Cm`, `Size152By198Cm`, `Size153By203Cm`, `Size154By195Cm`, `Size160By190Cm`, `Size160By200Cm`, `Size167By203Cm`, `Size170By190Cm`, `Size170By195Cm`, `Size180By190Cm`, `Size180By200Cm`, `Size183By198Cm`, `Size183By203Cm`, `Size183By213Cm`, `Size194By195Cm`, `Size194By203Cm`, `Size194By205Cm`, `Size200By200Cm` or `Size203By203Cm`. |
| `width`  | integer _int32_ |           | The width of the bed expressed in cm if the type of bed size is `Custom`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| `length` | integer _int32_ |           | The length of the bed expressed in cm if the type of bed size is `Custom`.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |

#### Summary

| Property | Type   | Mandatory | Description                                                                   |
| -------- | ------ | :-------: | ----------------------------------------------------------------------------- |
| `text`   | string |           | The room's formatted summary.                                                 |
| `value`  | string |           | The mime type of the summary. May contain `Html`, `Markdown` or  `PlainText`. |

#### Picture

| Property    | Type                                  | Mandatory | Description                                                                                          |
| ----------- | ------------------------------------- | :-------: | ---------------------------------------------------------------------------------------------------- |
| `templates` | array of [Template](broken-reference) |           | Contains information from picture templates requested by the [appropriate header](broken-reference). |
| `sortOrder` | integer _int32_                       |           | The display order of the pictures on the D-Edge booking engine.                                      |

#### Template

| Property | Type   | Mandatory | Description          |
| -------- | ------ | :-------: | -------------------- |
| `name`   | string |           | The template's name. |
| `url`    | string |           | The url's picture.   |

#### Service

| Property    | Type                                 | Mandatory | Description                                           |
| ----------- | ------------------------------------ | :-------: | ----------------------------------------------------- |
| `category`  | [Category](broken-reference)         |           | Contains details regarding the category of amenities. |
| `amenities` | array of [Amenity](broken-reference) |           | Contains the list of the room's amenities.            |

#### Category

| Property | Type   | Mandatory | Description                                                                                 |
| -------- | ------ | --------- | ------------------------------------------------------------------------------------------- |
| `text`   | string |           | The text of the amenities category expressed in the culture defined in the current session. |
| `value`  | string |           | The value of the amenities category. May contain `General`, `Bathroom` or `Appliances`.     |

#### Amenity

| Property | Type   | Mandatory | Description                                                                                                                                                                                                                                                                                                                                                                                                                        |
| -------- | ------ | :-------: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `text`   | string |           | The amenity's name expressed in the culture defined in the current session.                                                                                                                                                                                                                                                                                                                                                        |
| `value`  | string |           | The amenity's value. May contain `NonSmoking`, `AirConditioning`, `MiniBar`, `Soundproof`, `SafeBox`, `IroningBoard`, `DisabledPersonAmenities`, `Terrace`, `Balcony`, `Loggia`, `Phone`, `Bathroom`, `HairDryer`, `Shower`, `Bathtub`, `Bidet`, `Television`, `FlatScreenTelevision`, `ThemedTelevisionChannels`, `DvdPlayer`, `InternetAccess`, `WirelessInternetAccess`, `Radio`, `AlarmClock`, `Computer`, `Printer` or `Fax`. |

#### Occupancy

| Property      | Type                           | Mandatory | Description                                               |
| ------------- | ------------------------------ | :-------: | --------------------------------------------------------- |
| `occupancyId` | string                         |           | Unique identifier of the occupancy.                       |
| `isDefault`   | boolean                        |           | If true, this occupancy is the default one for the room.  |
| `definition`  | [Definition](broken-reference) |           | Contains information regarding the occupancy of the room. |

#### Definition

| Property | Type                      | Mandatory | Description                                                                                                                                  |
| -------- | ------------------------- | :-------: | -------------------------------------------------------------------------------------------------------------------------------------------- |
| `text`   | string                    |           | The text regarding the occupancy of the room displayed on the D-Edge booking engine expressed in the culture defined in the current session. |
| `value`  | [Value](broken-reference) |           | Contains details regarding the occupancy of the room.                                                                                        |

#### Value

| Property      | Type            | Mandatory | Description                                                                                              |
| ------------- | --------------- | :-------: | -------------------------------------------------------------------------------------------------------- |
| `isDetailed`  | boolean         |           | If true, the occupancy is configured with the restrictions: `adultCount`, `childCount` or `infantCount`. |
| `personCount` | integer _int32_ |           | Number of persons configured for the occupancy.                                                          |
| `adultCount`  | integer _int32_ |           | Number of adults configured for the occupancy.                                                           |
| `childCount`  | integer _int32_ |           | Number of children configured for the occupancy.                                                         |
| `infantCount` | integer _int32_ |           | Number of infants configured for the occupancy.                                                          |

## Get the rooms descriptions

{% hint style="info" %}
Rooms descriptions could be searched only if a `selectedHotelId` has been specified in the session context.
{% endhint %}

Use this operation to get the rooms descriptions matching the session context.

### Request

| Path parameter | Type   |       Mandatory      | Description                       |
| -------------- | ------ | :------------------: | --------------------------------- |
| `sessionId`    | string | :white\_check\_mark: | Unique identifier of the session. |

| Header parameter         | Type                                              | Mandatory | Description                                                          |
| ------------------------ | ------------------------------------------------- | :-------: | -------------------------------------------------------------------- |
| `X-AVP-Properties`       | string from [Properties](broken-reference)        |           | The properties required in the response separated with \| character. |
| `X-AVP-DescriptionType`  | string from [Description types](broken-reference) |           | Mime type of the descriptions separated with \| character.           |
| `X-AVP-PictureTemplates` | string from [Picture templates](broken-reference) |           | The picture templates separated with \| character.                   |

#### Properties

* `Information` : corresponds to descriptions of the rooms (bedding, surface area...).
* `Booking` : corresponds to booking parameters of the rooms (children age...).
* `Rates` : list of rate identifiers of the rooms.
* `Extras` : list of extra identifiers of the rooms.
* `Occupancies` : list of occupancy identifiers of the rooms.

#### Description types

* `text/html` (default)
* `text/plain`
* `text/x-markdown`

#### Picture templates

* `Small`&#x20;
* `Medium`&#x20;
* `Large`&#x20;
* `Original`&#x20;
* `Touch_Image_Extra`&#x20;
* `Touch_Image_Extra@2x`&#x20;
* `Touch_Image_Gallery`&#x20;
* `Touch_Image_Gallery@2x`&#x20;
* `Touch_Image_Hotel`&#x20;
* `Touch_Image_Hotel@2x`&#x20;
* `Touch_Image_Rate`&#x20;
* `Touch_Image_Rate@2x`&#x20;
* `Touch_Image_Room`&#x20;
* `Touch_Image_Room@2x`&#x20;
* `Touch_Image_RoomRate`&#x20;
* `Touch_Image_RoomRate@2x`&#x20;
* `Smart_Gallery_Preview`&#x20;
* `Smart_Image_Zoom`&#x20;
* `Smart_Package_Principal`&#x20;
* `Smart_Room_Principal`

`GET > https://api-be.availpro.com/v1/{sessionId}/description/rooms`

### Response

```javascript
{
  "rooms": [
    {
      "roomId": 48452,
      "hotelId": 9454,
      "name": "Hôtel J&N",
      "information": {...},
      "services": [...],
      "occupancies": [...],
      "extraIds": [...],
      "rateIds": [...]
    },
    {...}
  ]
}
```

| Property | Type                              | Mandatory | Description                      |
| -------- | --------------------------------- | :-------: | -------------------------------- |
| `rooms`  | array of [Room](broken-reference) |           | Contains the rooms' information. |

#### Room

Same structure as the [Room](broken-reference) object in [Get the room description](broken-reference) operation.

## Get the rate description

{% hint style="info" %}
Rate description could be searched only if a `selectedHotelId` has been specified in the session context.
{% endhint %}

Use this operation to get the rate description matching the session context.

### Request

| Path parameter | Type   |       Mandatory      | Description                       |
| -------------- | ------ | :------------------: | --------------------------------- |
| `sessionId`    | string | :white\_check\_mark: | Unique identifier of the session. |
| `rateId`       | string | :white\_check\_mark: | Unique identifier of the rate.    |

| Header parameter         | Type                                              | Mandatory | Description                                                          |
| ------------------------ | ------------------------------------------------- | :-------: | -------------------------------------------------------------------- |
| `X-AVP-Properties`       | string from [Properties](broken-reference)        |           | The properties required in the response separated with \| character. |
| `X-AVP-DescriptionType`  | string from [Description types](broken-reference) |           | Mime type of the descriptions separated with \| character.           |
| `X-AVP-PictureTemplates` | string from [Picture templates](broken-reference) |           | The picture templates separated with \| character.                   |

#### Properties

* `Information` : corresponds to descriptions of the rate (summary pictures...).
* `Constraints` : corresponds to constraints of the rate.
* `Offers`: corresponds to offers of the rate.
* `SellingConditions` : corresponds to cancel conditions of the rate (deposit, booking fees...).
* `CancelConditions` : corresponds to cancel conditions of the rate (delay, night count...).
* `Rooms` : list of room identifiers of the rate.
* `Extras` : list of extra identifiers of the rate.
* `Occupancies` : list of occupancy identifiers of the rate.

#### Description types

* `text/html` (default)
* `text/plain`
* `text/x-markdown`

#### Picture templates

* `Small`&#x20;
* `Medium`&#x20;
* `Large`&#x20;
* `Original`&#x20;
* `Touch_Image_Extra`&#x20;
* `Touch_Image_Extra@2x`&#x20;
* `Touch_Image_Gallery`&#x20;
* `Touch_Image_Gallery@2x`&#x20;
* `Touch_Image_Hotel`&#x20;
* `Touch_Image_Hotel@2x`&#x20;
* `Touch_Image_Rate`&#x20;
* `Touch_Image_Rate@2x`&#x20;
* `Touch_Image_Room`&#x20;
* `Touch_Image_Room@2x`&#x20;
* `Touch_Image_RoomRate`&#x20;
* `Touch_Image_RoomRate@2x`&#x20;
* `Smart_Gallery_Preview`&#x20;
* `Smart_Image_Zoom`&#x20;
* `Smart_Package_Principal`&#x20;
* `Smart_Room_Principal`

`GET > https://api-be.availpro.com/v1/{sessionId}/description/rates/{rateId}`

### Response

```javascript
{
  "rateId": 298840,
  "hotelId": 14188,
  "code": "BARSEMI",
  "name": "Semi-Flexible rate",
  "currencyCode": "EUR",
  "information": {
    "type": {
      "value": "PublicPrice"
    },
    "qualifier": {
      "text": "Room only",
      "value": "RoomOnly"
    },
    "currency": "EUR",
    "summary": [],
    "pictures": [],
    "isPrivate": false,
    "sortOrder": 4
  },
  "gratuitounessPeriods": [],
  "stay": {
    "lastMinuteDayCount": 0,
    "earlyBookingDayCount": 0
  },
  "salePeriods": [],
  "sellingConditions": {
    "deposit": {
      "depositType": "PercentageWithoutExtras",
      "percent": 12.0
    },
    "useOnlinePayment": true,
    "bookingFees": {
      "percent": 0.0,
      "nominal": 0.0
    },
    "allowFullOnlinePayment": false,
    "allowCallOption": false,
    "paymentBalance": [
      {
        "text": "<p>\nLe balance of %amount% on the day of your arrival.\n<br />\nThe hotel does a pre authorisation of the amount of the first night.\n<br />\nThis pre autorisation will be debited in case of late cancellation or no show.\n</p>\n",
        "value": "Html"
      },
      {
        "text": "Le balance of %amount% on the day of your arrival.\nThe hotel does a pre authorisation of the amount of the first night.\nThis pre autorisation will be debited in case of late cancellation or no show.",
        "value": "PlainText"
      }
    ]
  },
  "cancelConditions": {
    "cancelConditions": [
      {
        "delay": 0,
        "nightCount": 1,
        "nominal": 0.0,
        "percent": 0.0,
        "hour": "00:00:00"
      },
      {
        "delay": 7,
        "nightCount": 1,
        "nominal": 0.0,
        "percent": 0.0,
        "hour": "00:00:00"
      },
      {
        "delay": 2147483647,
        "nightCount": 0,
        "nominal": 0.0,
        "percent": 0.0,
        "hour": "00:00:00"
      }
    ],
    "description": [],
    "usePlanningConditions": false,
    "isGuestModificationEnabled": true,
    "isModificationEnabled": true
  },
  "roomIds": [
    48452,
    48453,
    48454,
    48457,
    48456,
    48455
  ],
  "occupancyIds": [],
  "extraIds": [
    30143,
    34473
  ]
}
```

| Property               | Type                                              | Mandatory | Description                                                  |
| ---------------------- | ------------------------------------------------- | :-------: | ------------------------------------------------------------ |
| `rateId`               | string                                            |           | Unique identifier of the rate.                               |
| `hotelId`              | string                                            |           | Unique identifier of the hotel.                              |
| `code`                 | string                                            |           | Code of the rate.                                            |
| `name`                 | string                                            |           | Name of the rate.                                            |
| `currencyCode`         | string                                            |           | Currency code of the rate.                                   |
| `information`          | [Information](broken-reference)                   |           | Contains information on the rate.                            |
| `gratuitounessPeriods` | array of [Gratuitouness period](broken-reference) |           | Contains details regarding the rate's gratuitouness periods. |
| `stay`                 | [Stay](broken-reference)                          |           | Contains details regarding the rate's stay periods.          |
| `salePeriods`          | array of [Sale period](broken-reference)          |           | Contains details regarding the rate's sale periods.          |
| `sellingConditions`    | [Selling conditions](broken-reference)            |           | Contains details regarding the rate's selling conditions.    |
| `cancelConditions`     | array of [Cancel condition](broken-reference)     |           | Contains details regarding the rate's cancel conditions.     |
| `roomIds`              | array of string                                   |           | The room ids of the rate.                                    |
| `occupancyIds`         | array of string                                   |           | The occupancy ids of the rate.                               |
| `extraIds`             | array of string                                   |           | The extra ids of the rate.                                   |

#### Information

| Property    | Type                                 | Mandatory | Description                                                 |
| ----------- | ------------------------------------ | :-------: | ----------------------------------------------------------- |
| `type`      | [Type](broken-reference)             |           | Contains details regarding the rate's type.                 |
| `qualifier` | [Qualifier](broken-reference)        |           | Contains details regarding the rate's qualifier.            |
| `currency`  | string                               |           | Currency code of the rate.                                  |
| `summary`   | array of [Summary](broken-reference) |           | Contains the rate's formatted summary.                      |
| `pictures`  | array of [Picture](broken-reference) |           | Contains information regarding the rate's pictures.         |
| `isPrivate` | boolean                              |           | If true, this rate is a private rate.                       |
| `sortOrder` | integer _int32_                      |           | The display order of the rate on the D-Edge booking engine. |

#### Type

| Property | Type   | Mandatory | Description                                                                                                                                                                                                                       |
| -------- | ------ | :-------: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `text`   | string |           | The text regarding the rate type displayed on the D-Edge booking engine expressed in the culture defined in the current session.                                                                                                  |
| `value`  | string |           | The type of bed. May contain `PublicPrice`, `Promotional`, `ThreeNightPackage`, `BestAvailable`, `LastMinute`, `EarlyBooking`, `Seasonal`, `WeekEnd`, `FreeFourthNight`, `FreeFifthNight`, `Corporate` or `FacebookSpecialOffer`. |

#### Qualifier

| Property | Type   | Mandatory | Description                                                                                                                                                                                                                                                |
| -------- | ------ | :-------: | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `text`   | string |           | The text regarding the name of the rate qualifier displayed on the D-Edge booking engine expressed in the culture defined in the current session.                                                                                                          |
| `value`  | string |           | The qualifier value. May contain `RoomOnly`, `BreakfastIncluded`, `HalfBoard`, `FullBoard`, `AllInclusive`, `SelfCatering`, `Package`, `BreakfastIncludedPackage`, `HalfBoardPackage`, `FullBoardPackage`, `AllInclusivePackage` or `SelfCateringPackage`. |

#### Summary

| Property | Type   | Mandatory | Description                                                                   |
| -------- | ------ | :-------: | ----------------------------------------------------------------------------- |
| `text`   | string |           | The rate's formatted summary.                                                 |
| `value`  | string |           | The mime type of the summary. May contain `Html`, `Markdown` or  `PlainText`. |

#### Picture

| Property    | Type                                  | Mandatory | Description                                                                                          |
| ----------- | ------------------------------------- | :-------: | ---------------------------------------------------------------------------------------------------- |
| `templates` | array of [Template](broken-reference) |           | Contains information from picture templates requested by the [appropriate header](broken-reference). |
| `sortOrder` | integer _int32_                       |           | The display order of the pictures on the D-Edge booking engine.                                      |

#### Template

| Property | Type   | Mandatory | Description          |
| -------- | ------ | :-------: | -------------------- |
| `name`   | string |           | The template's name. |
| `url`    | string |           | The url's picture.   |

#### Gratuitouness period

| Property         | Type                       | Mandatory | Description                                                  |
| ---------------- | -------------------------- | :-------: | ------------------------------------------------------------ |
| `period`         | [Period](broken-reference) |           | Contains details regarding the rate's gratuitouness periods. |
| `paidNightCount` | integer _int32_            |           | The paid night count.                                        |
| `freeNightCount` | integer _int32_            |           | The free night count.                                        |

#### Period

| Property        | Type            | Mandatory | Description                                 |
| --------------- | --------------- | :-------: | ------------------------------------------- |
| `start`         | string          |           | The start date of the gratuitouness period. |
| `end`           | string          |           | The end date of the gratuitouness period.   |
| `isStartClosed` | boolean         |           | :warning: Internal use only.                |
| `isEndClosed`   | boolean         |           | :warning: Internal use only.                |
| `length`        | string          |           | :warning: Internal use only.                |
| `dayLength`     | integer _int32_ |           | The day length of the gratuitouness period. |
| `isEmpty`       | boolean         |           | :warning: Internal use only.                |

#### Stay

| Property               | Type                                | Mandatory | Description                                         |
| ---------------------- | ----------------------------------- | :-------: | --------------------------------------------------- |
| `lastMinuteDayCount`   | integer _int32_                     |           | The last minute day count.                          |
| `earlyBookingDayCount` | integer _int32_                     |           | The early booking day count.                        |
| `periods`              | array of [Period](broken-reference) |           | Contains details regarding the rate's stay periods. |

#### Period

| roperty      | Type                       | Mandatory | Description                                                                                                |
| ------------ | -------------------------- | :-------: | ---------------------------------------------------------------------------------------------------------- |
| `period`     | [Period](broken-reference) |           | Contains details regarding the rate's stay period.                                                         |
| `daysOfWeek` | string                     |           | May contain `None`, `Sunday`, `Monday`, `Tuesday`, `Wednesday`, `Thursday`, `Friday`, `Saturday` or `All`. |

#### Period

| Property        | Type            | Mandatory | Description                        |
| --------------- | --------------- | :-------: | ---------------------------------- |
| `start`         | string          |           | The start date of the stay period. |
| `end`           | string          |           | The end date of the stay period.   |
| `isStartClosed` | boolean         |           | :warning: Internal use only.       |
| `isEndClosed`   | boolean         |           | :warning: Internal use only.       |
| `length`        | string          |           | :warning: Internal use only.       |
| `dayLength`     | integer _int32_ |           | The day length of the stay period. |
| `isEmpty`       | boolean         |           | :warning: Internal use only.       |

#### Sale period

| Property     | Type                       | Mandatory | Description                                                                                                |
| ------------ | -------------------------- | :-------: | ---------------------------------------------------------------------------------------------------------- |
| `period`     | [Period](broken-reference) |           | Contains details regarding the rate's sale periods.                                                        |
| `daysOfWeek` | string                     |           | May contain `None`, `Sunday`, `Monday`, `Tuesday`, `Wednesday`, `Thursday`, `Friday`, `Saturday` or `All`. |

#### Period

| Property        | Type            | Mandatory | Description                        |
| --------------- | --------------- | :-------: | ---------------------------------- |
| `start`         | string          |           | The start date of the sale period. |
| `end`           | string          |           | The end date of the sale period.   |
| `isStartClosed` | boolean         |           | :warning: Internal use only.       |
| `isEndClosed`   | boolean         |           | :warning: Internal use only.       |
| `length`        | string          |           | :warning: Internal use only.       |
| `dayLength`     | integer _int32_ |           | The day length of the sale period. |
| `isEmpty`       | boolean         |           | :warning: Internal use only.       |

#### Selling conditions

| Property                 | Type                                         | Mandatory | Description                                                              |
| ------------------------ | -------------------------------------------- | :-------: | ------------------------------------------------------------------------ |
| `deposit`                | [Deposit](broken-reference)                  |           | Contains details regarding the required deposit of the rate.             |
| `useOnlinePayment`       | boolean                                      |           | If true, the deposit amount will be captured by a payment provider.      |
| `bookingFees`            | [Booking fees](broken-reference)             |           | Contains details regarding the booking fees applied to the rate.         |
| `allowFullOnlinePayment` | boolean                                      |           | If true, the full booking amount will be captured by a payment provider. |
| `allowCallOption`        | boolean                                      |           | If true, the rate can be booked with an option to be validated later.    |
| `paymentBalance`         | array of [Payment balance](broken-reference) |           | Contains details regarding the payment balance texts of the rate.        |

#### Deposit

| Property      | Type   | Mandatory | Description                                                                                                                                     |
| ------------- | ------ | --------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| `depositType` | string |           | The type of deposit. May contain `Nothing`, `CreditCardNumber`, `FirstNightWithoutExtras`, `PercentageWithoutExtras` or `PercentageWithExtras`. |
| `percent`     | string |           | The percentage value of the deposit if it has been configured like this.                                                                        |

#### Booking fees

| Property  | Type            | Mandatory | Description                                                                                |
| --------- | --------------- | :-------: | ------------------------------------------------------------------------------------------ |
| `percent` | string          |           | The percentage value of booking fees if they have been configured like this.               |
| `nominal` | number _double_ |           | The nominal value (absolute value) of booking fees if they have been configured like this. |

#### Payment balance

| Property | Type   | Mandatory | Description                                                                   |
| -------- | ------ | :-------: | ----------------------------------------------------------------------------- |
| `text`   | string |           | The rate's formatted payment balance text.                                    |
| `value`  | string |           | The mime type of the summary. May contain `Html`, `Markdown` or  `PlainText`. |

#### Cancel condition

| Property                     | Type                                          | Mandatory | Description                                                                                                                          |
| ---------------------------- | --------------------------------------------- | :-------: | ------------------------------------------------------------------------------------------------------------------------------------ |
| `cancelConditions`           | array of [Cancel condition](broken-reference) |           | Contains details regarding the rate's cancel conditions.                                                                             |
| `description`                | array of [Description](broken-reference)      |           | Contains details regarding the cancel condition descriptions of the rate.                                                            |
| `usePlanningConditions`      | boolean                                       |           | If true, correspond to the cancellation conditions defined at the planning level that apply and not those defined at the rate level. |
| `isGuestModificationEnabled` | boolean                                       |           | If true, guest information can be changed after booking.                                                                             |
| `isModificationEnabled`      | boolean                                       |           | If true, booking information can be changed after booking.                                                                           |

#### Cancel condition

| Property     | Type            | Mandatory | Description                                                                                        |
| ------------ | --------------- | --------- | -------------------------------------------------------------------------------------------------- |
| `delay`      | integer _int32_ |           | Number of days before arrival until which the cancellation condition applies.                      |
| `nightCount` | integer _int32_ |           | Cancellation fees expressed in number of nights.                                                   |
| `nominal`    | number _double_ |           | Cancellation fees expressed in nominal value.                                                      |
| `percent`    | string          |           | Cancellation fees expressed as a percentage.                                                       |
| `hour`       | string          |           | Deadline until which the cancellation condition applies. Otherwise, it is the following condition. |

#### Description

| Property | Type   | Mandatory | Description                                                                   |
| -------- | ------ | :-------: | ----------------------------------------------------------------------------- |
| `text`   | string |           | The rate's formatted cancel conditions text.                                  |
| `value`  | string |           | The mime type of the summary. May contain `Html`, `Markdown` or  `PlainText`. |

## Get the rates descriptions

{% hint style="info" %}
Rates descriptions could be searched only if a `selectedHotelId` has been specified in the session context.
{% endhint %}

Use this operation to get the rates descriptions matching the session context.

### Request

| Path parameter | Type   |       Mandatory      | Description                       |
| -------------- | ------ | :------------------: | --------------------------------- |
| `sessionId`    | string | :white\_check\_mark: | Unique identifier of the session. |

| Header parameter         | Type                                              | Mandatory | Description                                                          |
| ------------------------ | ------------------------------------------------- | :-------: | -------------------------------------------------------------------- |
| `X-AVP-Properties`       | string from [Properties](broken-reference)        |           | The properties required in the response separated with \| character. |
| `X-AVP-DescriptionType`  | string from [Description types](broken-reference) |           | Mime type of the descriptions separated with \| character.           |
| `X-AVP-PictureTemplates` | string from [Picture templates](broken-reference) |           | The picture templates separated with \| character.                   |

#### Properties

* `Information` : corresponds to descriptions of the rate (summary pictures...).
* `Constraints` : corresponds to constraints of the rate.
* `Offers`: corresponds to offers of the rate.
* `SellingConditions` : corresponds to cancel conditions of the rate (deposit, booking fees...).
* `CancelConditions` : corresponds to cancel conditions of the rate (delay, night count...).
* `Rooms` : list of room identifiers of the rate.
* `Extras` : list of extra identifiers of the rate.
* `Occupancies` : list of occupancy identifiers of the rate.

#### Description types

* `text/html` (default)
* `text/plain`
* `text/x-markdown`

#### Picture templates

* `Small`&#x20;
* `Medium`&#x20;
* `Large`&#x20;
* `Original`&#x20;
* `Touch_Image_Extra`&#x20;
* `Touch_Image_Extra@2x`&#x20;
* `Touch_Image_Gallery`&#x20;
* `Touch_Image_Gallery@2x`&#x20;
* `Touch_Image_Hotel`&#x20;
* `Touch_Image_Hotel@2x`&#x20;
* `Touch_Image_Rate`&#x20;
* `Touch_Image_Rate@2x`&#x20;
* `Touch_Image_Room`&#x20;
* `Touch_Image_Room@2x`&#x20;
* `Touch_Image_RoomRate`&#x20;
* `Touch_Image_RoomRate@2x`&#x20;
* `Smart_Gallery_Preview`&#x20;
* `Smart_Image_Zoom`&#x20;
* `Smart_Package_Principal`&#x20;
* `Smart_Room_Principal`

`GET > https://api-be.availpro.com/v1/{sessionId}/description/rates`

### Response

```javascript
{
  "rates": [
    {
      "rateId": 298840,
      "hotelId": 14188,
      "code": "BARSEMI",
      "name": "Semi-Flexible rate",
      "currencyCode": "EUR",
      "information": {...},
      "gratuitounessPeriods": [...],
      "stay": {...},
      "salePeriods": [...],
      "sellingConditions": {...},
      "cancelConditions": {...},
      "roomIds": {...},
      "occupancyIds": [...],
      "extraIds": [...]
    },
    {...}
  ]
}
```

| Property | Type                              | Mandatory | Description                      |
| -------- | --------------------------------- | :-------: | -------------------------------- |
| `rates`  | array of [Rate](broken-reference) |           | Contains the rates' information. |

#### Rate

Same structure as the [Rate](broken-reference) object in [Get the rate description](broken-reference) operation.

## Get the extra description

{% hint style="info" %}
Extra description could be searched only if a `selectedHotelId` has been specified in the session context.
{% endhint %}

Use this operation to get the extra description matching the session context.

### Request

| Path parameter | Type   |       Mandatory      | Description                       |
| -------------- | ------ | :------------------: | --------------------------------- |
| `sessionId`    | string | :white\_check\_mark: | Unique identifier of the session. |
| `extraId`      | string | :white\_check\_mark: | Unique identifier of the extra.   |

| Header parameter         | Type                                              | Mandatory | Description                                                          |
| ------------------------ | ------------------------------------------------- | :-------: | -------------------------------------------------------------------- |
| `X-AVP-Properties`       | string from [Properties](broken-reference)        |           | The properties required in the response separated with \| character. |
| `X-AVP-DescriptionType`  | string from [Description types](broken-reference) |           | Mime type of the descriptions separated with \| character.           |
| `X-AVP-PictureTemplates` | string from [Picture templates](broken-reference) |           | The picture templates separated with \| character.                   |

#### Properties

* `Information` : corresponds to descriptions of the extra (summary pictures, stock...).
* `Rooms` : list of room identifiers of the extra.
* `Rates` : list of rate identifiers of the extra.

#### Description types

* `text/html` (default)
* `text/plain`
* `text/x-markdown`

#### Picture templates

* `Small`&#x20;
* `Medium`&#x20;
* `Large`&#x20;
* `Original`&#x20;
* `Touch_Image_Extra`&#x20;
* `Touch_Image_Extra@2x`&#x20;
* `Touch_Image_Gallery`&#x20;
* `Touch_Image_Gallery@2x`&#x20;
* `Touch_Image_Hotel`&#x20;
* `Touch_Image_Hotel@2x`&#x20;
* `Touch_Image_Rate`&#x20;
* `Touch_Image_Rate@2x`&#x20;
* `Touch_Image_Room`&#x20;
* `Touch_Image_Room@2x`&#x20;
* `Touch_Image_RoomRate`&#x20;
* `Touch_Image_RoomRate@2x`&#x20;
* `Smart_Gallery_Preview`&#x20;
* `Smart_Image_Zoom`&#x20;
* `Smart_Package_Principal`&#x20;
* `Smart_Room_Principal`

`GET > https://api-be.availpro.com/v1/{sessionId}/description/extras/{extraId}`

### Response

```javascript
{
  "extraId": 31090,
  "name": "½ bottle of Champagne",
  "hotelId": 14188,
  "rateIds": [
    57152,
    57162,
    57351,
    57432,
    58525,
    58526,
    63060,
    294666,
    294682,
    294704
  ],
  "roomIds": [],
  "information": {
    "class": "Hotel",
    "type": {
      "value": "Undefined"
    },
    "gratuitousnessType": {
      "value": "None"
    },
    "stock": "Unlimited",
    "summary": [
      {
        "text": "<p>\nEnjoy 1/2 bottle of Champagne for your Parisian stay !\n</p>\n",
        "value": "Html"
      },
      {
        "text": "Enjoy 1/2 bottle of Champagne for your Parisian stay !",
        "value": "PlainText"
      }
    ],
    "pictures": [
      {
        "templates": [
          {
            "name": "Original",
            "url": "https://i.1pic.co/files/images/Availpro-BookingEngines-Preview/570b06ff-aa7b-4b3b-acf8-519ce2b8e0a3"
          },
          {...}
        ],
        "sortOrder": 1
      }
    ],
    "maximumQuantity": 20,
    "isMandatory": false,
    "isPreselected": false,
    "payOnline": false,
    "sortOrder": 12,
    "countingType": {
      "text": "per booking",
      "value": "Booking"
    },
    "occupancyDefinition": {}
  }
}
```

| Property      | Type            | Mandatory | Description                        |
| ------------- | --------------- | :-------: | ---------------------------------- |
| `extraId`     | string          |           | Unique identifier of the extra.    |
| `name`        | string          |           | Name of the extra.                 |
| `hotelId`     | string          |           | Unique identifier of the hotel.    |
| `rateIds`     | array of string |           | The rate ids of the extra.         |
| `roomIds`     | array of string |           | The room ids of the extra.         |
| `information` | Information     |           | Contains information on the extra. |

#### Information

| Property              | Type                                     | Mandatory | Description                                                                               |
| --------------------- | ---------------------------------------- | :-------: | ----------------------------------------------------------------------------------------- |
| `class`               | string                                   |           | The class of the extra. May contain `Room` or `Hotel`.                                    |
| `type`                | [Type](broken-reference)                 |           | Contains details regarding the extra's type.                                              |
| `gratuitousnessType`  | [Gratuitousness type](broken-reference)  |           | Contains details regarding the extra's gratuitousness type.                               |
| `stock`               | string                                   |           | The extra's stock type. May contain `Uncountable`, `Unlimited`, `Dependent` or `Limited`. |
| `summary`             | array of [Summary](broken-reference)     |           | Contains the extra's formatted summary.                                                   |
| `pictures`            | array of [Picture](broken-reference)     |           | Contains information regarding the extra's pictures.                                      |
| `maximumQuantity`     | integer _int32_                          |           | The maximum quantity of the extra bookable by reservation.                                |
| `isMandatory`         | boolean                                  |           | If true, the extra must be included in the booking.                                       |
| `isPreselected`       | boolean                                  |           | If true, the extra is preselected in the selection of extras during the reservation.      |
| `payOnline`           | boolean                                  |           | If true, the extra will be paid online.                                                   |
| `sortOrder`           | integer _int32_                          |           | The display order of the extra on the D-Edge booking engine.                              |
| `countingType`        | [Counting type](broken-reference)        |           | Contains details regarding the extra's counting type.                                     |
| `occupancyDefinition` | [Occupancy definition](broken-reference) |           | Contains details regarding the extra's occupancy definition.                              |

#### Type

| Property | Type   | Mandatory | Description                                                                                                                                                                                                                                                     |
| -------- | ------ | :-------: | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `text`   | string |           | The type expressed in the culture defined in the current session.                                                                                                                                                                                               |
| `value`  | string |           | The extra's type. May contain `Undefined`, `StayTax`, `OtherTax`, `Breakfast`, `AdditionalInfant`, `AdditionalChild`, `AdditionalAdult`, `Coffin`, `AdditionalBed`, `Pet`, `Parking`, `Excursion`, `Entertainment`, `InternetAccess`, `Transfer` or `Cleaning`. |

#### Gratuitousness type

| Property | Type   | Mandatory | Description                                                                           |
| -------- | ------ | :-------: | ------------------------------------------------------------------------------------- |
| `text`   | string |           | The gratuitousness type expressed in the culture defined in the current session.      |
| `value`  | string |           | The extra's gratuitousness type. May contain `None`, `Included`, `Free` or `Offered`. |

#### Summary

| Property | Type   | Mandatory | Description                                                                   |
| -------- | ------ | :-------: | ----------------------------------------------------------------------------- |
| `text`   | string |           | The extra's formatted summary.                                                |
| `value`  | string |           | The mime type of the summary. May contain `Html`, `Markdown` or  `PlainText`. |

#### Picture

| Property    | Type                                  | Mandatory | Description                                                                                          |
| ----------- | ------------------------------------- | :-------: | ---------------------------------------------------------------------------------------------------- |
| `templates` | array of [Template](broken-reference) |           | Contains information from picture templates requested by the [appropriate header](broken-reference). |
| `sortOrder` | integer _int32_                       |           | The display order of the pictures on the D-Edge booking engine.                                      |

#### Template

| Property | Type   | Mandatory | Description          |
| -------- | ------ | :-------: | -------------------- |
| `name`   | string |           | The template's name. |
| `url`    | string |           | The url's picture.   |

#### Counting type

| Property | Type   | Mandatory | Description                                                                       |
| -------- | ------ | :-------: | --------------------------------------------------------------------------------- |
| `text`   | string |           | The counting type expressed in the culture defined in the current session.        |
| `value`  | string |           | The extra's counting type. May contain `Booking`, `Day`, `Person` or `PersonDay`. |

#### Occupancy definition

| Property | Type                      | Mandatory | Description                                                                                                                                   |
| -------- | ------------------------- | :-------: | --------------------------------------------------------------------------------------------------------------------------------------------- |
| `text`   | string                    |           | The text regarding the occupancy of the extra displayed on the D-Edge booking engine expressed in the culture defined in the current session. |
| `value`  | [Value](broken-reference) |           | Contains details regarding the occupancy of the extra.                                                                                        |

#### Value

| Property      | Type            | Mandatory | Description                                                                                              |
| ------------- | --------------- | :-------: | -------------------------------------------------------------------------------------------------------- |
| `isDetailed`  | boolean         |           | If true, the occupancy is configured with the restrictions: `adultCount`, `childCount` or `infantCount`. |
| `personCount` | integer _int32_ |           | Number of people configured for the occupancy.                                                           |
| `adultCount`  | integer _int32_ |           | Number of adults configured for the occupancy.                                                           |
| `childCount`  | integer _int32_ |           | Number of children configured for the occupancy.                                                         |
| `infantCount` | integer _int32_ |           | Number of infants configured for the occupancy.                                                          |

## Get the extras descriptions

{% hint style="info" %}
Extras descriptions could be searched only if a `selectedHotelId` has been specified in the session context.
{% endhint %}

Use this operation to get the extras descriptions matching the session context.

### Request

| Path parameter | Type   |       Mandatory      | Description                       |
| -------------- | ------ | :------------------: | --------------------------------- |
| `sessionId`    | string | :white\_check\_mark: | Unique identifier of the session. |

| Header parameter         | Type                                              | Mandatory | Description                                                          |
| ------------------------ | ------------------------------------------------- | :-------: | -------------------------------------------------------------------- |
| `X-AVP-Properties`       | string from [Properties](broken-reference)        |           | The properties required in the response separated with \| character. |
| `X-AVP-DescriptionType`  | string from [Description types](broken-reference) |           | Mime type of the descriptions separated with \| character.           |
| `X-AVP-PictureTemplates` | string from [Picture templates](broken-reference) |           | The picture templates separated with \| character.                   |

#### Properties

* `Information` : corresponds to descriptions of the extras (summary pictures, stock...).
* `Rooms` : list of room identifiers of the extras.
* `Rates` : list of rate identifiers of the extras.

#### Description types

* `text/html` (default)
* `text/plain`
* `text/x-markdown`

#### Picture templates

* `Small`&#x20;
* `Medium`&#x20;
* `Large`&#x20;
* `Original`&#x20;
* `Touch_Image_Extra`&#x20;
* `Touch_Image_Extra@2x`&#x20;
* `Touch_Image_Gallery`&#x20;
* `Touch_Image_Gallery@2x`&#x20;
* `Touch_Image_Hotel`&#x20;
* `Touch_Image_Hotel@2x`&#x20;
* `Touch_Image_Rate`&#x20;
* `Touch_Image_Rate@2x`&#x20;
* `Touch_Image_Room`&#x20;
* `Touch_Image_Room@2x`&#x20;
* `Touch_Image_RoomRate`&#x20;
* `Touch_Image_RoomRate@2x`&#x20;
* `Smart_Gallery_Preview`&#x20;
* `Smart_Image_Zoom`&#x20;
* `Smart_Package_Principal`&#x20;
* `Smart_Room_Principal`

`GET > https://api-be.availpro.com/v1/{sessionId}/description/extras`

### Response

```javascript
{
  "extras": [
    {
      "extraId": 31090,
      "name": "½ bottle of Champagne",
      "hotelId": 14188,
      "rateIds": [...],
      "roomIds": [...],
      "information": {...}
    },
    {...}
  ]
}
```

| Property | Type                               | Mandatory | Description                       |
| -------- | ---------------------------------- | :-------: | --------------------------------- |
| `extras` | array of [Extra](broken-reference) |           | Contains the extras' information. |

#### Extra

Same structure as the [Extra](broken-reference) object in [Get the extra description](broken-reference) operation.
