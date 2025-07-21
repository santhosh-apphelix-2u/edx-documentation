#######################
Proctortrack Setup
#######################

This document contains specific configuration details and setup instructions for Proctortrack that may be needed for historical reference. This information is valuable for maintaining existing Proctortrack implementations at 2U.

Setup Instructions
=================

As will be the case with all REST backends implementing the proctoring spec, one
doesn't need to configure much to get Proctortrack working on a
sandbox, e.g.::

    proctortrack:
      client_id: "<you'll need to fill these in with credentials from Proctortrack>"
      client_secret: "<you'll need to fill these in with credentials from Proctortrack>"
      base_url: 'https://prestaging.verificient.com'
      integration_specific_email: "proctortrack-support@edx.org"

In addition to adding these configurations, you'll also need to set up
a user which PT can authenticate as.

* Create a user group called ``proctortrack_review`` in Django admin
* Create a user, and associate it with that group
* Create an OAuth application
  (``/admin/oauth2_provider/application/``) pointing to the user
  you've created, and share the client_id with folks on the other end
  of the integration.
