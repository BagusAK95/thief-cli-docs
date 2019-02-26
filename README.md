Thief CLI - Documentation of Yaml Configuration
=========

# Configs
<!-- configs -->
* [`target`](#target)
* [`stealingMode`](#stealingmode-optional-default-thispage)
* [`interval`](#interval-optional-default-0)
* [`parent`](#parent)
* [`childs`](#childs)
* [`nextPage`](#nextPage)
* [`saveAs`](#saveas-optional-default-json)

## target

#### uri [Required]
The url that you want to steal the content

```
target:
    uri: https://demo.website.com
```

#### timeout [Optional] (Default: 60000)
Time to wait for a server to send response before aborting the request.

```
target:
    timeout: 300000 #5 minute
```

#### qs [Optional]
Object containing querystring values to be appended to the `uri`

```
target:
    qs:
        page: 1
        access_token: <Your Access token>
```

The url will be `https://demo.website.com?page=1&access_token=<Your Access token>`

#### headers [Optional]
HTTP Headers

```
target:
    headers:
        User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/72.0.3626.109 Safari/537.36
```

## stealingMode [Optional] (Default: thisPage)
There are 2 options for scraping mode namely `thisPage` and` toDetail`.

* `thisPage` is a scraping mode that get content from one page
* `toDetail` is a scraping mode that get content from page details

```
stealingMode: toDetail
```

## interval [Optional] (Default: 0)
The time needed to get content from the first page and the next page

```
interval: 5000 #5 seconds
```

## parent

#### selector [Required]
This selector method is the starting point for traversing and manipulating the document. Like jQuery, it's the primary method for selecting elements in the document, but unlike jQuery it's built on top of the CSSSelect library, which implements most of the Sizzle selectors.

```
parent:
    selector: a.article__link
```

#### attribute [Optional]
Method for getting and setting attributes. Gets the attribute value for only the first element in the matched set.

```
parent:
    selector: a.article__link
    attribute: href
```

## childs

#### content [Required]
Name of content.

```
childs:
    -
        content: title
        selector: h1.read__title
```

#### selector [Required]
This selector method is the starting point for traversing and manipulating the document. Like jQuery, it's the primary method for selecting elements in the document, but unlike jQuery it's built on top of the CSSSelect library, which implements most of the Sizzle selectors.

```
childs:
    -
        content: author
        selector: div#penulis > a
```

#### attribute [Optional]
Method for getting and setting attributes. Gets the attribute value for only the first element in the matched set.

```
childs:
    -
        content: image
        selector: div.photo > img
        attribute: src
```

#### regex [Optional]
A regular expression is an object that describes a pattern of characters.

```
childs:
    -
        content: date
        selector: div.read__time
        regex: (\d{1,4}\/\d{1,4}\/\d{1,4}, \d{1,4}\:\d{1,4})
```

#### group [Optional]
Get regex result by group.

```
childs:
    -
        content: date
        selector: div.read__time
        regex: (\d{1,4}\/\d{1,4}\/\d{1,4}, \d{1,4}\:\d{1,4})
        group: 1
```

#### format [Optional] {Default: String}
Format content to be `string`, `number`, `date`

```
childs:
    -
        content: date
        selector: div.read__time
        format:
            type: date #string, number, date
            dateFormat: DD/MM/YYYY, HH:mm #Format date from the content result (Just for Date)
            dateLocale: id #Code locale from the content result (Just for Date)
```

## nextPage

#### selector [Required]
This selector method is the starting point for traversing and manipulating the document. Like jQuery, it's the primary method for selecting elements in the document, but unlike jQuery it's built on top of the CSSSelect library, which implements most of the Sizzle selectors.

```
nextPage:
    selector: a.paging__link.paging__link--next[rel=next]
```

#### attribute [Optional]
Method for getting and setting attributes. Gets the attribute value for only the first element in the matched set.

```
nextPage:
    selector: a.paging__link.paging__link--next[rel=next]
    attribute: href
```

## saveAs [Optional] (Default: Json)
Save result to be `json` or `csv`

```
saveAs: csv
```

<!-- configsstop -->