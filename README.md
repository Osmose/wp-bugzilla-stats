# Wordpress Bugzilla Stats

**In Development, Use at your own Risk**

Provides two functions for retrieving statistics about a Bugzilla user. This can be used to add Bugzilla statistics to a Wordpress user profile page.

The following statistics are available:

* Bugs Created

## Installation

1. Copy the `bugzilla_stats` directory to your `wp-content/plugins` directory.
2. Activate the plugin via the Wordpress admin interface.
3. Navigate to the `Settings->Bugzilla Stats` page in the Wordpress admin interface and enter the URL for a Bugzilla install and delay time for caching retrieved data.

## Usage

The `get_bugzilla_stats_for_user` function takes an email address its argument and returns an array containing the following data:

* `$result['updated_at']`: Timestamp when the statistics were last updated.
* `$result['bug_count']`: Total amount of bugs the user has created.

If an invalid email address is given, the function returns `false`.

The `update_bugzilla_stats_for_user` function returns the same value, but will update the database cache regardless of how much time has passed since the last update.
