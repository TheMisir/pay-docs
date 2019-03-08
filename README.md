---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell: curl
  - php
  - javascript: Node.js

toc_footers:
  - <a target='_blank'  href='http://pay.uviba.com'>Sign Up To get API Keys</a>
  - <a target='_blank'  href='https://github.com/uviba/'>Our Libraries</a>


search: true
---

# Introduction
<style>
a {
    color: #0099e5;
    text-decoration: none;
}
.content blockquote>p {
    color: #dde4e8;
}
.shell .gp{
    user-select: none;
}
</style>
<style type="text/css">
	/* Checkbox body */

.cool_checkbox_label {
  display: block;
  width: 54px;
  height: 32px;
  margin: 0px auto;
  border-radius: 100px;
  transition: all 0.2s ease-in-out;
  -webkit-transition: all 0.2s ease-in-out;
  /*background-color: #E6E9EC;*/
  background: #dcdcdc;
}

.cool_checkbox {
  display: none;
}


/* The toggle */

.cool_checkbox_label>i {
  height: 28px;
  width: 28px;
  background: #ffffff;
  display: inline-block;
  border-radius: 100px;
  margin-top: 2px;
  margin-left: 2px;
  transition: all 0.2s ease-in-out;
  -webkit-transition: all 0.2s ease-in-out;
  pointer-events: none;
  box-shadow: 0px 0px 0px 0px rgba(0, 0, 0, 0);
}

.cool_checkbox_label:hover>i {
  box-shadow: 0px 1px 2px 0px rgba(0, 0, 0, 0.20);
  transform: scale(1.01);
}

.cool_checkbox:checked+.cool_checkbox_label>i {
  margin-left: 24px;
}

.cool_checkbox_label:active {
  background-color: #A6B9CB;
}

.cool_checkbox_label:active>i {
  width: 34px;
  box-shadow: 0px 2px 4px 0px rgba(0, 0, 0, 0.20);
}

.cool_checkbox:checked+.cool_checkbox_label:active>i {
  margin-left: 18px;
}

.cool_checkbox:checked+.cool_checkbox_label {
  background-color: #008FFF;
}

 
.with-hint{
	position: relative;
}

.with-hint:hover:after,.with-hint:focus:after{
     content: attr(data-hint);
    display: block;
    width: 100%;
    min-width: 218px;
    max-width: 300px;
    height: auto;
    background-color: #3692ff;
    color: #fff !important;
    position: absolute;
    top: -14px;
    left: 100%;
    margin-left: 7px;
    white-space: normal;
    font-size: 13px;
    color: #323438;
    padding: 10px;
    line-height: 1.6;
    border-radius: 6px;
    box-shadow: 1px 1px 4px 0 rgba(6, 6, 6, 0.27);
    word-wrap: break-word;
    word-spacing: inherit;
    word-break: break-word;z-index: 999999999;
}
.with-hint:hover:before,.with-hint:focus:before{
    content: '';
    display: block;
    position: absolute;
    top: 8px;
    left: 100%;
    margin-left: 1px;
    border: solid;
    border-color: #3692ff transparent;
    border-width: 0px 5px 5px;
    -webkit-transform: rotate(-90deg);
    -ms-transform: rotate(-90deg);
    transform: rotate(-90deg);    z-index: 999999999;
}
.content blockquote {
    background-color: #191D1F;
    padding: 13px 2em;
    color: #eee;
}
</style>
The Uviba API is organized around <a href="https://en.wikipedia.org/wiki/Representational_state_transfer" target="_blank">REST</a>. Our API has predictable resource-oriented URLs, accepts <a href="https://en.wikipedia.org/wiki/POST_(HTTP)#Use_for_submitting_web_forms" target="_blank">form-encoded</a> request bodies, returns <a href="http://www.json.org/" target="_blank">JSON-encoded</a> responses, and uses standard HTTP response codes, authentication, and verbs.

You can use the Uviba API in test mode, which does not affect your live data. The API key you use to authenticate the request determines whether the request is the live mode or test mode.

> <div style="margin:0px;font-size: 15px;font-weight: 500;">API libraries</div> <br/> Official libraries for the Uviba  API are available in <a target="_blank" href="https://github.com/uviba/" style="color: #0099e5;text-decoration: none;border: none;">several languages</a>. 

# Authentication
> To authorize, use this code:

```shell
$ curl https://api.stripe.com/v1/charges \
  -u your_private_key:
	# The colon prevents curl from asking for a password.

```

```php
require 'kittn.php';
echo'asdasd';
```


```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```



> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```php
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```javascript
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use blocks to denote code.</aside>
<!--<code><code></code> -->


### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete




<script type="text/javascript">

function isset(variablex){
  //it will duplicate in index.php
  //ISLEMIR
  if(typeof variablex != "undefined" && variablex !== null){
    return true;
  }else{
    return false;
  }
}

var private_test_key="sk_test_4DXgAakAurAQo7dc";
var private_live_key="sk_live_examplesAsdhQYeAJ";
var public_test_key="pk_test_AsuQyNoJOurAQo7dc";
var public_live_key="pk_live_exampleKhdaQyAnAoY";
function rep_tokens(word, element,rep_word1,rep_word2) {
		if(!isset(rep_word1)){
		   rep_word1=word;
		}
    var rgxp = new RegExp(word, 'g');
    var repl = '<span style="\
    color: #c1ef65;\
" class="token test_mode">' + rep_word1 + '</span>';
if(isset(rep_word2)){
repl += '<span style="\
    color: #c1ef65;display:none;\
" class="token live_mode">' + rep_word2 + '</span>';
}
    element.innerHTML = element.innerHTML.replace(rgxp, repl);
}

$('.highlight').each(function(){

rep_tokens('your_private_key',$(this).get(0),private_test_key,private_live_key);
rep_tokens('your_public_key',$(this).get(0),public_test_key,public_live_key);

});

$('.toc-footer').after('<ul class="toc-footer" style="\
    /* text-align: center; */\
">\
            <li><span>API Key Mode<span></span></span></li><li><span style="\
    font-size: 15px;user-select:none;\
">\
\
<span style="color: white; font-weight: 600;user-select:none; display: none;" class="live_mode">live</span>\
<span style="color: white; font-weight: 600;user-select:none;" class="test_mode">test</span>\
   <input class="cool_checkbox" type="checkbox" id="toggly">\
  <label style="-webkit-transform: scale(0.7);-moz-transform: scale(0.7);-ms-transform: scale(0.7);-o-transform: scale(0.7);transform: scale(0.6);cursor:pointer;left: 0;display: inline-block;position: relative;top: 8px;" class="cool_checkbox_label" onclick="var checkbox_elem = $(this).prev();\
\
 $(\'.live_mode\').toggle();\
 $(\'.test_mode\').toggle();\
 //live_balance_css means disappread only in toggle\
 if(isLiveMode==1){\
  isLiveMode=0;\
 }else if(isLiveMode==0){\
  isLiveMode=1;\
 }\
  " for="toggly"><i></i></label> </span></li>\
        </ul>');
</script>
