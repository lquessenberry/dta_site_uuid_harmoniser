# Digital Transformation Agency Site UUID Harmoniser

## What is this?

Upon installation, this module will:

1. Check whether the site is hosted on the DTA's cloud.gov.au infrastructure. It does this by checking for the presence of the `$_ENV['VCAP_SERVICES']` array.
2. If it finds the environment, it will then check for the correct user-provided service running on cloud.gov.au. If found, the module sets the site UUID to match the one found in the service.
3. If it does not find the environment, or the correct service, the module will set the site UUID to a generated one using Drupal's UUID generation service.

By harmonising the UUIDs across sites, it becomes possible to import configuration without using a database dump or Drush to reset the UUID. This is useful in a continuous delivery/continuous integration scenario.

## Advisory

This module is really only useful on installed sites where it is impossible to log in using SSH and run Drush commands. It relies on having the correct environment and the correct service running.
