# Shop & Sip — shopnsip.nstruct.io

Static page. No build step. Drop these four files at the repo root and point
Vercel at it (Framework Preset: Other, no build command, output dir: ./).

    index.html            the page (hero photo is inlined, no image deps)
    og.jpg                1200x630 social card
    favicon.png
    apple-touch-icon.png

## Form

Posts to the Google Form "Nstruct - Shop N Sip" via a no-cors POST.
Field map lives at the top of the <script> block in index.html:

    entry.1564216555   Full Name
    entry.535367127    Email
    entry.600691027    Brand or company
    entry.798362996    Coming as        (Brand Owner | Brand Operator | Agency or Partner)
    entry.112218098    Keep me in the loop   value: "Yes"

The select options MUST match the Google Form's option labels exactly, or
Google silently discards that answer. Same for LOOP_VALUE.

no-cors means the browser cannot read Google's response, so the success
message shows once the request leaves the browser. It is not a confirmation
that Google accepted it.

## Known limits

- Seat meter is static (75 guests / invite only). Google Forms cannot return
  a count. Swap to an Apps Script web app if you want it live again.
- Venue address is deliberately not on the page; it goes out with the
  confirmation email.
