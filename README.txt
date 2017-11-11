Flysystem Dropbox
=================

For setup instructions see the Flysystem README.txt.
Useful links:

Dropbox will turn off v1 of their API soon. It’s time to update your PHP application
https://murze.be/2017/04/dropbox-will-turn-off-v1-of-their-api-soon-its-time-to-update-your-php-application/

Connect your app to Dropbox:
https://auth0.com/docs/connections/social/dropbox


## CONFIGURATION ##

Configuration steps:
1. Go to the Dropbox developer portal and create an app
2. Generate an OAuth2 token
3. Add something like the following to settings.php

$schemes = [
  'dropboxexample' => [
    'driver' => 'dropbox',
    'config' => [
      'token' => 'a-long-token-string',
      'client_id' => 'You Client Id Name',

      // Optional.
      'prefix' => 'a/sub/directory',
      'public' => TRUE, // Serve files directly via Dropbox.
    ],
  ],
];

$settings['flysystem'] = $schemes;
