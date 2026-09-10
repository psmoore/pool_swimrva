# SwimRVA Competition Pool page — Pool Relay embed preview

An unofficial replica of the SwimRVA **Competition Pool** schedule page with the live
[Pool Relay](https://www.poolrelay.com) calendar in place of the hand-maintained
week-by-week tables.

**This is not a SwimRVA website.** The official site is <https://swimrichmond.org>.
This is a working preview of one proposed change to it, built so the change can be
looked at rather than described.

## What it is

`index.html` is a single self-contained page. It reproduces the existing page — header
and navigation, masthead image, the blue September-closures note, the pool description,
the footer — and replaces the "Filter by week" dropdown and its four weekly tables with:

```html
<iframe src="https://www.poolrelay.com/embed/c25bEeGnduSvRKXdcUoldP"
        width="100%" height="760" style="border:0"
        title="SwimRVA pool schedule"></iframe>
```

## What changes for SwimRVA

- One calendar instead of four week tables. It always shows the current week, so there is
  no stale week left behind and no "filter by week" list to extend.
- It can say **which** lanes, not only how many. The live page says "6 lanes".
- Competition, Instructional and Therapy become a dropdown on one calendar rather than
  three separate pages.
- The September closures list is redundant: a closure is an event, so it appears in the
  schedule itself.

## Notes

- Hand-written HTML and CSS. It will not drop into their CMS as-is; on the live site the
  change is to delete the table block and add a code block containing the iframe.
- The masthead image is hotlinked from swimrichmond.org. The logo is their own inline SVG,
  copied so the page renders without a network round-trip.
- Navigation links point at the live site, so they work from any hosting path.
- The page carries a visible "unofficial preview" ribbon and `noindex`.

## Local preview

```
python3 -m http.server 8801
```

Then open <http://localhost:8801/>.
