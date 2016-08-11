#Purpose

This notification plugin for [check_mk](http://mathias-kettner.com/check_mk_introduction.html) uses [janimo's textsecure client](https://github.com/janimo/textsecure/) or my [TextSecure Gateway](https://github.com/morph027/textsecure-gateway) to send event notifications via TextSecure.

#Prerequisites

If you want to use this directly on your _check_mk_ host, you need to [setup](https://github.com/janimo/textsecure/wiki/Installation) and register a TextSecure account using the client written by janimo. When successful, you should have folders _.config_, _.storage_ and a binary named _textsecure_ and can send messages to a contact like ```./textsecure -to="+49XXX" -message="Test"```.

If you want to use the [TextSecure Gateway](https://github.com/morph027/textsecure-gateway), you just need _curl/wget_ (HTTP) or _ssh_ (SSH).

#Installation

##textsecure client

See above, only necessary when using the textsecure client directly on your _check_mk_ host. Each _check_mk_ site should have ```~/local/bin``` in it's _PATH_ variable. Just put the _.config_ + _.storage_ folders and the _textsecure_ binary into it. In [OMD](http://omdistro.org/) this is ```/omd/sites/$SITE_NAME/local/bin```

##textsecure notification plugin

Get the _textsecure_ binary you want to use from this repo, place it into ```$CHECK_MK_SITE_PATH/local/share/check_mk/notifications/``` and make sure it's executable.

#Usage

Before you can use the plugin, you need to set a **_Pager address_** for the user in WATO. Also you need to add the plugin as notification rule. To do so, just navigate to the **_Notifications_** item in the **_WATO Configuration_** menu panel and add a new rule selecting one of the **_TextSecure (using janimos library)/using SSH Gateway/using HTTP Gateway_**.
