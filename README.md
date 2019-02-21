Thief CLI - Documentation of Yaml Configuration
=========

<!-- configs -->
* [`target`](#target)
* [`scrapingMode`](#scrapingMode)
* [`interval`](#interval)
* [`parent`](#parent)
* [`childs`](#childs)
* [`nextPage`](#nextPage)
* [`saveAs`](#saveAs)

## target

#### uri [Required]
The url that you want to steal the content

```
- uri: https://demo.website.com
```

#### timeout [Optional] (Default: 60000)
Time to wait for a server to send response before aborting the request.

```
- timeout: 300000 #5 minute
```

#### qs [Optional]
Object containing querystring values to be appended to the `uri`

```
- qs:
  - page: 1
  - access_token: xxxxx
```

The url will be `https://demo.website.com?page=1&access_token=xxxxx`

#### headers [Optional]
HTTP Headers

```
- headers:
  - User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/72.0.3626.109 Safari/537.36
  - content-type: application/json
```

## scrapingMode [Optional] (Default: thisPage)
There are 2 options for scraping mode namely `thisPage` and` toDetail`.

* `thisPage` is a scraping mode that get content from one page
* `toDetail` is a scraping mode that get content from page details

```
- scrapingMode: toDetail
```

## interval
The time needed to get content from the first page and the next page

```
- interval: 10000 #10 seconds
```

## parent

#### selector

#### attribute

## childs

#### content

#### selector

#### attribute

#### regex

#### group

#### format

## nextPage

#### selector

#### attribute

## saveAs
<!-- configsstop -->