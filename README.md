# NixOS Domain Unification

## Summary

Merge `nix.dev` into `docs.nixos.org` to have a single canonical domain for all things Nix.

## Motivation

- Having both `nixos.org` and `nix.dev` is not great because they may seem to be owned by different entities.
- It also creates ambiguity about which one should be the proper one, because neither is a perfect match

## Detailed Design

- Change the Netlify domain of `nix.dev` to `docs.nixos.org`
- Redirect any traffic from `nix.dev` to `docs.nixos.org`.

### Ownership

Both `nixos.org` and `nix.dev` are already owned by the NixOS Foundation, so there's no change in ownership.

### Sources

The source for the new `docs.nixos.org` will use the same source as the current `nix.dev`: https://github.com/NixOS/nix.dev

## Drawbacks

- Confusion regarding docs being for Nix and not NixOS.

## Alternatives

- Move everything from `nixos.org` to `nix.dev` instead.
  - (-) Very hard to do technically, as `nixos.org` has various subdomains and services
  - (-) Very hard to agree on, as `nixos.org` has been used for about 20 years now
  - (+) `nix.dev` is somewhat better of a domain name, since it makes it clearer that NixOS isn't necessary to use Nix
  - (-) `.dev` implies it's for developers, which is a [point of contention](https://github.com/nix-rfc-canonical-domain/rfcs/issues/11)
  - (-) `.dev` as a TLD also have [long-term stability problems](https://github.com/nix-rfc-canonical-domain/rfcs/issues/10)
- Move everything to a new but more fitting domain name
  - (-) This is an orthogonal effort and can be done later too
  - (-) As with the above alternative, hard to do technically and to agree on
  - Suggested alternatives have been:
    - `nix.org`
      - (+) Undoubtedly the ideal domain name
      - (-) As a three-letter domain name it would likely be very expensive, probably in the order of $10'000 to $100'000 to buy
    - `nix-platform.org` or `nix-platform.com` (@infinisil squatted these for now in case we want to use one)
      - (+) Would also allow establishing the term _Nix Platform_ as the combination of all official Nix projects, mainly including Nix, NixOS and Nixpkgs.
        - (-) _Nix Platform_ is [not a widely agreed-upon term](https://github.com/NixOS/nix.dev/pull/575#pullrequestreview-1455203487). It would require an independent discussion to establish it, and thus unduly grow the scope of this proposal.
      - (-) Those domain names are rather long.
    - `nix-lang.org`
      - (+) Some other languages use this pattern as well (e.g. `elixir-lang.org`)
      - (-) Gives the impression that the ecosystem revolves around the language, which not fully true and increases confusion.
- Trivial alternative of not doing anything and keeping both `nix.dev` and `nixos.org` as official websites.
  - (+) Doesn't require any effort
  - (-) Doesn't avoid the confusions about officiality of `nix.dev` and non-NixOS uses

## Prior art

- https://github.com/NixOS/nix.dev/issues/869
- https://github.com/NixOS/foundation/issues/34
- https://github.com/NixOS/nix.dev/issues/290
- https://github.com/NixOS/nixos-homepage/issues/633
- https://discourse.nixos.org/t/nix-related-domains-that-i-control/10034
- https://github.com/NixOS/nix.dev/issues/285
- https://github.com/NixOS/nixos-homepage/pull/882
- https://github.com/NixOS/nixos-homepage/issues/828

## Unresolved questions

- What if there were to be docs on NixOS?

## Future work

- Rework the design of the new `docs.nixos.org` to be consistent with the rest of the website.
- Maybe move `nixos.org/guides/*` to `docs.nixos.org/guides/*`.
