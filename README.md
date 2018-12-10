# BaniDB API
Active work ongoing under dev branch


# Users

* [Sundar Gutka - STTM Web](https://www.sikhitothemax.org/sundar-gutka)

# Migration Guide for v1 to v2

## Change in API endpoint

Instead of hitting `http://api.banidb.com/`, you should now hit `http://api.banidb.com/v2/`.

## ℹ️ Response

There are several changes in the response structure of v2 API.

### `pageinfo` ➡️ `resultsInfo`

```diff
- "pageinfo": {
-   "totalresults": 4,
-   "resultsperpage": 20,
-   "pageresults": 4
- },
+ "resultsInfo": {
+   "totalResults": 26,
+   "pageResults": 20,
+   "pages": {
+     "page": 1,
+     "resultsPerPage": 20,
+     "totalPages": 2,
+     "nextPage": "http://api.banidb.com/v2/search/asd?page=2"
+   }
+ },
```

### `shabads` ➡️ `verses`

```diff
- "shabads": [
-   {
-     "shabad": {}
-   }
-  ]
+ "verses": [
+  {}
+ ]
```

### `shabads[i].shabad` ➡️ `verses[i]`

```diff
-  "shabad": {
-      "id": "58445",
-      "gurbani": {
-        "gurmukhi": "ausu swcy dIbwn mih plw n pkrY koie ]201]",
-        "unicode": "ਉਸੁ ਸਾਚੇ ਦੀਬਾਨ ਮਹਿ ਪਲਾ ਨ ਪਕਰੈ ਕੋਇ ॥੨੦੧॥"
-      },
-      "larivaar": {
-        "gurmukhi": "aususwcydIbwnmihplwnpkrYkoie]201]",
-        "unicode": "ਉਸੁਸਾਚੇਦੀਬਾਨਮਹਿਪਲਾਨਪਕਰੈਕੋਇ॥੨੦੧॥"
-      },
-      "translation": {
-        "english": {
-          "ssk": "In the True Court of the Lord, no one will seize you. ||201||"
-        },
-        "punjabi": {
-          "bms": {
-            "gurmukhi": "aus s`cI kcihrI ivc koeI rok-tok nhIN krdw [201[",
-            "unicode": "ਉਸ ਸੱਚੀ ਕਚਹਿਰੀ ਵਿਚ ਕੋਈ ਰੋਕ-ਟੋਕ ਨਹੀਂ ਕਰਦਾ ।੨੦੧।"
-          }
-        },
-        "spanish": "en la Corte Verdadera del Señor nadie te va a tocar. (201)"
-      },
-      "transliteration": "aus saache dheebaan meh palaa na pakarai koi ||201||",
-      "shabadid": "5169",
-      "pageno": "1375",
-      "lineno": "7",
-      "updated": "2018-05-13 22:17:02",
-      "firstletters": {
-        "ascii": ",097,115,100,109,112,110,112,107,",
-        "english": "asdmpnpk"
-      },
-      "bisram": {
-        "sttm": "20",
-        "igurbani1": null,
-        "igurbani2": null
-      },
-      "writer": {
-        "id": "12",
-        "gurmukhi": "Bgq kbIr jI",
-        "unicode": null,
-        "english": "Bhagat Kabeer Ji"
-      },
-      "source": {
-        "id": "G",
-        "gurmukhi": "sRI gurU gRMQ swihb jI",
-        "unicode": "ਸ੍ਰੀ ਗੁਰੂ ਗ੍ਰੰਥ ਸਾਹਿਬ ਜੀ",
-        "english": "Sri Guru Granth Sahib Ji",
-        "pageno": "1375"
-      },
-      "raag": {
-        "id": "40",
-        "gurmukhi": "slok Bgq kbIr jIau ky",
-        "unicode": "ਸਲੋਕ ਭਗਤ ਕਬੀਰ ਜੀਉ ਕੇ",
-        "english": "Salok Kabeer Jee",
-        "startang": null,
-        "endang": null,
-        "raagwithpage": "Salok Kabeer Jee (1364-1377)"
-      }
-    }
-  }
+ {
+    "verseId": 638,
+    "verse": {
+      "gurmukhi": "aUqm sy dir aUqm khIAih nIc krm bih roie ]1] rhwau ]",
+      "unicode": "ਊਤਮ ਸੇ ਦਰਿ ਊਤਮ ਕਹੀਅਹਿ ਨੀਚ ਕਰਮ ਬਹਿ ਰੋਇ ॥੧॥ ਰਹਾਉ ॥"
+    },
+    "larivaar": {
+      "gurmukhi": "aUqmsydiraUqmkhIAihnIckrmbihroie]1]rhwau]",
+      "unicode": "ਊਤਮਸੇਦਰਿਊਤਮਕਹੀਅਹਿਨੀਚਕਰਮਬਹਿਰੋਇ॥੧॥ਰਹਾਉ॥"
+    },
+    "translation": {
+      "english": {
+        "ssk": "They alone are good, who are judged good at the Lord's Door. Those with bad karma can only sit and weep. ||1||Pause||"
+      },
+      "punjabi": {
+        "bms": {
+          "gurmukhi": "auhI mnu`K (Asl ivc) cMgy hn, jo pRBU dI hzUrI ivc cMgy AwKy jWdy hn, mMd-krmI bMdy bYTy Jurdy hI hn [1[rhwau[",
+          "unicode": "ਉਹੀ ਮਨੁੱਖ (ਅਸਲ ਵਿਚ) ਚੰਗੇ ਹਨ, ਜੋ ਪ੍ਰਭੂ ਦੀ ਹਜ਼ੂਰੀ ਵਿਚ ਚੰਗੇ ਆਖੇ ਜਾਂਦੇ ਹਨ, ਮੰਦ-ਕਰਮੀ ਬੰਦੇ ਬੈਠੇ ਝੁਰਦੇ ਹੀ ਹਨ ।੧।ਰਹਾਉ।"
+        }
+      },
+      "spanish": "Buenos son aquéllos que tienen el buen estilo en la Corte de Señor. Los malvados de corazón sólo sufren y perecen.  (1-Pausa)"
+    },
+    "transliteration": {
+      "english": "uootam se dhar uootam kahe'eeh neech karam beh roi ||1|| rahaau ||"
+    },
+    "shabadId": 57,
+    "pageNo": 15,
+    "lineNo": 11,
+    "updated": "2018-05-13 22:17:02",
+    "firstLetters": {
+      "ascii": ",097,115,100,097,107,110,107,098,114,117,",
+      "english": "usduknkbrr"
+    },
+    "bisram": {
+      "sttm": "8,25",
+      "igurbani1": null,
+      "igurbani2": null
+    },
+    "writer": {
+      "writerId": 1,
+      "gurmukhi": "mÚ 1",
+      "unicode": null,
+      "english": "Guru Nanak Dev Ji"
+    },
+    "source": {
+      "sourceId": "G",
+      "gurmukhi": "sRI gurU gRMQ swihb jI",
+      "unicode": "ਸ੍ਰੀ ਗੁਰੂ ਗ੍ਰੰਥ ਸਾਹਿਬ ਜੀ",
+      "english": "Sri Guru Granth Sahib Ji",
+      "pageNo": 15
+    },
+    "raag": {
+      "raagId": 5,
+      "gurmukhi": "isrI rwgu",
+      "unicode": "ਸਿਰੀ ਰਾਗੁ",
+      "english": "Siree Raag",
+      "startAng": 14,
+      "endAng": 588,
+      "raagWithPage": "Siree Raag (14-93)"
+    }
+  }
```

## ℹ️ Hukamnama API

We now support listing of Hukamnamas by dates.

* `/hukamnamas/:year?/:month?/:day?`. Provide any of the fields (from left-right) and get list of hukamnamas for that year/month/day.

## ℹ️ Random API

You can now provide the SourceID while fetching a random shabad.

*  `/random/:SourceID?`

## 🆕 Banis API

These are the compiled banis (Sundar Gutka).

* `/banis` to fetch all banies under Sundar Gutka
* `/banis/:BaniID` to fetch a particular bani.

## 🆕 Rehats API

* `/rehats` to get all rehats
* `/rehats/:RehatID` to get list of chapters under a rehat.
* `/rehats/:RehatID/chapters/:ChapterID?` to get the chapter details
* `/rehats/search/:string` to search rehat.
