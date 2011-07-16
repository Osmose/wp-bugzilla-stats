# Wordpress Bugzilla Stats

Provides functions for retrieving statistics about a Bugzilla user. This can be used to add Bugzilla statistics to a Wordpress user profile page.

## Installation

1. Copy the `bugzilla_stats` directory to your `wp-content/plugins` directory.
2. Activate the plugin via the Wordpress admin interface.
3. Navigate to the __Settings->Bugzilla Stats__ page in the Wordpress admin interface and enter the URL for a Bugzilla install and delay time for caching retrieved data.

## Usage

```
// You can also use get_userdata, get_currentuserinfo, or other equivalent functions
$user = get_user_by_email('user@example.com');

// Will pull from user metadata cache if possible
$stats = get_bugzilla_stats_for_user($user);

// You can also skip the cache and get stats for *any* Bugzilla user
$stats = get_buzilla_stats_for_email('user@example.com')
```

Results of the above code:

* `$stats['updated_at']`: Timestamp when the statistics were last updated.
* `$stats['bug_count']`: Total amount of bugs the user has created.
* `$stats['recent_bug_count']`: Amount of bugs created in the last month.

### Error Handling

Both functions will throw exceptions on errors:

* __BugzillaConnectionException__: An error has occurred while connection to Bugzilla.
* __BugzillaUserNotFoundException__: Thrown when a user cannot be found in Bugzilla.

## License

```
***** BEGIN LICENSE BLOCK *****
Version: MPL 1.1/GPL 2.0/LGPL 2.1

The contents of this file are subject to the Mozilla Public License Version
1.1 (the "License"); you may not use this file except in compliance with
the License. You may obtain a copy of the License at
http://www.mozilla.org/MPL/

Software distributed under the License is distributed on an "AS IS" basis,
WITHOUT WARRANTY OF ANY KIND, either express or implied. See the License
for the specific language governing rights and limitations under the
License.

The Original Code is Bugzilla User Statistics Wordpress plugin.

The Initial Developer of the Original Code is
Mozilla Corporation.
Portions created by the Initial Developer are Copyright (C) 2011
the Initial Developer. All Rights Reserved.

Contributor(s):
  Michael Kelly <mkelly@mozilla.com>

Alternatively, the contents of this file may be used under the terms of
either the GNU General Public License Version 2 or later (the "GPL"), or
the GNU Lesser General Public License Version 2.1 or later (the "LGPL"),
in which case the provisions of the GPL or the LGPL are applicable instead
of those above. If you wish to allow use of your version of this file only
under the terms of either the GPL or the LGPL, and not to allow others to
use your version of this file under the terms of the MPL, indicate your
decision by deleting the provisions above and replace them with the notice
and other provisions required by the GPL or the LGPL. If you do not delete
the provisions above, a recipient may use your version of this file under
the terms of any one of the MPL, the GPL or the LGPL.

***** END LICENSE BLOCK *****
```
