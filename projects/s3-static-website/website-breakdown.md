# Website Breakdown

Static site built for Cloud Fitness Gym, deployed to Amazon S3.

## Pages

Home
<img src="Website%20Screenshots/1.%20Home%20page.png" width="1760">
Home, "why choose us" features and featured classes preview.

Plans
<img src="Website%20Screenshots/2.%20Plans.png" width="1792">
<img src="Website%20Screenshots/3.%20Plans%20continued.png" width="1747">
Pricing tiers (Student / Professional / Premium), day pass, corporate & senior rates.

Classes
<img src="Website%20Screenshots/4.%20Classes.png" width="1716">
Class descriptions + filterable weekly schedule table (by day)

Booking
<img src="Website%20Screenshots/5.%20Booking.png" width="1690">
Class booking form which submits to confirmation.html

Contact
<img src="Website%20Screenshots/6.%20Contact%20Us.png" width="1697">
Membership sign-up form, gym contact details and map which submits to confirmation.html

Confirmation
<img src="Website%20Screenshots/7.%20Booking%20confirmation.png" width="1655">
Reads submitted form data from the URL and displays a booking/sign-up summary with a generated reference number

Error
<img src="Website%20Screenshots/8.%20Error.png" width="1693">
Custom 404, set as the S3 error document

## Shared components
- `styles.css` — single stylesheet covering layout, navbar, cards, forms, pricing grid, schedule table, and responsive breakpoints
- `main.js` — handles:
  - mobile nav toggle (hamburger menu)
  - scroll-based navbar background change
  - fade-in-on-scroll animation (feature/class cards, section titles)
  - class schedule day-filter tabs
  - confirmation page: reads query parameters from the booking/sign-up form submission and renders the details and reference number for the client's side.

## Design notes
- No backend — booking and sign-up "submissions" are simulated via GET form parameters.
- Fully static, so it maps directly onto S3 static website hosting with no server required.
