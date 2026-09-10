# JSON-LD CDATA Wrapper QA Demo Site

This static site is designed to test crawler handling of multiple JSON-LD blocks, CDATA-style JavaScript comment wrappers, and invalid JSON.

## Pages

- `index.html` - overview and crawler configuration
- `wrapped-events.html` - two wrapped JSON-LD blocks
- `standard-events.html` - two standard JSON-LD blocks
- `mixed-invalid.html` - wrapped valid + standard valid + wrapped invalid JSON-LD

## Recommended crawler field

- Field name: `json_ld_names`
- Selector type: `JSON-LD`
- Selector: `$.name`
- Multi-valued: `Yes`

## Expected values

### wrapped-events.html
- First Event
- Second Event

### standard-events.html
- Standard Event One
- Standard Event Two

### mixed-invalid.html
- Wrapped Valid Event
- Standard Valid Event

The invalid JSON block should be ignored without failing the crawl.

## Other JSON-LD paths available on wrapped-events.html

- `$.description`
- `$.startDate`
- `$.isAccessibleForFree`
- `$.maximumAttendeeCapacity`
- `$.ratingValue`
- `$.location.name`
- `$.location.address.addressLocality`
- `$.location.address.addressRegion`
- `$.location.address.postalCode`
- `$.location.geo.latitude`
- `$.location.geo.longitude`

## Hosting

You can deploy this folder to GitHub Pages, Render static site, Netlify, or any static web server.

For local testing:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000/`.

Note: update `sitemap.xml` URLs to your real deployed hostname if you want the sitemap to point to the hosted site.


## Additional real-world Event sample

`alumni-social-event.html` contains the supplied Alumni Social Event JSON-LD wrapped in `/*<![CDATA[*/ ... /*]]>*/`. Use JSON-LD paths such as `$.name`, `$.startDate`, `$.image.url`, `$.organizer.name`, and `$.additionalProperty[0].value`.
