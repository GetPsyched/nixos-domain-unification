# NixOS Domain Unification

## Summary

Merge `nix.dev` into `docs.nixos.org` maintaining one canonical domain for all things Nix.

## Motivation

- Having both `nixos.org` and `nix.dev` is not great because they may seem to be owned by different entities.

## Detailed Design

- Move the contents of `nix.dev` to the subdomain `docs.nixos.org`.
- Redirect any traffic from `nix.dev` to `docs.nixos.org`.

### Ownership

Both nixos.org and nix.dev are already controlled by the NixOS foundation, so there's no change in ownership.

### Sources

The source for the new `docs.nixos.org` will use the same source as the current `nix.dev`: https://github.com/NixOS/nix.dev

## Drawbacks

- Confusion regarding docs being for Nix and not NixOS.

## Alternatives

- Try to get the registered but unused `nix.org`
  - (+) Shorter than `nixos.org`
  - (-) As a three-letter domain name it would likely be very expensive, probably in the order of $10'000 to $100'000 to buy
- Use `nix-platform.org` or `nix-platform.com` (@infinisil squatted these for now in case we want to use one)
  - (+) Would also allow establishing the term _Nix Platform_ as the combination of all official Nix projects, mainly including Nix, NixOS and Nixpkgs.
  - (-) _Nix Platform_ is [not a widely agreed-upon term](https://github.com/NixOS/nix.dev/pull/575#pullrequestreview-1455203487). It would require an independent discussion to establish it, and thus unduly grow the scope of this proposal.
  - (-) Those domain names are rather long.
- Moving the current contents of `nix.dev` under `docs.nixos.org`
  - (+) Allows keeping `nixos.org` as the canonical domain
  - (-) Doesn't avoid the confusion regarding NixOS
- Trivial alternative of not doing anything and keeping both `nix.dev` and `nixos.org` as official websites.
  - (+) Doesn't require any effort
  - (-) Doesn't avoid the confusions about officiality of `nix.dev` and non-NixOS uses

## Prior art

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
