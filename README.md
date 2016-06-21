EDD Software Licensing REST API
===============================

Provides a RESTful API, using the WordPress REST API for managing Easy Digital Downloads software licenses.

Note: All routes require authentication through WordPress. I recommend using [JWT](https://wordpress.org/plugins/jwt-authentication-for-wp-rest-api/), which is easy and is as secure as wp-login (IE fairly secure if using HTTPS and you are using fail2ban or something.)

<strong>Under development</strong> Might break shit.


## Routes
<em>This documentation is fairly aspirational at this point</em>

### `/licenses`

GET only

* `edd-sl-api/v1/licenses`
    * Get the titles of all products current user has an active license for.
* `edd-sl-api/v1/licenses?return=full`
    * Get full details about all licenses current user has an active license for.
    * Returns:
        * `title` - Download title
        * `download` - download id
        * `slug` - Download slug
        * `code` - License code
        * `activations` - Number of times license has been activates
        * `sites` - Urls of sites license is active on
        * `at_limit` - If license is at limit
        * `unlimited` - If license is unlimited
        * `limit` - License activation limit
        * `license` - License ID

### `license/<id>`
ID is ID of license code, not the license code.

* POST - Activate or deactivate a license
    * Required arguments
        * `download` - ID of download
        * `url` - URL of site license is being activated on
        * `action` - Either `activate` or `deactivate`
    * Returns:
            * ??
* GET - View license info for a specific license
    * Required arguments
        * `download` - ID of download
    * Returns:
        * ??

### `license/<id>/file`
ID is ID of license code, not the license code.

* GET get download file for license
        * Required arguments
            * `download` - ID of download
        * Returns:
            * ??



### Copyright/ License
Copyright 2016 Josh Pollock & CalderaWP LLC. Licensed under the terms of the GNU GPL v2 or later.

