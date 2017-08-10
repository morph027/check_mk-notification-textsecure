# Purpose

This notification plugin for [check_mk](http://mathias-kettner.com/check_mk_introduction.html) uses [janimo's textsecure client](https://github.com/janimo/textsecure/) or my [Signal Web Gateway](http://gitlab.com/morph027/signal-web-gateway/) to send event notifications via TextSecure.

# Prerequisites

If you want to use this directly on your *check_mk* host, you need to [setup](https://github.com/janimo/textsecure/wiki/Installation) and register a TextSecure account using the client written by janimo. When successful, you should have folders `.config`, `.storage` and a binary named `textsecure` and can send messages to a contact like `./textsecure -to="+49XXX" -message="Test"`.

Recommended: If you want to use the [Signal Web Gateway](http://gitlab.com/morph027/signal-web-gateway/), you just to install `python-requests`.

# Installation

## textsecure client

See above, only necessary when using the textsecure client directly on your *check_mk* host. Each *check_mk* site should have `~/local/bin` in it's `PATH` variable. Just put the `.config` + `.storage` folders and the `textsecure` binary into it. In [OMD](http://omdistro.org/) this is `/omd/sites/$SITE_NAME/local/bin`.

## textsecure notification plugin

Download the script you want to use as notification plugin from this repo into `$CHECK_MK_SITE_PATH/local/share/check_mk/notifications/` and make sure it's executable.

### `textsecure-via-http`

Just make sure you do have the Python requests module. If not, just issue `apt-get -y install python-requests` or `yum -y install python-requests`.

# Usage

* before you can use the plugin, you need to set a **_Pager address_** for the user in WATO
* now you can setup a flexible notification rule for the user and selet one of the **_TextSecure (using janimos library)/using HTTP Gateway_**
* in case of **_TextSecure using HTTP Gateway_**, you also need to specifiy the URL of the signal gateway as first parameter in WATO (e.g. `http://mail2signal.example.com`)
