#Purpose

This notification plugin for [check_mk](http://mathias-kettner.com/check_mk_introduction.html) uses [janimo's textsecure client](https://github.com/janimo/textsecure/) to send event notifications via TextSecure.

#Prerequisites

You need to [setup](https://github.com/janimo/textsecure/wiki/Installation) and register a TextSecure account using the client written by janimo. When successful, you should have folders _.config_, _.storage_ and a binary named _textsecure_ and can send messages to a contact like ```./textsecure -to="+49XXX" -message="Test"```.

#Installation

##textsecure client

Each _check_mk_ site should have ```~/local/bin``` in it's _PATH_ variable. Just put the _.config_ + _.storage_ folders and the _textsecure_ binary into it. In [OMD](http://omdistro.org/) this is ```/omd/sites/$SITE_NAME/local/bin```

##textsecure notification plugin

Get the _textsecure_ binary from this repo, place it into ```$CHECK_MK_PATH/share/check_mk/notifications/``` and make sure it's executable. In [OMD](http://omdistro.org/), this is something like ```/opt/omd/versions/$OMD_VERSION/share/check_mk/notifications/```.

#Usage

Before you can use the plugin, you need to set a **_Pager address_** for the user in WATO. Also you user must use **_Flexible Custom Notifications_**. In it's section, just select **_TextSecure (using janimos library)_** as **_Notification Plugin_**.
