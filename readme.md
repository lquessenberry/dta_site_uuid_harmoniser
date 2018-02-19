# Digital Transformation Agency Site UUID Harmoniser

## What is this?

Upon installation, this module will:

1. Check whether the site is hosted on the DTA's cloud.gov.au infrastructure. It does this by checking for the presence of the `$_ENV['VCAP_SERVICES']` array.
2. If it finds the environment, it will then check for the correct user-provided service running on cloud.gov.au. If found, the module sets the site UUID to match the one found in the service.
3. If it does not find the environment, or the correct service, the module will set the site UUID to a generated one using Drupal's UUID generation service.
