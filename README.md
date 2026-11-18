# Prebid Page Takeover Module

Programmatic roadblocks for the open web: a proposed optional Prebid.js module that lets one buyer win multiple ad slots on the same page view through a takeover deal.

This is a proposed design for [prebid/Prebid.js#15719](https://github.com/prebid/Prebid.js/issues/15719) (whole page take over on deal response), updated after maintainer feedback there. It builds on the deal metadata (`bid.meta.deal`) and priority bids that Prebid.js already ships.

What it does:

- **Three modes:** take every slot (`all`), every slot in view (`viewport`), or as many matching slots as possible with a minimum count (`max`).
- **Uses Prebid's existing ranking:** priority tier first on each slot, then the takeover's summed desirability against the best other bids on those slots.
- **Exclusivity:** optionally keeps named competitors out of the other slots on the page.
- **Analytics-friendly:** each slot keeps its own price, with a takeover group id and a group-level event.
- **No DSP changes needed:** buyers target a normal PMP deal, and the SSP adds `ext.prebid.deal.takeover` to the bids.

## Status

Draft spec (v0.3), in discussion on #15719. No code yet.

- **[Read the spec](SPEC.md)**
- Feedback: comment on [#15719](https://github.com/prebid/Prebid.js/issues/15719), or open an issue in this repo

## License

[Apache 2.0](LICENSE), the same license as Prebid.js.
