# Template-Scan-Configurations
A collection of ready-to-use scan configuration templates for Burp Scanner. Useful for setting up scans quickly and consistently.

The provided scan configurations are a template, a foundation, and hence should be treated as such. These scan configurations should work as it is based on the type of application they are used for, but for any further changes, either follow the following docs or contact support@portswigger.net

https://portswigger.net/burp/documentation/scanner/scan-configurations/crawl-options
https://portswigger.net/burp/documentation/scanner/scan-configurations/audit-options

The scan configuration templates are categorised against the application type. Here are a few details about each scan configuration provided:

<h2>Authenticated scan configuration</h2>
The <i>'Crawl using my provided logins only'</i> toggle is enabled, which means Burp will only run an authenticated crawl of the app (if authentication is set up in Burp Suite). The crawl limit is set to the default value of 150 minutes.

The crawl strategy is set to <i>'Most Complete'</i> for Single-page or Dynamic apps for a more comprehensive crawl, while it is set to <i>'Fastest'</i> for Multi-page and Static apps. For the Single-page apps, the <i>'Click all pointer cursor elements'</i> toggle is also enabled, which allows for a better crawl by using non-standard clickable elements on the site.

<h2>Comprehensive scan configuration</h2>
A comprehensive scan configuration will allow you to crawl the app unauthenticated and then authenticated (if authentication is set up). The rest of the settings are similar to those in the previous section.

<h2>Single session scan configuration</h2>
This scan configuration allows you to scan applications that only allow one session at a time. The crawl strategy remains the same based on the app's type, with the addition of scan settings that accommodate the one-session requirement, and also setting the parallel crawl and audit to false.
