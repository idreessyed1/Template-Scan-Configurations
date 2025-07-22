# Template-Scan-Configurations
A collection of ready-to-use scan configuration templates for Burp Scanner. Useful for setting up scans quickly and consistently.

These scan configurations are designed with the type of app in mind. The most common ones are:

<h3>Single-page application (SPA)</h3>

- Loads a single HTML page and dynamically updates content as the user interacts with the app, without reloading the page.
- Uses React — only one real page load at the start.
- Navigating through playlists, songs, or search does NOT reload the page.
- All updates are through JavaScript and API calls.
- URLs change using pushState() but no HTML reload happens.
- Perfect to observe: No full page reloads, dynamic partial content updates, real-time behavior.

<h3>Multi-page application (MPA)</h3>

- Every link you click loads a brand new HTML page.
- The browser fully reloads with a new URL (e.g., /History_of_the_Internet, /Cybersecurity).
- Content is largely static per page.
- No JavaScript needed to fetch content.
- Perfect to observe: Page reloads, crawlable links, separate HTML per page.

<h3>Static web app (Static)</h3>

- Every template/demo is fully static.
- No user interaction, login, or backend.
- Right-click > “View Page Source” shows all content upfront.
- Content doesn’t change unless the files are manually edited.
- Perfect to observe: Fixed HTML, fast loads, identical experience every time.

<h3>Dynamic web app (Dynamic)</h3>

- URL changes for each product page (MPA structure), but content is generated dynamically.
- Pricing, recommendations, availability vary per user/location.
- Page source may not contain actual content without JS execution.
- Uses AJAX, cookies, user sessions. 
- Perfect to observe: Hidden inputs, JavaScript rendering, API responses, dynamic personalization.

The provided scan configurations are a template, a foundation, and hence should be treated as such. These scan configurations should work as it is based on the type of application they are used for, but for any further changes, either follow the docs below or contact support@portswigger.net:

https://portswigger.net/burp/documentation/scanner/scan-configurations/crawl-options
https://portswigger.net/burp/documentation/scanner/scan-configurations/audit-options

These configs represent a progression from speed-focused (multi-page) to thoroughness-focused (SPA configs), with the single session variant adding session safety for complex application states.

# Configuration Summaries

<h3>Multi-page - Comprehensive.json</h3>
  - Purpose: Fast scanning for traditional multi-page applications
  - Key Settings:
    - Uses fastest crawl strategy (speed-optimized)
    - 90-minute maximum crawl time limit
    - Allows both anonymous and authenticated crawling
  - Best For: Quick comprehensive scans of multi-page web applications with time constraints

<h3>Multi-page - Authenticated.json</h3>
  - Purpose: Fast authenticated scanning for multi-page applications
  - Key Settings:
    - Uses fastest crawl strategy (speed-optimized)
    - 60-minute maximum crawl time limit
    - Only uses provided login credentials (no anonymous crawling)
  - Best For: Quick authenticated scans of multi-page applications where login areas are the focus

<h3>Multi-page - single session.json</h3>
  - Purpose: Session-safe scanning for multi-page applications
  - Key Settings:
    - Uses normal crawl strategy (balanced approach)
    - 150-minute maximum crawl time limit
    - Authenticated-only crawling
    - Single-threaded scanning (max 1 item in progress)
    - Crawling and auditing run sequentially, not in parallel
  - Best For: Multi-page applications that can only handle one active session at a time

<h3>Single-page App - Comprehensive.json</h3>
  - Purpose: Thorough scanning for single-page applications
  - Key Settings:
    - Most complete crawl strategy (thoroughness-optimized)
    - Enables interaction with all clickable UI elements
    - Allows both anonymous and authenticated crawling
  - Best For: Complete testing of SPAs including both public and authenticated areas

<h3>Single-page App - Authenticated Only.json</h3>
  - Purpose: Thorough authenticated scanning for SPAs
  - Key Settings:
    - Most complete crawl strategy (thoroughness-optimized)
    - Only uses provided login credentials (no anonymous crawling)
    - Enables interaction with all clickable UI elements
  - Best For: Deep authenticated testing of single-page applications where login is required

<h3>Single-page App - single session.json</h3>
  - Purpose: Sequential, session-safe scanning for SPAs
  - Key Settings:
    - Most complete crawl strategy (thoroughness-optimized)
    - Authenticated-only crawling
    - Enhanced UI interaction capabilities
    - Single-threaded scanning (max 1 item in progress)
    - Crawling and auditing run sequentially, not in parallel
  - Best For: SPAs that can only handle one active session at a time

  These configs represent a 2x3 matrix approach:
  - Multi-page apps: Progress from fastest (Comprehensive) → fastest authenticated (Authenticated) → careful session handling (Single Session)
  - Single-page apps: Progress from thorough coverage (Comprehensive) → authenticated focus (Authenticated Only) → session-safe thoroughness (Single Session)
