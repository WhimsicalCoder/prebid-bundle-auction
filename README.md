# Prebid Page Bundle Auction

Programmatic roadblocks for the open web: a proposed design for Prebid.js that lets one buyer win multiple ad slots on the same page view through a takeover deal.

This is a proposed extension of [prebid/Prebid.js#15719](https://github.com/prebid/Prebid.js/issues/15719) (whole page takeover on deal response). It builds on the deal metadata (`bid.meta.deal`) and priority bids (`allowPriorityBids`) that Prebid.js already ships.

What it adds:

- **Partial takeovers:** a buyer wins every slot on the page that matches its creative sizes (exact match, no letterboxing), with a minimum slot count. An all-or-nothing mode covers the case in #15719.
- **Revenue-safe by default:** a non-sponsorship takeover wins only if it beats the sum of the best separate bids on its slots, plus a publisher-set premium. Sponsorship takeovers win by deal priority.
- **Exclusivity:** optionally keeps named competitors out of the other slots on the page.
- **No DSP changes needed:** buyers target a normal PMP deal, and the SSP adds `ext.prebid.deal.takeover` to the bids.

## Status

Draft spec (v0.2), seeking feedback from Prebid maintainers, SSPs, publishers and buyers. No code yet.

- **[Read the spec](SPEC.md)**
- Feedback: open an issue in this repo, or comment on [#15719](https://github.com/prebid/Prebid.js/issues/15719)

## License

[Apache 2.0](LICENSE), the same license as Prebid.js.
