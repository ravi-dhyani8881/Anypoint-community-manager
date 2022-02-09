---
title:  "Exclude Post from Search Index"
search: false
tags: [Mermaid]
comments: true
mermaid: true
categories: 
  - Jekyll
last_modified_at: 2018-02-19T08:06:00-05:00
---



# Example RAML 1.0 API documentation version 1
http://example.com/{version}

### Welcome
Welcome to the Example Documentation. The Example API allows you
to do stuff. See also [example.com](https://www.example.com).

```javascript
var raml2html = require('raml2html');

// Using the default templates:
// source can either be a filename, file contents (string) or parsed RAML object
raml2html.parse(source, onSuccess, onError);

// Using your own templates:
// - config should be an object with at least an `template` property
// - config can also include `helpers` and `partials`
// - the config object will be accessible from your handlebars templates
raml2html.parseWithConfig(source, config, onSuccess, onError);
```
<div class="mermaid">
%% Code for flowchart below
graph TB
    sq[Square shape] --> ci((Circle shape))

    subgraph A subgraph2
        od>Odd shape]-- Two line<br>edge comment --> ro
        di{Diamond with <br/> line break} -.-> ro(Rounded<br>square<br>shape)
        di==>ro2(Rounded square shape)
    end

    %% Notice that no text in shape are added here instead that is appended further down
    e --> od3>Really long text with linebreak<br>in an Odd shape]

    %% Comments after double percent signs
    e((Inner / circle<br>and some odd <br>special characters)) --> f(,.?!+-*ز)

    cyr[Cyrillic]-->cyr2((Circle shape Начало));

     classDef green fill:#9f6,stroke:#333,stroke-width:2px;
     classDef orange fill:#f96,stroke:#333,stroke-width:4px;
     class sq,e green
     class di orange
</div>

### Chapter two
More content here. Including **bold** text!

Small table:

| A | B | C |
|---|---|---|
| 1 | 2 | 3 |

Done

---

## ACCOUNT
This is the top level description for /account.
* One
* Two
* Three

### /account

* **post**: Creates a new account. Some **bold** text here. More text. Need to fill the line, so make it longer still. Hooray!
Line two

Paragraph two

<iframe src="https://drive.google.com/file/d/1sAljROKTAd_sf1S-xKnMVGB_TnHZ6Ocu/preview" width="640" height="480" allow="autoplay"></iframe>


### /account/find

* **get**: find an account

### /account/{id}

* **get**: 
* **put**: Update the account
* **delete**: Delete the account

### /account/login

* **post**: Login with email and password

### /account/forgot

* **post**: Sends an email to the user with a link to set a new password

### /account/session

* **get**: Gets the sessions
* **delete**: Deletes the session, logging out the user

### /account/admin

* **post**: Creates a new administrator account.

### /account/user

* **post**: Test for multiple inheritence.

## ACCOUNTS

### /accounts

* **post**: Creates multiple accounts.

## Forecasts
The very top resource - displays OK

### /forecasts/{geoposition}
Overview endpoint to assemble and access forecast data in various timely resolutions - THIS IS NOT DISPLAYED ANYWHERE WITH RAML2HTML :/

* **get**: Provides an overview of the available data - display OK

### /forecasts/test
No methods here, but it does have a description

## /conversations
This is the top level description for /conversations.

### /conversations

* **get** *(secured)*: Get a list of conversation for the current user
* **post** *(secured)*: Create a new conversions. The currently logged in user doesn't need to be supplied in the members list, it's implied.

### /conversations/{convId}

* **get**: Get a single conversation including its messages
* **put**: Update a conversation (change members)

### /conversations/{convId}/messages

* **get**: Get the messages for the conversation
* **post**: Add a new message to a conversation

### /conversations/{convId}/messages/{messageId}

* **put**: Update the message
* **delete**: Delete the message

## /users

### /users

* **get**: Get a list of all users
* **post**: Creates a new user

### /users/{userId}

* **get**: Get the details of a user including a list of groups he belongs to
* **put**: Update a user
* **delete**: Deletes a user

### /users/name_{userName}_{account}

* **get**: Get all the users with a specific name

## /groups

### /groups

* **get**: Get a list of all the groups
* **post**: Create a new group

### /groups/{groupId}

* **get**: Get the details of a group, including the member list
* **put**: Update the group, **optionally** supplying the new list of members (overwrites current list)
* **delete**: Removes the group

### /groups/{groupId}/users

* **post**: Adds a user to a group

### /groups/{groupId}/users/{userId}

* **delete**: Removes a user from a group

{% if page.comments %} 

<div id="disqus_thread"></div>
<script>
    /**
    *  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
    *  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables    */
    /*
    var disqus_config = function () {
    this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
    this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
    };
    */
    (function() { // DON'T EDIT BELOW THIS LINE
    var d = document, s = d.createElement('script');
    s.src = 'https://ravi-dhyani-github-io-anypoint-community-manager.disqus.com/embed.js';
    s.setAttribute('data-timestamp', +new Date());
    (d.head || d.body).appendChild(s);
    })();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
{% endif %}