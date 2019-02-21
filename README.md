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
* [`uri`](#uri)
* [`method`](#method)
* [`timeout`](#timeout)
* [`qs`](#qs)
* [`headers`](#headers)
* [`body`](#body)
* [`formData`](#formData)

#### uri [Required]
Full url

```
- uri: https://demo.website.com
```

#### method [Optional] (Default: GET)
HTTP Method (GET, POST, PUT, DELETE)

```
- method: GET
```

#### timeout

#### qs

#### headers

#### body

#### formData

## scrapingMode

## interval

## parent
* [`selector`](#selector)
* [`attribute`](#attribute)

#### selector

#### attribute

## childs
* [`content`](#content)
* [`selector`](#selector)
* [`attribute`](#attribute)
* [`regex`](#regex)
* [`group`](#group)
* [`format`](#format)

#### content

#### selector

#### attribute

#### regex

#### group

#### format

## nextPage
* [`selector`](#selector)
* [`attribute`](#attribute)

#### selector

#### attribute

## saveAs
<!-- configsstop -->