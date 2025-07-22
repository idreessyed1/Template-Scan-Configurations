# Template-Scan-Configurations
A collection of ready-to-use scan configuration templates for Burp Scanner. Useful for setting up scans quickly and consistently.

These scan configurations are designed with the type of app in mind. The most common ones are:
<h1>Single-page application (SPA)</h1>
Loads a single HTML page and dynamically updates content as the user interacts with the app, without reloading the page.
Uses React — only one real page load at the start.
Navigating through playlists, songs, or search does NOT reload the page.
All updates are through JavaScript and API calls.
URLs change using pushState() but no HTML reload happens.
Perfect to observe: No full page reloads, dynamic partial content updates, real-time behavior.

<b>Multi-page application (MPA)</b>
Every link you click loads a brand new HTML page.
The browser fully reloads with a new URL (e.g., /History_of_the_Internet, /Cybersecurity).
Content is largely static per page.
No JavaScript needed to fetch content.
Perfect to observe: Page reloads, crawlable links, separate HTML per page.

<b>Static web app (Static)</b>
Every template/demo is fully static.
No user interaction, login, or backend.
Right-click > “View Page Source” shows all content upfront.
Content doesn’t change unless the files are manually edited.
Perfect to observe: Fixed HTML, fast loads, identical experience every time.

<b>Dynamic web app (Dynamic)</b>
URL changes for each product page (MPA structure), but content is generated dynamically.
Pricing, recommendations, availability vary per user/location.
Page source may not contain actual content without JS execution.
Uses AJAX, cookies, user sessions. 
Perfect to observe: Hidden inputs, JavaScript rendering, API responses, dynamic personalization.

The provided scan configurations are a template, a foundation, and hence should be treated as such. These scan configurations should work as it is based on the type of application they are used for, but for any further changes, either follow the docs below or contact support@portswigger.net:

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
