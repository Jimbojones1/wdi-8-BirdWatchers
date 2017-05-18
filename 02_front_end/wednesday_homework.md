# Wednesday Exercises and Homework

> Today and tonight's exercises and homework will reinforce the array concepts combined with how to access the properties of an object two different ways

## In-Class Loop & Object Exercise

### Instructions

Your job is to write a program that loops over an array of objects. Using the example array below, do the following:

1. Iterate over each item in the array
2. Filter out all objects where the `Language` property does not equal to `en` (stands for English)
3. Loop over the filtered array and...
4. Output each array item's key and value

__Hint:__ Remember, this is an array of objects. This means you'll need to use both array methods and object concepts to complete this. Also remember that some methods return new copies of arrays instead of changing their values in place.

#### Starter code:

This is the array of objects you'll need to work with:

```js
var tagMap = [
  {
    "MapTagID":1,
    "MapParentID":0,
    "ParentID":1,
    "TagID":1,
    "TagName":"Walt Disney World",
    "TopParentID":1,
    "TagLevel":0,
    "Language": "en"
  },
  {
    "MapTagID":1,
    "MapParentID":0,
    "ParentID":1,
    "TagID":1,
    "TagName":"Walt Disney World",
    "TopParentID":1,
    "TagLevel":0,
    "Language": "es"
  },
  {
    "MapTagID":1,
    "MapParentID":0,
    "ParentID":1,
    "TagID":1,
    "TagName":"Walt Disney World",
    "TopParentID":1,
    "TagLevel":0,
    "Language": "fr"
  },
  {
    "MapTagID":1,
    "MapParentID":0,
    "ParentID":1,
    "TagID":1,
    "TagName":"Walt Disney World",
    "TopParentID":1,
    "TagLevel":0,
    "Language": "pt"
  },
  {
    "MapTagID":2,
    "MapParentID":0,
    "ParentID":2,
    "TagID":2,
    "TagName":"Disneyland",
    "TopParentID":2,
    "TagLevel":0,
    "Language": "en"
  },
  {
    "MapTagID":3,
    "MapParentID":0,
    "ParentID":3,
    "TagID":3,
    "TagName":"ESPN Wide World of Sports",
    "TopParentID":3,
    "TagLevel":0,
    "Language": "en"
  },
  {
    "MapTagID":5,
    "MapParentID":0,
    "ParentID":5,
    "TagID":5,
    "TagName":"Disney Cruise Line",
    "TopParentID":5,
    "TagLevel":0,
    "Language": "en"
  },
  {
    "MapTagID":6,
    "MapParentID":0,
    "ParentID":6,
    "TagID":6,
    "TagName":"Disney Vacation Club",
    "TopParentID":6,
    "TagLevel":0,
    "Language": "en"
  },
  {
    "MapTagID":7,
    "MapParentID":0,
    "ParentID":7,
    "TagID":7,
    "TagName":"runDisney",
    "TopParentID":7,
    "TagLevel":0,
    "Language": "en"
  },
  {
    "MapTagID":8,
    "MapParentID":1,
    "ParentID":1,
    "TagID":8,
    "TagName":"Dining",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":8,
    "MapParentID":1,
    "ParentID":1,
    "TagID":8,
    "TagName":"Restaurantes/Comidas",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "es"
  },
  {
    "MapTagID":8,
    "MapParentID":1,
    "ParentID":1,
    "TagID":8,
    "TagName":"Restaurants",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "fr"
  },
  {
    "MapTagID":8,
    "MapParentID":1,
    "ParentID":1,
    "TagID":8,
    "TagName":"Refeições",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "pt"
  },
  {
    "MapTagID":9,
    "MapParentID":2,
    "ParentID":2,
    "TagID":8,
    "TagName":"Dining",
    "TopParentID":2,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":10,
    "MapParentID":3,
    "ParentID":3,
    "TagID":8,
    "TagName":"Dining",
    "TopParentID":3,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":12,
    "MapParentID":5,
    "ParentID":5,
    "TagID":8,
    "TagName":"Dining",
    "TopParentID":5,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":13,
    "MapParentID":6,
    "ParentID":6,
    "TagID":8,
    "TagName":"Dining",
    "TopParentID":6,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":99,
    "MapParentID":2,
    "ParentID":2,
    "TagID":24,
    "TagName":"Moms Panel",
    "TopParentID":2,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":100,
    "MapParentID":2,
    "ParentID":2,
    "TagID":47,
    "TagName":"General",
    "TopParentID":2,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":101,
    "MapParentID":2,
    "ParentID":2,
    "TagID":48,
    "TagName":"Planning",
    "TopParentID":2,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":102,
    "MapParentID":2,
    "ParentID":2,
    "TagID":49,
    "TagName":"Destinations",
    "TopParentID":2,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":103,
    "MapParentID":2,
    "ParentID":2,
    "TagID":63,
    "TagName":"Activities",
    "TopParentID":2,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":104,
    "MapParentID":2,
    "ParentID":2,
    "TagID":71,
    "TagName":"Shopping and Nightlife",
    "TopParentID":2,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":105,
    "MapParentID":2,
    "ParentID":2,
    "TagID":75,
    "TagName":"Tickets",
    "TopParentID":2,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":152,
    "MapParentID":5,
    "ParentID":5,
    "TagID":24,
    "TagName":"Moms Panel",
    "TopParentID":5,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":153,
    "MapParentID":5,
    "ParentID":5,
    "TagID":47,
    "TagName":"General",
    "TopParentID":5,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":154,
    "MapParentID":5,
    "ParentID":5,
    "TagID":48,
    "TagName":"Planning",
    "TopParentID":5,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":155,
    "MapParentID":5,
    "ParentID":5,
    "TagID":49,
    "TagName":"Destinations",
    "TopParentID":5,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":156,
    "MapParentID":5,
    "ParentID":5,
    "TagID":63,
    "TagName":"Activities",
    "TopParentID":5,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":197,
    "MapParentID":3,
    "ParentID":3,
    "TagID":24,
    "TagName":"Moms Panel",
    "TopParentID":3,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":198,
    "MapParentID":3,
    "ParentID":3,
    "TagID":47,
    "TagName":"General",
    "TopParentID":3,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":199,
    "MapParentID":3,
    "ParentID":3,
    "TagID":48,
    "TagName":"Planning",
    "TopParentID":3,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":200,
    "MapParentID":3,
    "ParentID":3,
    "TagID":63,
    "TagName":"Activities",
    "TopParentID":3,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":201,
    "MapParentID":3,
    "ParentID":3,
    "TagID":75,
    "TagName":"Tickets",
    "TopParentID":3,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":221,
    "MapParentID":1,
    "ParentID":1,
    "TagID":160,
    "TagName":"Celebrations",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":221,
    "MapParentID":1,
    "ParentID":1,
    "TagID":160,
    "TagName":"Celebraciones",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "es"
  },
  {
    "MapTagID":221,
    "MapParentID":1,
    "ParentID":1,
    "TagID":160,
    "TagName":"Célébrations",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "fr"
  },
  {
    "MapTagID":221,
    "MapParentID":1,
    "ParentID":1,
    "TagID":160,
    "TagName":"Comemorações",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "pt"
  },
  {
    "MapTagID":46,
    "MapParentID":1,
    "ParentID":1,
    "TagID":24,
    "TagName":"Moms Panel",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":46,
    "MapParentID":1,
    "ParentID":1,
    "TagID":24,
    "TagName":"Moms Panel",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "es"
  },
  {
    "MapTagID":46,
    "MapParentID":1,
    "ParentID":1,
    "TagID":24,
    "TagName":"Mom's Panel",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "fr"
  },
  {
    "MapTagID":46,
    "MapParentID":1,
    "ParentID":1,
    "TagID":24,
    "TagName":"Painel de mães",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "pt"
  },
  {
    "MapTagID":47,
    "MapParentID":1,
    "ParentID":1,
    "TagID":47,
    "TagName":"General",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":47,
    "MapParentID":1,
    "ParentID":1,
    "TagID":47,
    "TagName":"General",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "es"
  },
  {
    "MapTagID":47,
    "MapParentID":1,
    "ParentID":1,
    "TagID":47,
    "TagName":"Généralité",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "fr"
  },
  {
    "MapTagID":47,
    "MapParentID":1,
    "ParentID":1,
    "TagID":47,
    "TagName":"Geral",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "pt"
  },
  {
    "MapTagID":48,
    "MapParentID":1,
    "ParentID":1,
    "TagID":48,
    "TagName":"Planning",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":48,
    "MapParentID":1,
    "ParentID":1,
    "TagID":48,
    "TagName":"Planificación",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "es"
  },
  {
    "MapTagID":48,
    "MapParentID":1,
    "ParentID":1,
    "TagID":48,
    "TagName":"Planification",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "fr"
  },
  {
    "MapTagID":48,
    "MapParentID":1,
    "ParentID":1,
    "TagID":48,
    "TagName":"Planejamento",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "pt"
  },
  {
    "MapTagID":49,
    "MapParentID":1,
    "ParentID":1,
    "TagID":49,
    "TagName":"Destinations",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":49,
    "MapParentID":1,
    "ParentID":1,
    "TagID":49,
    "TagName":"Destinos",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "es"
  },
  {
    "MapTagID":49,
    "MapParentID":1,
    "ParentID":1,
    "TagID":49,
    "TagName":"Destinations",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "fr"
  },
  {
    "MapTagID":49,
    "MapParentID":1,
    "ParentID":1,
    "TagID":49,
    "TagName":"Destinos",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "pt"
  },
  {
    "MapTagID":50,
    "MapParentID":1,
    "ParentID":1,
    "TagID":63,
    "TagName":"Activities",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":50,
    "MapParentID":1,
    "ParentID":1,
    "TagID":63,
    "TagName":"Actividades",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "es"
  },
  {
    "MapTagID":50,
    "MapParentID":1,
    "ParentID":1,
    "TagID":63,
    "TagName":"Activités",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "fr"
  },
  {
    "MapTagID":50,
    "MapParentID":1,
    "ParentID":1,
    "TagID":63,
    "TagName":"Atividades",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "pt"
  },
  {
    "MapTagID":51,
    "MapParentID":1,
    "ParentID":1,
    "TagID":71,
    "TagName":"Shopping and Nightlife",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":51,
    "MapParentID":1,
    "ParentID":1,
    "TagID":71,
    "TagName":"Compras y vida nocturna",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "es"
  },
  {
    "MapTagID":51,
    "MapParentID":1,
    "ParentID":1,
    "TagID":71,
    "TagName":"Magasinage et vie nocturne",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "fr"
  },
  {
    "MapTagID":51,
    "MapParentID":1,
    "ParentID":1,
    "TagID":71,
    "TagName":"Lojas e vida noturna",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "pt"
  },
  {
    "MapTagID":52,
    "MapParentID":1,
    "ParentID":1,
    "TagID":75,
    "TagName":"Tickets",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":52,
    "MapParentID":1,
    "ParentID":1,
    "TagID":75,
    "TagName":"Boletos",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "es"
  },
  {
    "MapTagID":52,
    "MapParentID":1,
    "ParentID":1,
    "TagID":75,
    "TagName":"Billets",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "fr"
  },
  {
    "MapTagID":52,
    "MapParentID":1,
    "ParentID":1,
    "TagID":75,
    "TagName":"Ingressos",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "pt"
  },
  {
    "MapTagID":53,
    "MapParentID":1,
    "ParentID":1,
    "TagID":82,
    "TagName":"Videos",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":53,
    "MapParentID":1,
    "ParentID":1,
    "TagID":82,
    "TagName":"Videos",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "es"
  },
  {
    "MapTagID":53,
    "MapParentID":1,
    "ParentID":1,
    "TagID":82,
    "TagName":"Videos",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "fr"
  },
  {
    "MapTagID":53,
    "MapParentID":1,
    "ParentID":1,
    "TagID":82,
    "TagName":"Videos",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "pt"
  },
  {
    "MapTagID":276,
    "MapParentID":1,
    "ParentID":1,
    "TagID":198,
    "TagName":"Resort Hotels",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":276,
    "MapParentID":1,
    "ParentID":1,
    "TagID":198,
    "TagName":"Hoteles",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "es"
  },
  {
    "MapTagID":276,
    "MapParentID":1,
    "ParentID":1,
    "TagID":198,
    "TagName":"Hôtels Disney",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "fr"
  },
  {
    "MapTagID":276,
    "MapParentID":1,
    "ParentID":1,
    "TagID":198,
    "TagName":"Hotéis Resort",
    "TopParentID":1,
    "TagLevel":1,
    "Language": "pt"
  },
  {
    "MapTagID":247,
    "MapParentID":7,
    "ParentID":7,
    "TagID":8,
    "TagName":"Dining",
    "TopParentID":7,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":248,
    "MapParentID":7,
    "ParentID":7,
    "TagID":47,
    "TagName":"General",
    "TopParentID":7,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":249,
    "MapParentID":7,
    "ParentID":7,
    "TagID":48,
    "TagName":"Planning",
    "TopParentID":7,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":250,
    "MapParentID":7,
    "ParentID":7,
    "TagID":49,
    "TagName":"Destinations",
    "TopParentID":7,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":251,
    "MapParentID":3,
    "ParentID":3,
    "TagID":71,
    "TagName":"Shopping and Nightlife",
    "TopParentID":3,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":252,
    "MapParentID":3,
    "ParentID":3,
    "TagID":49,
    "TagName":"Destinations",
    "TopParentID":3,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":177,
    "MapParentID":6,
    "ParentID":6,
    "TagID":24,
    "TagName":"Moms Panel",
    "TopParentID":6,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":178,
    "MapParentID":6,
    "ParentID":6,
    "TagID":47,
    "TagName":"General",
    "TopParentID":6,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":179,
    "MapParentID":6,
    "ParentID":6,
    "TagID":48,
    "TagName":"Planning",
    "TopParentID":6,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":180,
    "MapParentID":6,
    "ParentID":6,
    "TagID":49,
    "TagName":"Destinations",
    "TopParentID":6,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":181,
    "MapParentID":6,
    "ParentID":6,
    "TagID":63,
    "TagName":"Activities",
    "TopParentID":6,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":189,
    "MapParentID":7,
    "ParentID":7,
    "TagID":24,
    "TagName":"Moms Panel",
    "TopParentID":7,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":190,
    "MapParentID":7,
    "ParentID":7,
    "TagID":63,
    "TagName":"Activities",
    "TopParentID":7,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":241,
    "MapParentID":6,
    "ParentID":6,
    "TagID":137,
    "TagName":"Aulani",
    "TopParentID":6,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":238,
    "MapParentID":5,
    "ParentID":5,
    "TagID":71,
    "TagName":"Shopping and Nightlife",
    "TopParentID":5,
    "TagLevel":1,
    "Language": "en"
  },
  {
    "MapTagID":239,
    "MapParentID":238,
    "ParentID":71,
    "TagID":170,
    "TagName":"Shopping",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":240,
    "MapParentID":238,
    "ParentID":71,
    "TagID":171,
    "TagName":"Nightlife",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":242,
    "MapParentID":241,
    "ParentID":137,
    "TagID":8,
    "TagName":"Dining",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":243,
    "MapParentID":241,
    "ParentID":137,
    "TagID":48,
    "TagName":"Planning",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":244,
    "MapParentID":241,
    "ParentID":137,
    "TagID":49,
    "TagName":"Destinations",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":245,
    "MapParentID":241,
    "ParentID":137,
    "TagID":63,
    "TagName":"Activities",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":246,
    "MapParentID":241,
    "ParentID":137,
    "TagID":172,
    "TagName":"Accomodations",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":191,
    "MapParentID":190,
    "ParentID":63,
    "TagID":146,
    "TagName":"Endurance Races",
    "TopParentID":7,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":192,
    "MapParentID":189,
    "ParentID":24,
    "TagID":25,
    "TagName":"How To Be a Panelist",
    "TopParentID":7,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":196,
    "MapParentID":10,
    "ParentID":8,
    "TagID":153,
    "TagName":"Feeding the Team",
    "TopParentID":3,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":184,
    "MapParentID":178,
    "ParentID":47,
    "TagID":135,
    "TagName":"Member Benefits",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":185,
    "MapParentID":177,
    "ParentID":24,
    "TagID":25,
    "TagName":"How To Be a Panelist",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":257,
    "MapParentID":50,
    "ParentID":63,
    "TagID":173,
    "TagName":"Golf",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":257,
    "MapParentID":50,
    "ParentID":63,
    "TagID":173,
    "TagName":"Golf",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":257,
    "MapParentID":50,
    "ParentID":63,
    "TagID":173,
    "TagName":"Golf",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":257,
    "MapParentID":50,
    "ParentID":63,
    "TagID":173,
    "TagName":"Golfe",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":258,
    "MapParentID":50,
    "ParentID":63,
    "TagID":174,
    "TagName":"Miniature Golf",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":258,
    "MapParentID":50,
    "ParentID":63,
    "TagID":174,
    "TagName":"Minigolf",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":258,
    "MapParentID":50,
    "ParentID":63,
    "TagID":174,
    "TagName":"Mini-golf",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":258,
    "MapParentID":50,
    "ParentID":63,
    "TagID":174,
    "TagName":"Minigolfe",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":259,
    "MapParentID":50,
    "ParentID":63,
    "TagID":175,
    "TagName":"Spas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":259,
    "MapParentID":50,
    "ParentID":63,
    "TagID":175,
    "TagName":"Spas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":259,
    "MapParentID":50,
    "ParentID":63,
    "TagID":175,
    "TagName":"Centres de beauté",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":259,
    "MapParentID":50,
    "ParentID":63,
    "TagID":175,
    "TagName":"Spas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":260,
    "MapParentID":51,
    "ParentID":71,
    "TagID":178,
    "TagName":"Boardwalk",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":260,
    "MapParentID":51,
    "ParentID":71,
    "TagID":178,
    "TagName":"Boardwalk",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":260,
    "MapParentID":51,
    "ParentID":71,
    "TagID":178,
    "TagName":"Boardwalk",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":260,
    "MapParentID":51,
    "ParentID":71,
    "TagID":178,
    "TagName":"Boardwalk",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":261,
    "MapParentID":221,
    "ParentID":160,
    "TagID":179,
    "TagName":"Reunions",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":261,
    "MapParentID":221,
    "ParentID":160,
    "TagID":179,
    "TagName":"Reuniones",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":261,
    "MapParentID":221,
    "ParentID":160,
    "TagID":179,
    "TagName":"Réunions",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":261,
    "MapParentID":221,
    "ParentID":160,
    "TagID":179,
    "TagName":"Encontros",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":263,
    "MapParentID":8,
    "ParentID":8,
    "TagID":10,
    "TagName":"Quick Service",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":263,
    "MapParentID":8,
    "ParentID":8,
    "TagID":10,
    "TagName":"Servicio rápido",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":263,
    "MapParentID":8,
    "ParentID":8,
    "TagID":10,
    "TagName":"Service rapide",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":263,
    "MapParentID":8,
    "ParentID":8,
    "TagID":10,
    "TagName":"Serviço de balcão",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":264,
    "MapParentID":8,
    "ParentID":8,
    "TagID":12,
    "TagName":"Buffet and Family Style",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":264,
    "MapParentID":8,
    "ParentID":8,
    "TagID":12,
    "TagName":"Estilo buffet y familiar",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":264,
    "MapParentID":8,
    "ParentID":8,
    "TagID":12,
    "TagName":"Style buffet et familial",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":264,
    "MapParentID":8,
    "ParentID":8,
    "TagID":12,
    "TagName":"Bufê e pratos para serem compartilhados",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":265,
    "MapParentID":8,
    "ParentID":8,
    "TagID":94,
    "TagName":"Dining Events",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":265,
    "MapParentID":8,
    "ParentID":8,
    "TagID":94,
    "TagName":"Eventos con comida",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":265,
    "MapParentID":8,
    "ParentID":8,
    "TagID":94,
    "TagName":"Événements de repas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":265,
    "MapParentID":8,
    "ParentID":8,
    "TagID":94,
    "TagName":"Eventos com refeição",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":266,
    "MapParentID":8,
    "ParentID":8,
    "TagID":182,
    "TagName":"Casual Dining",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":266,
    "MapParentID":8,
    "ParentID":8,
    "TagID":182,
    "TagName":"Comida informal",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":266,
    "MapParentID":8,
    "ParentID":8,
    "TagID":182,
    "TagName":"Restaurant décontracté",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":266,
    "MapParentID":8,
    "ParentID":8,
    "TagID":182,
    "TagName":"Restaurante informal",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":267,
    "MapParentID":8,
    "ParentID":8,
    "TagID":183,
    "TagName":"Dinner Shows",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":267,
    "MapParentID":8,
    "ParentID":8,
    "TagID":183,
    "TagName":"Espectáculos con cena",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":267,
    "MapParentID":8,
    "ParentID":8,
    "TagID":183,
    "TagName":"Soupers-spectacles",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":267,
    "MapParentID":8,
    "ParentID":8,
    "TagID":183,
    "TagName":"Shows com jantar",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":268,
    "MapParentID":8,
    "ParentID":8,
    "TagID":185,
    "TagName":"Fast Casual Dining",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":268,
    "MapParentID":8,
    "ParentID":8,
    "TagID":185,
    "TagName":"Comidas informales y rápidas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":268,
    "MapParentID":8,
    "ParentID":8,
    "TagID":185,
    "TagName":"Repas décontractés rapides",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":268,
    "MapParentID":8,
    "ParentID":8,
    "TagID":185,
    "TagName":"Restaurante informal rápido",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":269,
    "MapParentID":8,
    "ParentID":8,
    "TagID":186,
    "TagName":"Food Truck",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":269,
    "MapParentID":8,
    "ParentID":8,
    "TagID":186,
    "TagName":"Camión de comida",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":269,
    "MapParentID":8,
    "ParentID":8,
    "TagID":186,
    "TagName":"Cantine mobile",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":269,
    "MapParentID":8,
    "ParentID":8,
    "TagID":186,
    "TagName":"Food Truck",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":270,
    "MapParentID":8,
    "ParentID":8,
    "TagID":187,
    "TagName":"Lounges",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":270,
    "MapParentID":8,
    "ParentID":8,
    "TagID":187,
    "TagName":"Bar cafetería",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":270,
    "MapParentID":8,
    "ParentID":8,
    "TagID":187,
    "TagName":"Bars-salons",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":270,
    "MapParentID":8,
    "ParentID":8,
    "TagID":187,
    "TagName":"Lounges",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":271,
    "MapParentID":8,
    "ParentID":8,
    "TagID":188,
    "TagName":"Pool Bars",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":271,
    "MapParentID":8,
    "ParentID":8,
    "TagID":188,
    "TagName":"Bares en la piscina",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":271,
    "MapParentID":8,
    "ParentID":8,
    "TagID":188,
    "TagName":"Bars à la piscine",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":271,
    "MapParentID":8,
    "ParentID":8,
    "TagID":188,
    "TagName":"Bares de piscina",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":272,
    "MapParentID":8,
    "ParentID":8,
    "TagID":189,
    "TagName":"Room Service",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":272,
    "MapParentID":8,
    "ParentID":8,
    "TagID":189,
    "TagName":"Servicio de habitaciones ",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":272,
    "MapParentID":8,
    "ParentID":8,
    "TagID":189,
    "TagName":"Service aux chambres",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":272,
    "MapParentID":8,
    "ParentID":8,
    "TagID":189,
    "TagName":"Serviço de quarto",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":273,
    "MapParentID":8,
    "ParentID":8,
    "TagID":190,
    "TagName":"Grab and Go",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":273,
    "MapParentID":8,
    "ParentID":8,
    "TagID":190,
    "TagName":"Listo para llevar",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":273,
    "MapParentID":8,
    "ParentID":8,
    "TagID":190,
    "TagName":"À emporter",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":273,
    "MapParentID":8,
    "ParentID":8,
    "TagID":190,
    "TagName":"Retirar e levar",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":274,
    "MapParentID":49,
    "ParentID":49,
    "TagID":196,
    "TagName":"Disneys Typhoon Lagoon",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":274,
    "MapParentID":49,
    "ParentID":49,
    "TagID":196,
    "TagName":"Disneys Typhoon Lagoon",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":274,
    "MapParentID":49,
    "ParentID":49,
    "TagID":196,
    "TagName":"Disneys Typhoon Lagoon",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":274,
    "MapParentID":49,
    "ParentID":49,
    "TagID":196,
    "TagName":"Disneys Typhoon Lagoon",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":275,
    "MapParentID":49,
    "ParentID":49,
    "TagID":197,
    "TagName":"Disneys Blizzard Beach",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":275,
    "MapParentID":49,
    "ParentID":49,
    "TagID":197,
    "TagName":"Disneys Blizzard Beach",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":275,
    "MapParentID":49,
    "ParentID":49,
    "TagID":197,
    "TagName":"Disneys Blizzard Beach",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":275,
    "MapParentID":49,
    "ParentID":49,
    "TagID":197,
    "TagName":"Disneys Blizzard Beach",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":277,
    "MapParentID":276,
    "ParentID":198,
    "TagID":191,
    "TagName":"Deluxe Resorts",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":277,
    "MapParentID":276,
    "ParentID":198,
    "TagID":191,
    "TagName":"Hoteles de Lujo",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":277,
    "MapParentID":276,
    "ParentID":198,
    "TagID":191,
    "TagName":"Hôtels Disney de catégorie « Deluxe »",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":277,
    "MapParentID":276,
    "ParentID":198,
    "TagID":191,
    "TagName":"Resorts categoria deluxe",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":278,
    "MapParentID":276,
    "ParentID":198,
    "TagID":192,
    "TagName":"Moderate Resorts",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":278,
    "MapParentID":276,
    "ParentID":198,
    "TagID":192,
    "TagName":"Hoteles Moderados",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":278,
    "MapParentID":276,
    "ParentID":198,
    "TagID":192,
    "TagName":"Hôtels Disney de catégorie « Moderate »",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":278,
    "MapParentID":276,
    "ParentID":198,
    "TagID":192,
    "TagName":"Resorts categoria moderada",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":279,
    "MapParentID":276,
    "ParentID":198,
    "TagID":193,
    "TagName":"Value Resorts",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":279,
    "MapParentID":276,
    "ParentID":198,
    "TagID":193,
    "TagName":"Hoteles Económicos",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":279,
    "MapParentID":276,
    "ParentID":198,
    "TagID":193,
    "TagName":"Hôtels Disney de catégorie « Value »",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":279,
    "MapParentID":276,
    "ParentID":198,
    "TagID":193,
    "TagName":"Resorts categoria econômica",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":280,
    "MapParentID":276,
    "ParentID":198,
    "TagID":194,
    "TagName":"Deluxe Villa Resorts",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":280,
    "MapParentID":276,
    "ParentID":198,
    "TagID":194,
    "TagName":"Villas de Lujo",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":280,
    "MapParentID":276,
    "ParentID":198,
    "TagID":194,
    "TagName":"Hôtels de type villa de catégorie « Deluxe »",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":280,
    "MapParentID":276,
    "ParentID":198,
    "TagID":194,
    "TagName":"Resorts Villa categoria deluxe",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":281,
    "MapParentID":276,
    "ParentID":198,
    "TagID":195,
    "TagName":"Campgrounds",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":281,
    "MapParentID":276,
    "ParentID":198,
    "TagID":195,
    "TagName":"Sitios para acampar",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":281,
    "MapParentID":276,
    "ParentID":198,
    "TagID":195,
    "TagName":"Terrains de camping",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":281,
    "MapParentID":276,
    "ParentID":198,
    "TagID":195,
    "TagName":"Acampamentos",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":282,
    "MapParentID":52,
    "ParentID":75,
    "TagID":47,
    "TagName":"General",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":282,
    "MapParentID":52,
    "ParentID":75,
    "TagID":47,
    "TagName":"General",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":282,
    "MapParentID":52,
    "ParentID":75,
    "TagID":47,
    "TagName":"Généralité",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":282,
    "MapParentID":52,
    "ParentID":75,
    "TagID":47,
    "TagName":"Geral",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":283,
    "MapParentID":52,
    "ParentID":75,
    "TagID":201,
    "TagName":"Military",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":283,
    "MapParentID":52,
    "ParentID":75,
    "TagID":201,
    "TagName":"Militares",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":283,
    "MapParentID":52,
    "ParentID":75,
    "TagID":201,
    "TagName":"Militaire",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":283,
    "MapParentID":52,
    "ParentID":75,
    "TagID":201,
    "TagName":"Militares",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":284,
    "MapParentID":52,
    "ParentID":75,
    "TagID":202,
    "TagName":"Special Events",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":284,
    "MapParentID":52,
    "ParentID":75,
    "TagID":202,
    "TagName":"Eventos especiales",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":284,
    "MapParentID":52,
    "ParentID":75,
    "TagID":202,
    "TagName":"Événements spéciaux",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":284,
    "MapParentID":52,
    "ParentID":75,
    "TagID":202,
    "TagName":"Eventos especiais",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":285,
    "MapParentID":48,
    "ParentID":48,
    "TagID":76,
    "TagName":"FastPass+",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":285,
    "MapParentID":48,
    "ParentID":48,
    "TagID":76,
    "TagName":"FastPass+",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":285,
    "MapParentID":48,
    "ParentID":48,
    "TagID":76,
    "TagName":"FastPass+",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":285,
    "MapParentID":48,
    "ParentID":48,
    "TagID":76,
    "TagName":"FastPass+",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":286,
    "MapParentID":48,
    "ParentID":48,
    "TagID":203,
    "TagName":"Magic Bands",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":286,
    "MapParentID":48,
    "ParentID":48,
    "TagID":203,
    "TagName":"Magic Bands",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":286,
    "MapParentID":48,
    "ParentID":48,
    "TagID":203,
    "TagName":"Bracelets Magic Band",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":286,
    "MapParentID":48,
    "ParentID":48,
    "TagID":203,
    "TagName":"Magic Bands",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":287,
    "MapParentID":48,
    "ParentID":48,
    "TagID":204,
    "TagName":"Memory Maker",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":287,
    "MapParentID":48,
    "ParentID":48,
    "TagID":204,
    "TagName":"Memory Maker",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":287,
    "MapParentID":48,
    "ParentID":48,
    "TagID":204,
    "TagName":"Memory Maker",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":287,
    "MapParentID":48,
    "ParentID":48,
    "TagID":204,
    "TagName":"Memory Maker",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":288,
    "MapParentID":48,
    "ParentID":48,
    "TagID":206,
    "TagName":"First Disney Vacation",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":288,
    "MapParentID":48,
    "ParentID":48,
    "TagID":206,
    "TagName":"Primeras vacaciones en Disney",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":288,
    "MapParentID":48,
    "ParentID":48,
    "TagID":206,
    "TagName":"Mes premières vacances Disney",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":288,
    "MapParentID":48,
    "ParentID":48,
    "TagID":206,
    "TagName":"Primeiras férias na Disney",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":289,
    "MapParentID":48,
    "ParentID":48,
    "TagID":207,
    "TagName":"Parties 5-9",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":289,
    "MapParentID":48,
    "ParentID":48,
    "TagID":207,
    "TagName":"Grupos de 5 a 9 integrantes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":289,
    "MapParentID":48,
    "ParentID":48,
    "TagID":207,
    "TagName":"Groupes 5-9",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":289,
    "MapParentID":48,
    "ParentID":48,
    "TagID":207,
    "TagName":"Grupos de 5 a 9 pessoas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":290,
    "MapParentID":48,
    "ParentID":48,
    "TagID":208,
    "TagName":"Multi-Generational",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":290,
    "MapParentID":48,
    "ParentID":48,
    "TagID":208,
    "TagName":"Multigeneracional",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":290,
    "MapParentID":48,
    "ParentID":48,
    "TagID":208,
    "TagName":"Multigénérationel",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":290,
    "MapParentID":48,
    "ParentID":48,
    "TagID":208,
    "TagName":"Várias gerações",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":291,
    "MapParentID":49,
    "ParentID":49,
    "TagID":65,
    "TagName":"Entertainment",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":291,
    "MapParentID":49,
    "ParentID":49,
    "TagID":65,
    "TagName":"Entretenimiento",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":291,
    "MapParentID":49,
    "ParentID":49,
    "TagID":65,
    "TagName":"Divertissements",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":291,
    "MapParentID":49,
    "ParentID":49,
    "TagID":65,
    "TagName":"Entretenimento",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":292,
    "MapParentID":49,
    "ParentID":49,
    "TagID":66,
    "TagName":"Events and Tours",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":292,
    "MapParentID":49,
    "ParentID":49,
    "TagID":66,
    "TagName":"Eventos y tours",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":292,
    "MapParentID":49,
    "ParentID":49,
    "TagID":66,
    "TagName":"Événements et visites",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":292,
    "MapParentID":49,
    "ParentID":49,
    "TagID":66,
    "TagName":"Eventos e passeios",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":293,
    "MapParentID":49,
    "ParentID":49,
    "TagID":67,
    "TagName":"Parades",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":293,
    "MapParentID":49,
    "ParentID":49,
    "TagID":67,
    "TagName":"Desfiles",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":293,
    "MapParentID":49,
    "ParentID":49,
    "TagID":67,
    "TagName":"Parades",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":293,
    "MapParentID":49,
    "ParentID":49,
    "TagID":67,
    "TagName":"Desfiles",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":294,
    "MapParentID":49,
    "ParentID":49,
    "TagID":68,
    "TagName":"Fireworks",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":294,
    "MapParentID":49,
    "ParentID":49,
    "TagID":68,
    "TagName":"Fuegos artificiales",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":294,
    "MapParentID":49,
    "ParentID":49,
    "TagID":68,
    "TagName":"Feux d’artifice",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":294,
    "MapParentID":49,
    "ParentID":49,
    "TagID":68,
    "TagName":"Fogos de artifício",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":295,
    "MapParentID":49,
    "ParentID":49,
    "TagID":202,
    "TagName":"Special Events",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":295,
    "MapParentID":49,
    "ParentID":49,
    "TagID":202,
    "TagName":"Eventos especiales",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":295,
    "MapParentID":49,
    "ParentID":49,
    "TagID":202,
    "TagName":"Événements spéciaux",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":295,
    "MapParentID":49,
    "ParentID":49,
    "TagID":202,
    "TagName":"Eventos especiais",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":296,
    "MapParentID":180,
    "ParentID":49,
    "TagID":137,
    "TagName":"Aulani",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":297,
    "MapParentID":180,
    "ParentID":49,
    "TagID":213,
    "TagName":"Disney Vacation Club Villas",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":298,
    "MapParentID":180,
    "ParentID":49,
    "TagID":214,
    "TagName":"Ko Olina",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":299,
    "MapParentID":180,
    "ParentID":49,
    "TagID":215,
    "TagName":"Hawaii",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":300,
    "MapParentID":180,
    "ParentID":49,
    "TagID":216,
    "TagName":"Bay Lake Tower at Disney’s Contemporary Resort",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":301,
    "MapParentID":180,
    "ParentID":49,
    "TagID":217,
    "TagName":"Disney Vacation Club Villa at Disney’s Animal Kingdom Lodge",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":302,
    "MapParentID":180,
    "ParentID":49,
    "TagID":218,
    "TagName":"Kidani Village at Disney’s Animal Kingdom Lodge",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":303,
    "MapParentID":180,
    "ParentID":49,
    "TagID":219,
    "TagName":"Disney’s Beach Club Villas",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":304,
    "MapParentID":180,
    "ParentID":49,
    "TagID":220,
    "TagName":"Disney's Hilton Head Island Resort",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":305,
    "MapParentID":180,
    "ParentID":49,
    "TagID":221,
    "TagName":"Disney's Old Key West Resort",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":306,
    "MapParentID":180,
    "ParentID":49,
    "TagID":222,
    "TagName":"Disney's Polynesian Villas and Bungalows",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":307,
    "MapParentID":180,
    "ParentID":49,
    "TagID":223,
    "TagName":"Disney's BoardWalk Villas",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":308,
    "MapParentID":180,
    "ParentID":49,
    "TagID":224,
    "TagName":"Disney's Saratoga Springs Resort and Spa",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":309,
    "MapParentID":180,
    "ParentID":49,
    "TagID":225,
    "TagName":"Disney's Vero Beach Resort",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":310,
    "MapParentID":180,
    "ParentID":49,
    "TagID":226,
    "TagName":"The Villa's at Disney's Wilderness Lodge",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":311,
    "MapParentID":180,
    "ParentID":49,
    "TagID":227,
    "TagName":"The Villas at Disney's Grand Floridian Resort and Spa",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":312,
    "MapParentID":180,
    "ParentID":49,
    "TagID":228,
    "TagName":"The Villas at Disney's Grand Californian Hotel and Spa",
    "TopParentID":6,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":313,
    "MapParentID":12,
    "ParentID":8,
    "TagID":9,
    "TagName":"Table Service",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":314,
    "MapParentID":12,
    "ParentID":8,
    "TagID":185,
    "TagName":"Fast Casual Dining",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":315,
    "MapParentID":12,
    "ParentID":8,
    "TagID":229,
    "TagName":"Snack Stands",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":318,
    "MapParentID":50,
    "ParentID":63,
    "TagID":176,
    "TagName":"Mickey's Very Merry Christmas Party",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":318,
    "MapParentID":50,
    "ParentID":63,
    "TagID":176,
    "TagName":"Mickey’s Very Merry Christmas Party",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":318,
    "MapParentID":50,
    "ParentID":63,
    "TagID":176,
    "TagName":"Mickey’s Very Merry Christmas Party",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":318,
    "MapParentID":50,
    "ParentID":63,
    "TagID":176,
    "TagName":"Mickey’s Very Merry Christmas Party",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":319,
    "MapParentID":50,
    "ParentID":63,
    "TagID":177,
    "TagName":"Mickey's Not-So-Scary Halloween Party",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":319,
    "MapParentID":50,
    "ParentID":63,
    "TagID":177,
    "TagName":"Mickey's Not-So-Scary Halloween Party",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":319,
    "MapParentID":50,
    "ParentID":63,
    "TagID":177,
    "TagName":"Mickey's Not-So-Scary Halloween Party",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":319,
    "MapParentID":50,
    "ParentID":63,
    "TagID":177,
    "TagName":"Mickey's Not-So-Scary Halloween Party",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":320,
    "MapParentID":50,
    "ParentID":63,
    "TagID":184,
    "TagName":"Dessert Parties",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":320,
    "MapParentID":50,
    "ParentID":63,
    "TagID":184,
    "TagName":"Fiestas de postres",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":320,
    "MapParentID":50,
    "ParentID":63,
    "TagID":184,
    "TagName":"Farandoles de desserts",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":320,
    "MapParentID":50,
    "ParentID":63,
    "TagID":184,
    "TagName":"Dessert Parties",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":321,
    "MapParentID":50,
    "ParentID":63,
    "TagID":210,
    "TagName":"Pirates League",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":321,
    "MapParentID":50,
    "ParentID":63,
    "TagID":210,
    "TagName":"Pirates League",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":321,
    "MapParentID":50,
    "ParentID":63,
    "TagID":210,
    "TagName":"Pirates League",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":321,
    "MapParentID":50,
    "ParentID":63,
    "TagID":210,
    "TagName":"Pirates League",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":322,
    "MapParentID":50,
    "ParentID":63,
    "TagID":211,
    "TagName":"Harmony Barber",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":322,
    "MapParentID":50,
    "ParentID":63,
    "TagID":211,
    "TagName":"Harmony Barber",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":322,
    "MapParentID":50,
    "ParentID":63,
    "TagID":211,
    "TagName":"Harmony Barber",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":322,
    "MapParentID":50,
    "ParentID":63,
    "TagID":211,
    "TagName":"Harmony Barber",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":323,
    "MapParentID":50,
    "ParentID":63,
    "TagID":212,
    "TagName":"Pirates and Pals",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":323,
    "MapParentID":50,
    "ParentID":63,
    "TagID":212,
    "TagName":"Pirates and Pals",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":323,
    "MapParentID":50,
    "ParentID":63,
    "TagID":212,
    "TagName":"Pirates and pals",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":323,
    "MapParentID":50,
    "ParentID":63,
    "TagID":212,
    "TagName":"Piratas e amigos",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":324,
    "MapParentID":48,
    "ParentID":48,
    "TagID":205,
    "TagName":"Budget Travel",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":324,
    "MapParentID":48,
    "ParentID":48,
    "TagID":205,
    "TagName":"Presupuesto de viaje",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":324,
    "MapParentID":48,
    "ParentID":48,
    "TagID":205,
    "TagName":"Voyage à bas prix",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":324,
    "MapParentID":48,
    "ParentID":48,
    "TagID":205,
    "TagName":"Viagem econômica",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":325,
    "MapParentID":49,
    "ParentID":49,
    "TagID":199,
    "TagName":"Magical Express",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":325,
    "MapParentID":49,
    "ParentID":49,
    "TagID":199,
    "TagName":"Magical Express",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":325,
    "MapParentID":49,
    "ParentID":49,
    "TagID":199,
    "TagName":"Magical Express",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":325,
    "MapParentID":49,
    "ParentID":49,
    "TagID":199,
    "TagName":"Magical Express",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":327,
    "MapParentID":52,
    "ParentID":75,
    "TagID":115,
    "TagName":"Special Offers",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":327,
    "MapParentID":52,
    "ParentID":75,
    "TagID":115,
    "TagName":"Ofertas especiales",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":327,
    "MapParentID":52,
    "ParentID":75,
    "TagID":115,
    "TagName":"Ofertas especiais",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":327,
    "MapParentID":52,
    "ParentID":75,
    "TagID":115,
    "TagName":"Ofertas especiais",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":328,
    "MapParentID":276,
    "ParentID":198,
    "TagID":61,
    "TagName":"Reservations",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":328,
    "MapParentID":276,
    "ParentID":198,
    "TagID":61,
    "TagName":"Reservaciones",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":328,
    "MapParentID":276,
    "ParentID":198,
    "TagID":61,
    "TagName":"Réservations",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":328,
    "MapParentID":276,
    "ParentID":198,
    "TagID":61,
    "TagName":"Reservas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":329,
    "MapParentID":48,
    "ParentID":48,
    "TagID":180,
    "TagName":"PhotoPass",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":329,
    "MapParentID":48,
    "ParentID":48,
    "TagID":180,
    "TagName":"Photo pass",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":329,
    "MapParentID":48,
    "ParentID":48,
    "TagID":180,
    "TagName":"Photo pass",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":329,
    "MapParentID":48,
    "ParentID":48,
    "TagID":180,
    "TagName":"Photo pass",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":330,
    "MapParentID":49,
    "ParentID":49,
    "TagID":72,
    "TagName":"Disney Springs",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":330,
    "MapParentID":49,
    "ParentID":49,
    "TagID":72,
    "TagName":"Disney Springs",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":330,
    "MapParentID":49,
    "ParentID":49,
    "TagID":72,
    "TagName":"Disney Springs",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":330,
    "MapParentID":49,
    "ParentID":49,
    "TagID":72,
    "TagName":"Disney Springs",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":331,
    "MapParentID":50,
    "ParentID":63,
    "TagID":230,
    "TagName":"Bibbidi Bobbidi Boutique",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":331,
    "MapParentID":50,
    "ParentID":63,
    "TagID":230,
    "TagName":"Bibbidi Bobbidi Boutique",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":331,
    "MapParentID":50,
    "ParentID":63,
    "TagID":230,
    "TagName":"Bibbidi Bobbidi Boutique",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":331,
    "MapParentID":50,
    "ParentID":63,
    "TagID":230,
    "TagName":"Butique Bibbidi Bobbidi",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":332,
    "MapParentID":8,
    "ParentID":8,
    "TagID":14,
    "TagName":"Food Allergies",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":332,
    "MapParentID":8,
    "ParentID":8,
    "TagID":14,
    "TagName":"Alergias a los alimentos",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":332,
    "MapParentID":8,
    "ParentID":8,
    "TagID":14,
    "TagName":"Allergies alimentaires",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":332,
    "MapParentID":8,
    "ParentID":8,
    "TagID":14,
    "TagName":"Alergias alimentares",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":333,
    "MapParentID":50,
    "ParentID":63,
    "TagID":209,
    "TagName":"Food and Wine",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":333,
    "MapParentID":50,
    "ParentID":63,
    "TagID":209,
    "TagName":"Gastronomía y vinos",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":333,
    "MapParentID":50,
    "ParentID":63,
    "TagID":209,
    "TagName":"Gastronomie et vin",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":333,
    "MapParentID":50,
    "ParentID":63,
    "TagID":209,
    "TagName":"Food and Wine",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":334,
    "MapParentID":276,
    "ParentID":198,
    "TagID":200,
    "TagName":"Valet Parking",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":334,
    "MapParentID":276,
    "ParentID":198,
    "TagID":200,
    "TagName":"Valet parking",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":334,
    "MapParentID":276,
    "ParentID":198,
    "TagID":200,
    "TagName":"Service de voiturier",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":334,
    "MapParentID":276,
    "ParentID":198,
    "TagID":200,
    "TagName":"Service de voiturier",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":335,
    "MapParentID":276,
    "ParentID":198,
    "TagID":52,
    "TagName":"Amenities",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":335,
    "MapParentID":276,
    "ParentID":198,
    "TagID":52,
    "TagName":"Servicios",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":335,
    "MapParentID":276,
    "ParentID":198,
    "TagID":52,
    "TagName":"Commodités",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":335,
    "MapParentID":276,
    "ParentID":198,
    "TagID":52,
    "TagName":"Comodidades",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":336,
    "MapParentID":276,
    "ParentID":198,
    "TagID":28,
    "TagName":"Parking",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":336,
    "MapParentID":276,
    "ParentID":198,
    "TagID":28,
    "TagName":"Estacionamiento",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":336,
    "MapParentID":276,
    "ParentID":198,
    "TagID":28,
    "TagName":"Aire de stationnement",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":336,
    "MapParentID":276,
    "ParentID":198,
    "TagID":28,
    "TagName":"Estacionamento",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":337,
    "MapParentID":276,
    "ParentID":198,
    "TagID":53,
    "TagName":"Pools",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":337,
    "MapParentID":276,
    "ParentID":198,
    "TagID":53,
    "TagName":"Piscinas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":337,
    "MapParentID":276,
    "ParentID":198,
    "TagID":53,
    "TagName":"Piscines",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":337,
    "MapParentID":276,
    "ParentID":198,
    "TagID":53,
    "TagName":"Piscinas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":338,
    "MapParentID":276,
    "ParentID":198,
    "TagID":54,
    "TagName":"Transportation",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":338,
    "MapParentID":276,
    "ParentID":198,
    "TagID":54,
    "TagName":"Transporte",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":338,
    "MapParentID":276,
    "ParentID":198,
    "TagID":54,
    "TagName":"Transport",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":338,
    "MapParentID":276,
    "ParentID":198,
    "TagID":54,
    "TagName":"Transporte",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":339,
    "MapParentID":276,
    "ParentID":198,
    "TagID":55,
    "TagName":"Features",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":339,
    "MapParentID":276,
    "ParentID":198,
    "TagID":55,
    "TagName":"Características",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":339,
    "MapParentID":276,
    "ParentID":198,
    "TagID":55,
    "TagName":"Caractéristiques",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":339,
    "MapParentID":276,
    "ParentID":198,
    "TagID":55,
    "TagName":"Recursos",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":340,
    "MapParentID":276,
    "ParentID":198,
    "TagID":56,
    "TagName":"Kitchens",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":340,
    "MapParentID":276,
    "ParentID":198,
    "TagID":56,
    "TagName":"Cocinas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":340,
    "MapParentID":276,
    "ParentID":198,
    "TagID":56,
    "TagName":"Cuisines",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":340,
    "MapParentID":276,
    "ParentID":198,
    "TagID":56,
    "TagName":"Cozinhas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":341,
    "MapParentID":48,
    "ParentID":48,
    "TagID":169,
    "TagName":"Adults",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":341,
    "MapParentID":48,
    "ParentID":48,
    "TagID":169,
    "TagName":"Adultos",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":341,
    "MapParentID":48,
    "ParentID":48,
    "TagID":169,
    "TagName":"Adultes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":341,
    "MapParentID":48,
    "ParentID":48,
    "TagID":169,
    "TagName":"Adultos",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":342,
    "MapParentID":48,
    "ParentID":48,
    "TagID":231,
    "TagName":"Conventions",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":342,
    "MapParentID":48,
    "ParentID":48,
    "TagID":231,
    "TagName":"Convenciones",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":342,
    "MapParentID":48,
    "ParentID":48,
    "TagID":231,
    "TagName":"Congrès",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":342,
    "MapParentID":48,
    "ParentID":48,
    "TagID":231,
    "TagName":"Convenções",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":343,
    "MapParentID":50,
    "ParentID":63,
    "TagID":233,
    "TagName":"Jedi Training",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":343,
    "MapParentID":50,
    "ParentID":63,
    "TagID":233,
    "TagName":"Entrenamiento Jedi",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":343,
    "MapParentID":50,
    "ParentID":63,
    "TagID":233,
    "TagName":"Entraînement Jedi",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":343,
    "MapParentID":50,
    "ParentID":63,
    "TagID":233,
    "TagName":"Treinamento Jedi",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":344,
    "MapParentID":276,
    "ParentID":198,
    "TagID":232,
    "TagName":"Bell Services",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":344,
    "MapParentID":276,
    "ParentID":198,
    "TagID":232,
    "TagName":"Servicios de botones",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":344,
    "MapParentID":276,
    "ParentID":198,
    "TagID":232,
    "TagName":"Services Bell",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":344,
    "MapParentID":276,
    "ParentID":198,
    "TagID":232,
    "TagName":"Serviços de mensageiro",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":345,
    "MapParentID":276,
    "ParentID":198,
    "TagID":175,
    "TagName":"Spas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":345,
    "MapParentID":276,
    "ParentID":198,
    "TagID":175,
    "TagName":"Spas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":345,
    "MapParentID":276,
    "ParentID":198,
    "TagID":175,
    "TagName":"Centres de beauté",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":345,
    "MapParentID":276,
    "ParentID":198,
    "TagID":175,
    "TagName":"Spas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":346,
    "MapParentID":276,
    "ParentID":198,
    "TagID":234,
    "TagName":"Online Check-in",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":346,
    "MapParentID":276,
    "ParentID":198,
    "TagID":234,
    "TagName":"Check in en línea",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":346,
    "MapParentID":276,
    "ParentID":198,
    "TagID":234,
    "TagName":"Inscription en ligne",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":346,
    "MapParentID":276,
    "ParentID":198,
    "TagID":234,
    "TagName":"Check-in on-line",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":347,
    "MapParentID":276,
    "ParentID":198,
    "TagID":235,
    "TagName":"Connecting Rooms",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":347,
    "MapParentID":276,
    "ParentID":198,
    "TagID":235,
    "TagName":"Habitaciones comunicadas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":347,
    "MapParentID":276,
    "ParentID":198,
    "TagID":235,
    "TagName":"Chambres communicantes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":347,
    "MapParentID":276,
    "ParentID":198,
    "TagID":235,
    "TagName":"Quartos conjugados",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":348,
    "MapParentID":46,
    "ParentID":24,
    "TagID":236,
    "TagName":"Disney Parks Blog",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":348,
    "MapParentID":46,
    "ParentID":24,
    "TagID":236,
    "TagName":"Blog Disney Parks",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":348,
    "MapParentID":46,
    "ParentID":24,
    "TagID":236,
    "TagName":"Blogue des parcs Disney",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":348,
    "MapParentID":46,
    "ParentID":24,
    "TagID":236,
    "TagName":"Blog dos parques da Disney",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":349,
    "MapParentID":276,
    "ParentID":198,
    "TagID":237,
    "TagName":"Fitness Centers",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":349,
    "MapParentID":276,
    "ParentID":198,
    "TagID":237,
    "TagName":"Gimnasios",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":349,
    "MapParentID":276,
    "ParentID":198,
    "TagID":237,
    "TagName":"Centre de conditionnement physique",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":349,
    "MapParentID":276,
    "ParentID":198,
    "TagID":237,
    "TagName":"Academias de ginástica",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":350,
    "MapParentID":49,
    "ParentID":49,
    "TagID":54,
    "TagName":"Transportation",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":350,
    "MapParentID":49,
    "ParentID":49,
    "TagID":54,
    "TagName":"Transporte",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":350,
    "MapParentID":49,
    "ParentID":49,
    "TagID":54,
    "TagName":"Transport",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":350,
    "MapParentID":49,
    "ParentID":49,
    "TagID":54,
    "TagName":"Transporte",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":351,
    "MapParentID":49,
    "ParentID":49,
    "TagID":238,
    "TagName":"Guest Services",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":351,
    "MapParentID":49,
    "ParentID":49,
    "TagID":238,
    "TagName":"Servicios para Huéspedes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":351,
    "MapParentID":49,
    "ParentID":49,
    "TagID":238,
    "TagName":"Services à la clientèle",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":351,
    "MapParentID":49,
    "ParentID":49,
    "TagID":238,
    "TagName":"Serviços para visitantes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":352,
    "MapParentID":50,
    "ParentID":63,
    "TagID":239,
    "TagName":"Flower & Garden",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":352,
    "MapParentID":50,
    "ParentID":63,
    "TagID":239,
    "TagName":"Flower & Garden",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":352,
    "MapParentID":50,
    "ParentID":63,
    "TagID":239,
    "TagName":"Fleur et jardin",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":352,
    "MapParentID":50,
    "ParentID":63,
    "TagID":239,
    "TagName":"Flores e jardins",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":353,
    "MapParentID":51,
    "ParentID":71,
    "TagID":240,
    "TagName":"Floral & Gifts",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":353,
    "MapParentID":51,
    "ParentID":71,
    "TagID":240,
    "TagName":"Floral & Gifts",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":353,
    "MapParentID":51,
    "ParentID":71,
    "TagID":240,
    "TagName":"Fleurs et cadeaux",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":353,
    "MapParentID":51,
    "ParentID":71,
    "TagID":240,
    "TagName":"Flores e presentes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":354,
    "MapParentID":8,
    "ParentID":8,
    "TagID":241,
    "TagName":"Dietary Restrictions",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":354,
    "MapParentID":8,
    "ParentID":8,
    "TagID":241,
    "TagName":"Restricciones alimentarias",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":354,
    "MapParentID":8,
    "ParentID":8,
    "TagID":241,
    "TagName":"Restrictions alimentaires",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":354,
    "MapParentID":8,
    "ParentID":8,
    "TagID":241,
    "TagName":"Restrições alimentares",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":355,
    "MapParentID":48,
    "ParentID":48,
    "TagID":86,
    "TagName":"Travel",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":355,
    "MapParentID":48,
    "ParentID":48,
    "TagID":86,
    "TagName":"Viajar",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":355,
    "MapParentID":48,
    "ParentID":48,
    "TagID":86,
    "TagName":"Voyage",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":355,
    "MapParentID":48,
    "ParentID":48,
    "TagID":86,
    "TagName":"Viagem",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":356,
    "MapParentID":48,
    "ParentID":48,
    "TagID":118,
    "TagName":"Health and Wellness",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":356,
    "MapParentID":48,
    "ParentID":48,
    "TagID":118,
    "TagName":"Salud y bienestar",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":356,
    "MapParentID":48,
    "ParentID":48,
    "TagID":118,
    "TagName":"Santé et bien-être",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":356,
    "MapParentID":48,
    "ParentID":48,
    "TagID":118,
    "TagName":"Saúde e bem-estar",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":357,
    "MapParentID":49,
    "ParentID":49,
    "TagID":242,
    "TagName":"Extra Magic Hours",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":357,
    "MapParentID":49,
    "ParentID":49,
    "TagID":242,
    "TagName":"Extra Magic Hours",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":357,
    "MapParentID":49,
    "ParentID":49,
    "TagID":242,
    "TagName":"Heures Magiques Supplémentaires",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":357,
    "MapParentID":49,
    "ParentID":49,
    "TagID":242,
    "TagName":"Horas Mágicas Extras",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":358,
    "MapParentID":8,
    "ParentID":8,
    "TagID":243,
    "TagName":"Kids Menus",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":359,
    "MapParentID":48,
    "ParentID":48,
    "TagID":244,
    "TagName":"Easter",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":360,
    "MapParentID":50,
    "ParentID":63,
    "TagID":245,
    "TagName":"La Nouba",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":360,
    "MapParentID":50,
    "ParentID":63,
    "TagID":245,
    "TagName":"La Nouba",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":360,
    "MapParentID":50,
    "ParentID":63,
    "TagID":245,
    "TagName":"La Nouba",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":360,
    "MapParentID":50,
    "ParentID":63,
    "TagID":245,
    "TagName":"La Nouba",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":361,
    "MapParentID":101,
    "ParentID":48,
    "TagID":246,
    "TagName":"Diamond Celebration",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":362,
    "MapParentID":200,
    "ParentID":63,
    "TagID":247,
    "TagName":"Spring Training",
    "TopParentID":3,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":54,
    "MapParentID":46,
    "ParentID":24,
    "TagID":25,
    "TagName":"How To Be a Panelist",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":54,
    "MapParentID":46,
    "ParentID":24,
    "TagID":25,
    "TagName":"Cómo ser un panelista",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":54,
    "MapParentID":46,
    "ParentID":24,
    "TagID":25,
    "TagName":"Comment faire partie des panélistes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":54,
    "MapParentID":46,
    "ParentID":24,
    "TagID":25,
    "TagName":"Como se tornar um participante",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":58,
    "MapParentID":47,
    "ParentID":47,
    "TagID":28,
    "TagName":"Parking",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":58,
    "MapParentID":47,
    "ParentID":47,
    "TagID":28,
    "TagName":"Estacionamiento",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":58,
    "MapParentID":47,
    "ParentID":47,
    "TagID":28,
    "TagName":"Aire de stationnement",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":58,
    "MapParentID":47,
    "ParentID":47,
    "TagID":28,
    "TagName":"Estacionamento",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":60,
    "MapParentID":47,
    "ParentID":47,
    "TagID":30,
    "TagName":"Pets",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":60,
    "MapParentID":47,
    "ParentID":47,
    "TagID":30,
    "TagName":"Mascotas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":60,
    "MapParentID":47,
    "ParentID":47,
    "TagID":30,
    "TagName":"Animaux de compagnie",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":60,
    "MapParentID":47,
    "ParentID":47,
    "TagID":30,
    "TagName":"Animais de estimação",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":61,
    "MapParentID":47,
    "ParentID":47,
    "TagID":31,
    "TagName":"Pin Trading",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":61,
    "MapParentID":47,
    "ParentID":47,
    "TagID":31,
    "TagName":"Pin Trading",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":61,
    "MapParentID":47,
    "ParentID":47,
    "TagID":31,
    "TagName":"Échange d'épinglettes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":61,
    "MapParentID":47,
    "ParentID":47,
    "TagID":31,
    "TagName":"Troca de bótons",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":62,
    "MapParentID":48,
    "ParentID":48,
    "TagID":32,
    "TagName":"My Disney Experience",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":62,
    "MapParentID":48,
    "ParentID":48,
    "TagID":32,
    "TagName":"My Disney Experience",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":62,
    "MapParentID":48,
    "ParentID":48,
    "TagID":32,
    "TagName":"My Disney Experience",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":62,
    "MapParentID":48,
    "ParentID":48,
    "TagID":32,
    "TagName":"My Disney Experience",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":63,
    "MapParentID":48,
    "ParentID":48,
    "TagID":33,
    "TagName":"Planning Tools",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":63,
    "MapParentID":48,
    "ParentID":48,
    "TagID":33,
    "TagName":"Herramientas de planificación",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":63,
    "MapParentID":48,
    "ParentID":48,
    "TagID":33,
    "TagName":"Outils de planification",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":63,
    "MapParentID":48,
    "ParentID":48,
    "TagID":33,
    "TagName":"Ferramentas para planejamento",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":64,
    "MapParentID":48,
    "ParentID":48,
    "TagID":34,
    "TagName":"Disabilities",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":64,
    "MapParentID":48,
    "ParentID":48,
    "TagID":34,
    "TagName":"Discapacidades",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":64,
    "MapParentID":48,
    "ParentID":48,
    "TagID":34,
    "TagName":"Handicaps",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":64,
    "MapParentID":48,
    "ParentID":48,
    "TagID":34,
    "TagName":"Necessidades especiais",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":65,
    "MapParentID":48,
    "ParentID":48,
    "TagID":35,
    "TagName":"Infants",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":65,
    "MapParentID":48,
    "ParentID":48,
    "TagID":35,
    "TagName":"Niños pequeños",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":65,
    "MapParentID":48,
    "ParentID":48,
    "TagID":35,
    "TagName":"Enfants en bas âge",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":65,
    "MapParentID":48,
    "ParentID":48,
    "TagID":35,
    "TagName":"Bebês",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":66,
    "MapParentID":48,
    "ParentID":48,
    "TagID":36,
    "TagName":"Preschoolers",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":66,
    "MapParentID":48,
    "ParentID":48,
    "TagID":36,
    "TagName":"Niños en edad preescolar",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":66,
    "MapParentID":48,
    "ParentID":48,
    "TagID":36,
    "TagName":"Enfants d’âge préscolaire",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":66,
    "MapParentID":48,
    "ParentID":48,
    "TagID":36,
    "TagName":"Crianças pequenas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":67,
    "MapParentID":48,
    "ParentID":48,
    "TagID":37,
    "TagName":"Kids",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":67,
    "MapParentID":48,
    "ParentID":48,
    "TagID":37,
    "TagName":"Niños",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":67,
    "MapParentID":48,
    "ParentID":48,
    "TagID":37,
    "TagName":"Enfants",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":67,
    "MapParentID":48,
    "ParentID":48,
    "TagID":37,
    "TagName":"Crianças",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":68,
    "MapParentID":48,
    "ParentID":48,
    "TagID":38,
    "TagName":"Tweens",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":68,
    "MapParentID":48,
    "ParentID":48,
    "TagID":38,
    "TagName":"Preadolescentes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":68,
    "MapParentID":48,
    "ParentID":48,
    "TagID":38,
    "TagName":"Préadolescents",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":68,
    "MapParentID":48,
    "ParentID":48,
    "TagID":38,
    "TagName":"Pré-adolescentes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":69,
    "MapParentID":48,
    "ParentID":48,
    "TagID":39,
    "TagName":"Teens",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":69,
    "MapParentID":48,
    "ParentID":48,
    "TagID":39,
    "TagName":"Adolescentes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":69,
    "MapParentID":48,
    "ParentID":48,
    "TagID":39,
    "TagName":"Adolescents",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":69,
    "MapParentID":48,
    "ParentID":48,
    "TagID":39,
    "TagName":"Adolescentes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":70,
    "MapParentID":48,
    "ParentID":48,
    "TagID":40,
    "TagName":"Budgeting",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":70,
    "MapParentID":48,
    "ParentID":48,
    "TagID":40,
    "TagName":"Cálculo de presupuestos",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":70,
    "MapParentID":48,
    "ParentID":48,
    "TagID":40,
    "TagName":"Élaboration du budget",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":70,
    "MapParentID":48,
    "ParentID":48,
    "TagID":40,
    "TagName":"Orçando",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":71,
    "MapParentID":48,
    "ParentID":48,
    "TagID":41,
    "TagName":"Seasons",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":71,
    "MapParentID":48,
    "ParentID":48,
    "TagID":41,
    "TagName":"Temporadas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":71,
    "MapParentID":48,
    "ParentID":48,
    "TagID":41,
    "TagName":"Saisons",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":71,
    "MapParentID":48,
    "ParentID":48,
    "TagID":41,
    "TagName":"Estações",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":72,
    "MapParentID":48,
    "ParentID":48,
    "TagID":42,
    "TagName":"Weather",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":72,
    "MapParentID":48,
    "ParentID":48,
    "TagID":42,
    "TagName":"Clima",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":72,
    "MapParentID":48,
    "ParentID":48,
    "TagID":42,
    "TagName":"Météo",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":72,
    "MapParentID":48,
    "ParentID":48,
    "TagID":42,
    "TagName":"Clima",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":73,
    "MapParentID":48,
    "ParentID":48,
    "TagID":43,
    "TagName":"Large Parties",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":73,
    "MapParentID":48,
    "ParentID":48,
    "TagID":43,
    "TagName":"Grupos grandes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":73,
    "MapParentID":48,
    "ParentID":48,
    "TagID":43,
    "TagName":"Grands groupes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":73,
    "MapParentID":48,
    "ParentID":48,
    "TagID":43,
    "TagName":"Grupos grandes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":74,
    "MapParentID":49,
    "ParentID":49,
    "TagID":44,
    "TagName":"Magic Kingdom",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":74,
    "MapParentID":49,
    "ParentID":49,
    "TagID":44,
    "TagName":"Magic Kingdom",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":74,
    "MapParentID":49,
    "ParentID":49,
    "TagID":44,
    "TagName":"Magic Kingdom",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":74,
    "MapParentID":49,
    "ParentID":49,
    "TagID":44,
    "TagName":"Magic Kingdom",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":75,
    "MapParentID":49,
    "ParentID":49,
    "TagID":45,
    "TagName":"Epcot",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":75,
    "MapParentID":49,
    "ParentID":49,
    "TagID":45,
    "TagName":"Epcot",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":75,
    "MapParentID":49,
    "ParentID":49,
    "TagID":45,
    "TagName":"Epcot",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":75,
    "MapParentID":49,
    "ParentID":49,
    "TagID":45,
    "TagName":"Epcot",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":76,
    "MapParentID":49,
    "ParentID":49,
    "TagID":50,
    "TagName":"Disney's Hollywood Studios",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":76,
    "MapParentID":49,
    "ParentID":49,
    "TagID":50,
    "TagName":"Disney's Hollywood Studios",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":76,
    "MapParentID":49,
    "ParentID":49,
    "TagID":50,
    "TagName":"Disney's Hollywood Studios",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":76,
    "MapParentID":49,
    "ParentID":49,
    "TagID":50,
    "TagName":"Disney's Hollywood Studios",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":77,
    "MapParentID":49,
    "ParentID":49,
    "TagID":51,
    "TagName":"Disney's Animal Kingdom",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":77,
    "MapParentID":49,
    "ParentID":49,
    "TagID":51,
    "TagName":"Disney's Animal Kingdom",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":77,
    "MapParentID":49,
    "ParentID":49,
    "TagID":51,
    "TagName":"Disney's Animal Kingdom",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":77,
    "MapParentID":49,
    "ParentID":49,
    "TagID":51,
    "TagName":"Disney's Animal Kingdom",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":78,
    "MapParentID":198,
    "ParentID":198,
    "TagID":52,
    "TagName":"Amenities",
    "TopParentID":3,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":83,
    "MapParentID":50,
    "ParentID":63,
    "TagID":64,
    "TagName":"Attractions",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":83,
    "MapParentID":50,
    "ParentID":63,
    "TagID":64,
    "TagName":"Atracciones",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":83,
    "MapParentID":50,
    "ParentID":63,
    "TagID":64,
    "TagName":"Attractions",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":83,
    "MapParentID":50,
    "ParentID":63,
    "TagID":64,
    "TagName":"Atrações",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":84,
    "MapParentID":50,
    "ParentID":63,
    "TagID":65,
    "TagName":"Entertainment",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":84,
    "MapParentID":50,
    "ParentID":63,
    "TagID":65,
    "TagName":"Entretenimiento",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":84,
    "MapParentID":50,
    "ParentID":63,
    "TagID":65,
    "TagName":"Divertissements",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":84,
    "MapParentID":50,
    "ParentID":63,
    "TagID":65,
    "TagName":"Entretenimento",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":85,
    "MapParentID":50,
    "ParentID":63,
    "TagID":66,
    "TagName":"Events and Tours",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":85,
    "MapParentID":50,
    "ParentID":63,
    "TagID":66,
    "TagName":"Eventos y tours",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":85,
    "MapParentID":50,
    "ParentID":63,
    "TagID":66,
    "TagName":"Événements et visites",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":85,
    "MapParentID":50,
    "ParentID":63,
    "TagID":66,
    "TagName":"Eventos e passeios",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":86,
    "MapParentID":50,
    "ParentID":63,
    "TagID":67,
    "TagName":"Parades",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":86,
    "MapParentID":50,
    "ParentID":63,
    "TagID":67,
    "TagName":"Desfiles",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":86,
    "MapParentID":50,
    "ParentID":63,
    "TagID":67,
    "TagName":"Parades",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":86,
    "MapParentID":50,
    "ParentID":63,
    "TagID":67,
    "TagName":"Desfiles",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":87,
    "MapParentID":50,
    "ParentID":63,
    "TagID":68,
    "TagName":"Fireworks",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":87,
    "MapParentID":50,
    "ParentID":63,
    "TagID":68,
    "TagName":"Fuegos artificiales",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":87,
    "MapParentID":50,
    "ParentID":63,
    "TagID":68,
    "TagName":"Feux d’artifice",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":87,
    "MapParentID":50,
    "ParentID":63,
    "TagID":68,
    "TagName":"Fogos de artifício",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":88,
    "MapParentID":50,
    "ParentID":63,
    "TagID":69,
    "TagName":"Rides",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":88,
    "MapParentID":50,
    "ParentID":63,
    "TagID":69,
    "TagName":"Paseos",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":88,
    "MapParentID":50,
    "ParentID":63,
    "TagID":69,
    "TagName":"Manèges",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":88,
    "MapParentID":50,
    "ParentID":63,
    "TagID":69,
    "TagName":"Passeios",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":89,
    "MapParentID":50,
    "ParentID":63,
    "TagID":70,
    "TagName":"Character Experiences",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":89,
    "MapParentID":50,
    "ParentID":63,
    "TagID":70,
    "TagName":"Experiencias con los personajes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":89,
    "MapParentID":50,
    "ParentID":63,
    "TagID":70,
    "TagName":"Rencontres des personnages",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":89,
    "MapParentID":50,
    "ParentID":63,
    "TagID":70,
    "TagName":"Experiências com personagens",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":90,
    "MapParentID":51,
    "ParentID":71,
    "TagID":72,
    "TagName":"Disney Springs",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":90,
    "MapParentID":51,
    "ParentID":71,
    "TagID":72,
    "TagName":"Disney Springs",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":90,
    "MapParentID":51,
    "ParentID":71,
    "TagID":72,
    "TagName":"Disney Springs",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":90,
    "MapParentID":51,
    "ParentID":71,
    "TagID":72,
    "TagName":"Disney Springs",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":91,
    "MapParentID":51,
    "ParentID":71,
    "TagID":73,
    "TagName":"Gift Cards and Disney Dollars",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":91,
    "MapParentID":51,
    "ParentID":71,
    "TagID":73,
    "TagName":"Tarjetas de regalo y dólares de Disney",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":91,
    "MapParentID":51,
    "ParentID":71,
    "TagID":73,
    "TagName":"Cartes-cadeaux et Dollars Disney",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":91,
    "MapParentID":51,
    "ParentID":71,
    "TagID":73,
    "TagName":"Cartões de presente e Disney Dollars",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":92,
    "MapParentID":51,
    "ParentID":71,
    "TagID":74,
    "TagName":"Merchandise",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":92,
    "MapParentID":51,
    "ParentID":71,
    "TagID":74,
    "TagName":"Productos",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":92,
    "MapParentID":51,
    "ParentID":71,
    "TagID":74,
    "TagName":"Articles",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":92,
    "MapParentID":51,
    "ParentID":71,
    "TagID":74,
    "TagName":"Produtos",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":93,
    "MapParentID":52,
    "ParentID":75,
    "TagID":76,
    "TagName":"FastPass+",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":93,
    "MapParentID":52,
    "ParentID":75,
    "TagID":76,
    "TagName":"FastPass+",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":93,
    "MapParentID":52,
    "ParentID":75,
    "TagID":76,
    "TagName":"FastPass+",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":93,
    "MapParentID":52,
    "ParentID":75,
    "TagID":76,
    "TagName":"FastPass+",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":94,
    "MapParentID":52,
    "ParentID":75,
    "TagID":77,
    "TagName":"Annual Passes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":94,
    "MapParentID":52,
    "ParentID":75,
    "TagID":77,
    "TagName":"Pases anuales",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":94,
    "MapParentID":52,
    "ParentID":75,
    "TagID":77,
    "TagName":"Laissez-passer annuels",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":94,
    "MapParentID":52,
    "ParentID":75,
    "TagID":77,
    "TagName":"Passes anuais",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":95,
    "MapParentID":52,
    "ParentID":75,
    "TagID":78,
    "TagName":"Expiration",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":95,
    "MapParentID":52,
    "ParentID":75,
    "TagID":78,
    "TagName":"Vencimiento",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":95,
    "MapParentID":52,
    "ParentID":75,
    "TagID":78,
    "TagName":"Expiration",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":95,
    "MapParentID":52,
    "ParentID":75,
    "TagID":78,
    "TagName":"Validade",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":96,
    "MapParentID":52,
    "ParentID":75,
    "TagID":79,
    "TagName":"Florida Resident",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":96,
    "MapParentID":52,
    "ParentID":75,
    "TagID":79,
    "TagName":"Residente de la Florida",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":96,
    "MapParentID":52,
    "ParentID":75,
    "TagID":79,
    "TagName":"Résident de la Floride",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":96,
    "MapParentID":52,
    "ParentID":75,
    "TagID":79,
    "TagName":"Residente da Flórida",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":97,
    "MapParentID":52,
    "ParentID":75,
    "TagID":80,
    "TagName":"Options",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":97,
    "MapParentID":52,
    "ParentID":75,
    "TagID":80,
    "TagName":"Opciones",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":97,
    "MapParentID":52,
    "ParentID":75,
    "TagID":80,
    "TagName":"Options",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":97,
    "MapParentID":52,
    "ParentID":75,
    "TagID":80,
    "TagName":"Opções",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":98,
    "MapParentID":52,
    "ParentID":75,
    "TagID":81,
    "TagName":"Park Hopper/Water Parks",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":98,
    "MapParentID":52,
    "ParentID":75,
    "TagID":81,
    "TagName":"Park Hopper/Parques Acuáticos",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":98,
    "MapParentID":52,
    "ParentID":75,
    "TagID":81,
    "TagName":"Park Hopper/Parcs aquatiques",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":98,
    "MapParentID":52,
    "ParentID":75,
    "TagID":81,
    "TagName":"Park Hopper/Parques aquáticos",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":222,
    "MapParentID":221,
    "ParentID":160,
    "TagID":161,
    "TagName":"Birthdays",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":222,
    "MapParentID":221,
    "ParentID":160,
    "TagID":161,
    "TagName":"Cumpleaños",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":222,
    "MapParentID":221,
    "ParentID":160,
    "TagID":161,
    "TagName":"Fêtes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":222,
    "MapParentID":221,
    "ParentID":160,
    "TagID":161,
    "TagName":"Aniversários",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":223,
    "MapParentID":221,
    "ParentID":160,
    "TagID":162,
    "TagName":"Graduations",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":223,
    "MapParentID":221,
    "ParentID":160,
    "TagID":162,
    "TagName":"Graduaciones",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":223,
    "MapParentID":221,
    "ParentID":160,
    "TagID":162,
    "TagName":"Remises des diplômes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":223,
    "MapParentID":221,
    "ParentID":160,
    "TagID":162,
    "TagName":"Formaturas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":224,
    "MapParentID":221,
    "ParentID":160,
    "TagID":163,
    "TagName":"Quinceaneras",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":224,
    "MapParentID":221,
    "ParentID":160,
    "TagID":163,
    "TagName":"Quinceañeras",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":224,
    "MapParentID":221,
    "ParentID":160,
    "TagID":163,
    "TagName":"Quinceaneras",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":224,
    "MapParentID":221,
    "ParentID":160,
    "TagID":163,
    "TagName":"Debutantes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":225,
    "MapParentID":221,
    "ParentID":160,
    "TagID":164,
    "TagName":"Anniversaries",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":225,
    "MapParentID":221,
    "ParentID":160,
    "TagID":164,
    "TagName":"Aniversarios",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":225,
    "MapParentID":221,
    "ParentID":160,
    "TagID":164,
    "TagName":"Anniversaires",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":225,
    "MapParentID":221,
    "ParentID":160,
    "TagID":164,
    "TagName":"Datas especiais",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":226,
    "MapParentID":221,
    "ParentID":160,
    "TagID":165,
    "TagName":"Weddings",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":226,
    "MapParentID":221,
    "ParentID":160,
    "TagID":165,
    "TagName":"Bodas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":226,
    "MapParentID":221,
    "ParentID":160,
    "TagID":165,
    "TagName":"Mariages",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":226,
    "MapParentID":221,
    "ParentID":160,
    "TagID":165,
    "TagName":"Casamentos",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":227,
    "MapParentID":221,
    "ParentID":160,
    "TagID":166,
    "TagName":"Honeymoons",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":227,
    "MapParentID":221,
    "ParentID":160,
    "TagID":166,
    "TagName":"Lunas de miel",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":227,
    "MapParentID":221,
    "ParentID":160,
    "TagID":166,
    "TagName":"Lunes de miel",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":227,
    "MapParentID":221,
    "ParentID":160,
    "TagID":166,
    "TagName":"Luas-de-mel",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":228,
    "MapParentID":102,
    "ParentID":49,
    "TagID":59,
    "TagName":"Downtown Disney",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":229,
    "MapParentID":153,
    "ParentID":47,
    "TagID":119,
    "TagName":"Just for Adults",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":230,
    "MapParentID":153,
    "ParentID":47,
    "TagID":159,
    "TagName":"Health",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":231,
    "MapParentID":156,
    "ParentID":63,
    "TagID":35,
    "TagName":"Infants",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":232,
    "MapParentID":156,
    "ParentID":63,
    "TagID":36,
    "TagName":"Preschoolers",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":233,
    "MapParentID":156,
    "ParentID":63,
    "TagID":37,
    "TagName":"Kids",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":234,
    "MapParentID":156,
    "ParentID":63,
    "TagID":38,
    "TagName":"Tweens",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":235,
    "MapParentID":156,
    "ParentID":63,
    "TagID":39,
    "TagName":"Teens",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":236,
    "MapParentID":156,
    "ParentID":63,
    "TagID":65,
    "TagName":"Entertainment",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":237,
    "MapParentID":156,
    "ParentID":63,
    "TagID":169,
    "TagName":"Adults",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":202,
    "MapParentID":201,
    "ParentID":75,
    "TagID":155,
    "TagName":"Complex and Event Admission",
    "TopParentID":3,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":203,
    "MapParentID":201,
    "ParentID":75,
    "TagID":156,
    "TagName":"Spectator Events",
    "TopParentID":3,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":204,
    "MapParentID":200,
    "ParentID":63,
    "TagID":154,
    "TagName":"Fun Off the Field",
    "TopParentID":3,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":205,
    "MapParentID":199,
    "ParentID":48,
    "TagID":54,
    "TagName":"Transportation",
    "TopParentID":3,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":206,
    "MapParentID":199,
    "ParentID":48,
    "TagID":150,
    "TagName":"Budgeting and Fundraising",
    "TopParentID":3,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":207,
    "MapParentID":199,
    "ParentID":48,
    "TagID":151,
    "TagName":"Team Travel Planning",
    "TopParentID":3,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":208,
    "MapParentID":198,
    "ParentID":47,
    "TagID":147,
    "TagName":"Commemorate your Competition",
    "TopParentID":3,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":209,
    "MapParentID":198,
    "ParentID":47,
    "TagID":148,
    "TagName":"Share Your Experience",
    "TopParentID":3,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":210,
    "MapParentID":198,
    "ParentID":47,
    "TagID":149,
    "TagName":"On-site Services",
    "TopParentID":3,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":211,
    "MapParentID":197,
    "ParentID":24,
    "TagID":25,
    "TagName":"How To Be a Panelist",
    "TopParentID":3,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":217,
    "MapParentID":49,
    "ParentID":49,
    "TagID":28,
    "TagName":"Parking",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":217,
    "MapParentID":49,
    "ParentID":49,
    "TagID":28,
    "TagName":"Estacionamiento",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":217,
    "MapParentID":49,
    "ParentID":49,
    "TagID":28,
    "TagName":"Aire de stationnement",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":217,
    "MapParentID":49,
    "ParentID":49,
    "TagID":28,
    "TagName":"Estacionamento",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":218,
    "MapParentID":8,
    "ParentID":8,
    "TagID":72,
    "TagName":"Disney Springs",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":218,
    "MapParentID":8,
    "ParentID":8,
    "TagID":72,
    "TagName":"Disney Springs",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":218,
    "MapParentID":8,
    "ParentID":8,
    "TagID":72,
    "TagName":"Disney Springs",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":218,
    "MapParentID":8,
    "ParentID":8,
    "TagID":72,
    "TagName":"Disney Springs",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":219,
    "MapParentID":8,
    "ParentID":8,
    "TagID":158,
    "TagName":"Food",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":219,
    "MapParentID":8,
    "ParentID":8,
    "TagID":158,
    "TagName":"Comida",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":219,
    "MapParentID":8,
    "ParentID":8,
    "TagID":158,
    "TagName":"Nourriture",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":219,
    "MapParentID":8,
    "ParentID":8,
    "TagID":158,
    "TagName":"Alimentação",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":220,
    "MapParentID":47,
    "ParentID":47,
    "TagID":159,
    "TagName":"Health",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":220,
    "MapParentID":47,
    "ParentID":47,
    "TagID":159,
    "TagName":"Salud",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":220,
    "MapParentID":47,
    "ParentID":47,
    "TagID":159,
    "TagName":"Santé",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":220,
    "MapParentID":47,
    "ParentID":47,
    "TagID":159,
    "TagName":"Saúde",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":162,
    "MapParentID":155,
    "ParentID":49,
    "TagID":123,
    "TagName":"Castaway Cay",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":163,
    "MapParentID":12,
    "ParentID":8,
    "TagID":124,
    "TagName":"Dress",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":164,
    "MapParentID":12,
    "ParentID":8,
    "TagID":125,
    "TagName":"Seating Times",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":165,
    "MapParentID":154,
    "ParentID":48,
    "TagID":33,
    "TagName":"Planning Tools",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":166,
    "MapParentID":154,
    "ParentID":48,
    "TagID":35,
    "TagName":"Infants",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":167,
    "MapParentID":154,
    "ParentID":48,
    "TagID":36,
    "TagName":"Preschoolers",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":168,
    "MapParentID":154,
    "ParentID":48,
    "TagID":37,
    "TagName":"Kids",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":169,
    "MapParentID":154,
    "ParentID":48,
    "TagID":38,
    "TagName":"Tweens",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":170,
    "MapParentID":154,
    "ParentID":48,
    "TagID":39,
    "TagName":"Teens",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":171,
    "MapParentID":154,
    "ParentID":48,
    "TagID":43,
    "TagName":"Large Parties",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":172,
    "MapParentID":154,
    "ParentID":48,
    "TagID":121,
    "TagName":"Itineraries",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":173,
    "MapParentID":152,
    "ParentID":24,
    "TagID":25,
    "TagName":"How To Be a Panelist",
    "TopParentID":5,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":107,
    "MapParentID":105,
    "ParentID":75,
    "TagID":76,
    "TagName":"FastPass+",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":108,
    "MapParentID":105,
    "ParentID":75,
    "TagID":77,
    "TagName":"Annual Passes",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":109,
    "MapParentID":105,
    "ParentID":75,
    "TagID":78,
    "TagName":"Expiration",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":110,
    "MapParentID":105,
    "ParentID":75,
    "TagID":80,
    "TagName":"Options",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":111,
    "MapParentID":105,
    "ParentID":75,
    "TagID":115,
    "TagName":"Special Offers",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":112,
    "MapParentID":104,
    "ParentID":71,
    "TagID":59,
    "TagName":"Downtown Disney",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":113,
    "MapParentID":104,
    "ParentID":71,
    "TagID":74,
    "TagName":"Merchandise",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":114,
    "MapParentID":103,
    "ParentID":63,
    "TagID":64,
    "TagName":"Attractions",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":115,
    "MapParentID":103,
    "ParentID":63,
    "TagID":65,
    "TagName":"Entertainment",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":116,
    "MapParentID":103,
    "ParentID":63,
    "TagID":66,
    "TagName":"Events and Tours",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":117,
    "MapParentID":103,
    "ParentID":63,
    "TagID":67,
    "TagName":"Parades",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":118,
    "MapParentID":103,
    "ParentID":63,
    "TagID":68,
    "TagName":"Fireworks",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":119,
    "MapParentID":103,
    "ParentID":63,
    "TagID":69,
    "TagName":"Rides",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":120,
    "MapParentID":103,
    "ParentID":63,
    "TagID":70,
    "TagName":"Character Experiences",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":121,
    "MapParentID":102,
    "ParentID":49,
    "TagID":90,
    "TagName":"Disneyland Park",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":122,
    "MapParentID":102,
    "ParentID":49,
    "TagID":91,
    "TagName":"Disney California Adventure Park",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":123,
    "MapParentID":102,
    "ParentID":49,
    "TagID":93,
    "TagName":"Disneyland Resort Hotels",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":124,
    "MapParentID":101,
    "ParentID":48,
    "TagID":34,
    "TagName":"Disabilities",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":125,
    "MapParentID":101,
    "ParentID":48,
    "TagID":35,
    "TagName":"Infants",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":126,
    "MapParentID":101,
    "ParentID":48,
    "TagID":36,
    "TagName":"Preschoolers",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":127,
    "MapParentID":101,
    "ParentID":48,
    "TagID":37,
    "TagName":"Kids",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":128,
    "MapParentID":101,
    "ParentID":48,
    "TagID":38,
    "TagName":"Tweens",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":129,
    "MapParentID":101,
    "ParentID":48,
    "TagID":40,
    "TagName":"Budgeting",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":130,
    "MapParentID":101,
    "ParentID":48,
    "TagID":41,
    "TagName":"Seasons",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":131,
    "MapParentID":101,
    "ParentID":48,
    "TagID":42,
    "TagName":"Weather",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":132,
    "MapParentID":101,
    "ParentID":48,
    "TagID":43,
    "TagName":"Large Parties",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":133,
    "MapParentID":101,
    "ParentID":48,
    "TagID":87,
    "TagName":"How To Get There",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":134,
    "MapParentID":101,
    "ParentID":48,
    "TagID":88,
    "TagName":"Multi-Day Visits",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":135,
    "MapParentID":100,
    "ParentID":47,
    "TagID":28,
    "TagName":"Parking",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":136,
    "MapParentID":100,
    "ParentID":47,
    "TagID":29,
    "TagName":"First Aid",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":137,
    "MapParentID":100,
    "ParentID":47,
    "TagID":30,
    "TagName":"Pets",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":138,
    "MapParentID":100,
    "ParentID":47,
    "TagID":31,
    "TagName":"Pin Trading",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":139,
    "MapParentID":99,
    "ParentID":24,
    "TagID":25,
    "TagName":"How To Be a Panelist",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":143,
    "MapParentID":9,
    "ParentID":8,
    "TagID":9,
    "TagName":"Table Service",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":144,
    "MapParentID":9,
    "ParentID":8,
    "TagID":10,
    "TagName":"Quick Service",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":145,
    "MapParentID":9,
    "ParentID":8,
    "TagID":13,
    "TagName":"Character Dining",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":146,
    "MapParentID":9,
    "ParentID":8,
    "TagID":57,
    "TagName":"Counter Service",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":147,
    "MapParentID":9,
    "ParentID":8,
    "TagID":58,
    "TagName":"Dining Plan",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":148,
    "MapParentID":9,
    "ParentID":8,
    "TagID":60,
    "TagName":"Hotels",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":149,
    "MapParentID":9,
    "ParentID":8,
    "TagID":61,
    "TagName":"Reservations",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":150,
    "MapParentID":9,
    "ParentID":8,
    "TagID":62,
    "TagName":"Signature Dining",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":151,
    "MapParentID":9,
    "ParentID":8,
    "TagID":94,
    "TagName":"Dining Events",
    "TopParentID":2,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":15,
    "MapParentID":8,
    "ParentID":8,
    "TagID":9,
    "TagName":"Table Service",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":15,
    "MapParentID":8,
    "ParentID":8,
    "TagID":9,
    "TagName":"Servicio de mesa",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":15,
    "MapParentID":8,
    "ParentID":8,
    "TagID":9,
    "TagName":"Service à table",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":15,
    "MapParentID":8,
    "ParentID":8,
    "TagID":9,
    "TagName":"Serviço de mesa",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":19,
    "MapParentID":8,
    "ParentID":8,
    "TagID":13,
    "TagName":"Character Dining",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":19,
    "MapParentID":8,
    "ParentID":8,
    "TagID":13,
    "TagName":"Comidas con los Personajes",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":19,
    "MapParentID":8,
    "ParentID":8,
    "TagID":13,
    "TagName":"Repas en compagnie de personnage",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":19,
    "MapParentID":8,
    "ParentID":8,
    "TagID":13,
    "TagName":"Refeição com personagens",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":40,
    "MapParentID":8,
    "ParentID":8,
    "TagID":57,
    "TagName":"Counter Service",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":40,
    "MapParentID":8,
    "ParentID":8,
    "TagID":57,
    "TagName":"Servicio de mostrador",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":40,
    "MapParentID":8,
    "ParentID":8,
    "TagID":57,
    "TagName":"Service au comptoir",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":40,
    "MapParentID":8,
    "ParentID":8,
    "TagID":57,
    "TagName":"Serviço de balcão",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":41,
    "MapParentID":8,
    "ParentID":8,
    "TagID":58,
    "TagName":"Dining Plan",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":41,
    "MapParentID":8,
    "ParentID":8,
    "TagID":58,
    "TagName":"Plan de comidas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":41,
    "MapParentID":8,
    "ParentID":8,
    "TagID":58,
    "TagName":"Formule de repas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":41,
    "MapParentID":8,
    "ParentID":8,
    "TagID":58,
    "TagName":"Plano de refeições",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":43,
    "MapParentID":8,
    "ParentID":8,
    "TagID":60,
    "TagName":"Hotels",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":43,
    "MapParentID":8,
    "ParentID":8,
    "TagID":60,
    "TagName":"Hoteles",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":43,
    "MapParentID":8,
    "ParentID":8,
    "TagID":60,
    "TagName":"Hôtels",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":43,
    "MapParentID":8,
    "ParentID":8,
    "TagID":60,
    "TagName":"Hotéis",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":44,
    "MapParentID":8,
    "ParentID":8,
    "TagID":61,
    "TagName":"Reservations",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":44,
    "MapParentID":8,
    "ParentID":8,
    "TagID":61,
    "TagName":"Reservaciones",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":44,
    "MapParentID":8,
    "ParentID":8,
    "TagID":61,
    "TagName":"Réservations",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
    "MapTagID":44,
    "MapParentID":8,
    "ParentID":8,
    "TagID":61,
    "TagName":"Reservas",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "pt"
  },
  {
    "MapTagID":45,
    "MapParentID":8,
    "ParentID":8,
    "TagID":62,
    "TagName":"Signature Dining",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "en"
  },
  {
    "MapTagID":45,
    "MapParentID":8,
    "ParentID":8,
    "TagID":62,
    "TagName":"Comidas de lujo",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "es"
  },
  {
    "MapTagID":45,
    "MapParentID":8,
    "ParentID":8,
    "TagID":62,
    "TagName":"Repas Signature",
    "TopParentID":1,
    "TagLevel":2,
    "Language": "fr"
  },
  {
  "MapTagID":45,
  "MapParentID":8,
  "ParentID":8,
  "TagID":62,
  "TagName":"Restaurante exclusivo",
  "TopParentID":1,
  "TagLevel":2,
  "Language": "pt"
  }
]
```
Don't be intimidated by the size of this array. Just use your knowledge of loops and how to access object properties using either dot syntax or bracket syntax.

<hr />

## Homework

This is tonight's official homework. Be sure to submit it to the homework repository. The exercise above is only an in-class exercise. Do not submit the exercise as homework, only submit this.

### Instructions

Create the following basic website layouts. See [this article for more information about each layout](https://designshack.net/articles/layouts/10-rock-solid-website-layout-examples/).

Using what you know about CSS grid systems, create the fllowing layouts in separate HTML pages using your grid styling method of choice: Traditional Float Based Grids or Flex box grids:

1. <img src="images/1.jpg" />
2. <img src="images/2.jpg" />
3. <img src="images/3.jpg" />
4. <img src="images/4.jpg" />
5. <img src="images/5.jpg" />
