# Clouve app (app.clouve.com)

The Clouve app, offered by Clouve Inc, serves as the primary tool for their clients, facilitating the deployment and management of cloud applications.

## Release Notes


### Release 3.2.0:

- Display capacity of each deployment
- One password for app suites
- Fix the “subscription after trial period has expired is failing” issue
- Explain auto generated password dilemma
- Misunderstanding about subscription before trial period ends (the user thinks that just adding a payment method to their profile is enough)
- Tabbed App Library splitting app suits from apps
- Add serviceCapacity block in app attributes
    - Joomla
    - Moodle
    - ghost
    - Drupal
    - Gibbon
    - Education Suite
    - Professional Suite
    - SuiteCRM
    - OrangeHRM
    - Odoo
    - Osclass
    - ownCloud
    - DokuWiki
    - MediaWiki
- Error upon subscription
- Fix “Assigned To Me” orgSnapshot issue
- Decouple dns records from nginx-ingress-controller’s external ip
- GCP Backup and Restore namespaces (deployments)
    - Cluster level backup for namespaces


### Release 3.2.3:

- Remove Delete button for expired deployments to fix already paused issue
- Allow Cancel Subscription option for an active deployment (will pause)
- Allow subscribe after cancel (will resume)
- Allow authorized user deletion for orgs - Disable user instead to maintain history - Not Doable
- Subscription email address should come from the user (not the org) - Works as expected
- Pause should scale down StatefulSets as well
- FTA -> View deployments and support by client


### Release 3.2.4:

- Replace subdomain input with InputGroup
- Switch Estimate input to a dropdown
- FTA - Add assigned to me flag to orgSnapshot call
- FTA - Add a ButtonGroup to filter by tickets and deployments


### Release 3.2.5:

- Remove url and orgName fields from organization table
- Admin client list to be scrollable
- Admin client list export functionality
- Move all images to a cdn bucket
- Send email upon trial period expiration
- Fix deployment actions by checking whether the current action is already applied
- Fix email links


### Release 3.3.0:

- Add a capability to add a hostname (cname) through the UI
  - Create Deployment
    - Upgrade react-jsonschema-form
  - Move dns manipulation to thermo
    - Gibbon deployment is failing
  - Update Deployment to add/update/remove a custom domain
    - Update all charts
      - Check if updating a deployment overwrites passwords
        - New password is being generated but not used - Needs to be fixed
      - Use existingSecret
      - Add auto generated passwords
      - Fix UI for existing deployments by showing one Installed App
    - Implement UI to trigger dnsName/extraDnsName update
      - Fix ticket update
      - Fix ticket estimated time drop downs and styles
      - Create new thermo trigger for magneto
      - Fix - Canceling a deployment clears domain name
      - Fix - installed apps refresh issue
- Fix - Resolved status
- Fix - My Organization is not scrollable vertically on mobile
- Fix - Users is not scrollable horizontally on mobile


### Release 3.3.1:

- Create a bundle to include Moodle, Gibbon, and SuiteCRM (Education Management Suite - education-suite)
- Create a bundle to include Wordpress, Moodle, Gibbon, and SuiteCRM (Comprehensive Education Management Suite - education-suite-comprehensive)
- Add extraHosts to ingress manifests
- Test Deployments
- Test adding a Custom Domain for App Suites
- Test updating the Custom Domain for App Suites
  - Fix - Update button stays disabled even after changing Custom Domain field
  - Fix - Remove old dns record before updating dnsName
  - Fix - The value of property "_raw_data" is longer than 1048487 bytes
  - Fix - stateChange updates
- Test adding a Custom Domain for Apps
- Test updating the Custom Domain for Apps
  - Fix - Custom Domain update for Gibbon


### Release 3.3.2:
- Provide a way to sort apps within a serviceType category
- Expand “Custom Domain Name” by default if a value exists
- Add a capability to update domain names for sub applications of a bundle
    - Naked extra dns should be prefixed with www
        - Unless a subdomain is prepended
    - Create Deployment with custom domain
    - Update deployment’s custom domain
        - Deployment details should show custom domain for all apps
        - Custom Domain Name under settings should list all  possible hostnames for a bundle
- List included applications in bundles
- Fix routing from a support ticket to it’s corresponding deployment
- Display app name and version for custom domain name
- Gibbon - fix updated custom domain URL issue
- Add “Try Again” button to Custom Domain


### Release 3.4.0:

- Add a capability to scale up/down deployments’ capacities and their associated subscription plans
    - Allow user to select a capacity and associated subscription plan while creating a new deployment
    - Allow user to scale up/down existing deployments’ capacity
    - This feature is only available to users with a subscription
    - Show only selected capacity on checkout page
- Add orgTicketId as a label to namespaces to make it easier for agents to find tickets’ resources
- Check - Test create/prepare cluster locally and through cloud build
- Fix - Gibbon’s capacity is not getting applied properly
- Fix - Display limits only in “Allocated Resources” of the deployed applications to prevent confusion
- Fix - Prevent using the same Custom Domain Name with two different deployments
- Fix - Custom Domain Name is not reflected on namespace labels after launch
- Fix - Add spinners after triggering user actions
- Remove OrangeHRM in lieu of Odoo
- Fix - Gibbon’s “Base URL” issue preventing systems admins from updating system settings
- Fix - Updating profile picture does not enable the save button
- Fix - Deployment settings “Custom Domain Name” of bundled deployments do not show subdomains
- Fix - Allow the user to customize subdomains of apps within a deployment
- Test Launch/Subscribe & Apply/Scale functions of the all deployments


### Release 3.4.1:

- Moodle - add a cronjob to call cron.php every minute
- Increase the upload limit of nginx to 50MB
- Agent: Add organization id beside name on Clients tab to make it easier to find
- Agent: Add org id and tkt id on ticket details to make it easier to find

