# DCF Job Board

A job board website built for the DeKalb Chamber Foundation, connecting DeKalb, IL high school students with local employers offering trades employment opportunities.

## About

This project was built during my summer internship with the DeKalb Chamber Foundation to give students an easy way to browse and apply for trades jobs — electrical, plumbing, welding, HVAC, construction, and more — right in their own community. It links directly to employer application pages (or phone numbers, for businesses that prefer calls) and lets employers request new postings themselves through a built-in form.

## Features

* Filterable job listings by trade category and experience level (Entry, Apprentice, Journeyman)
* Job cards auto-sort by most recently updated
* Employer-submitted job posting requests via an in-page form (powered by Formspree)
* Supports both web application links and click-to-call phone numbers for employers without an online application
* Fully responsive layout for mobile and desktop
* Custom favicon, logo header, and DCF-branded color scheme

## Built With

* HTML5 / CSS3 / vanilla JavaScript (no frameworks)
* Google Fonts (Oswald, Inter)
* Formspree for form handling
* GitHub Pages for hosting

## What I Learned

* Structuring and styling a responsive layout from scratch using CSS Grid and Flexbox
* DOM manipulation for dynamic filtering, sorting, and content updates without a framework
* Proper use of semantic HTML — including why `href` belongs on `<a>` tags, not `<img>` tags
* Debugging GitHub Pages deployment issues (Jekyll processing, CDN propagation delays, `.nojekyll`)
* Handling form submissions with `fetch()` and displaying real-time status feedback to the user

## How to Run

Live site: [tylervilet.github.io/DCFJobBoard](https://tylervilet.github.io/DCFJobBoard/)

To run locally:
1. Clone the repo
2. Open `index.html` in VS Code
3. Right-click and select **Open with Live Server** (or open the file directly in a browser)

## Adding or Editing a Job Listing

Each job is a `.job-card` div in `index.html` with three data attributes that drive filtering and sorting:

* `data-category` — trade type (`electrical`, `plumbing`, `welding`, `hvac`, `construction`, `sheetmetal`, `masonry`, `automotive`, `other`)
* `data-level` — `entry`, `apprentice`, or `journeyman`
* `data-updated` — date last updated, in `YYYY-MM-DD` format (drives auto-sorting, newest first)

For the apply button, use a regular link for online applications:
```html
<a class="apply-btn" href="https://example.com/apply" target="_blank">Apply</a>
```
or a `tel:` link for employers who prefer phone calls:
```html
<a class="apply-btn" href="tel:+18155551234">Call: (815) 555-1234</a>
```
