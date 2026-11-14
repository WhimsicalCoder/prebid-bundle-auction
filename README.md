# Prebid Page Bundle Auction

Programmatic roadblocks for the open web: an open-source Prebid.js module that lets one buyer win multiple ad slots on the same page view as a bundle.

Today, Prebid and OpenRTB auction each ad slot on its own. The only way to own a whole page is a Programmatic Guaranteed roadblock, negotiated with one publisher at a time. This module adds a **page bundle auction** next to the normal one:

- A buyer bids for every slot on the page that matches its creative sizes (exact match, no letterboxing), with a minimum slot count.
- The bundle wins only if it beats the sum of the best separate bids on those slots, plus a publisher-set premium. **Publisher revenue can't drop.**
- Optional **exclusivity** keeps named competitors out of the other slots on the page.
- **No DSP changes needed in v1:** buyers target a normal PMP deal, and SSP adapters map bundle deal IDs to an `ext.bundle` object.

## Status

Draft spec, seeking feedback from Prebid maintainers, SSPs, publishers and buyers. No code yet.

- 📄 **[Read the spec](SPEC.md)**
- 💬 Feedback: open an issue in this repo

## License

[Apache 2.0](LICENSE), the same license as Prebid.js.
