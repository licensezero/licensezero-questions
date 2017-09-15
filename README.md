If you're having a problem using License Zero, [e-mail support](mailto:support@artlessdevices.com).

To suggest a question about License Zero for this page, open an issue or pull request [on GitHub](https://github.com/licensezero/licensezero-questions).

**Do _not_ put confidential information about you, your work, or your clients in issues or pull requests.  Do _not_ ask for legal advice on GitHub, or try to disguise requests for legal advice as general questions or hypotheticals.  You don't want advice from anybody dumb enough to fall for that.**

## Are you my lawyer?

No.  [Not even close](https://licensezero.com/terms/service).

## What about tax?

Tax rules about software license sales remain unfortunately complex.  In the United States, for example, some states don't charge any sales tax at all on sales of "canned", non-custom software sold without physical media.  Others tax transactions either from or to their jurisdiction differently, along those dimensions.

In the future, License Zero may offer integration with a tax calculation and reporting service.  On first pass, existing services offer too much of the wrong thing, too little of what's actually needed, and usually too little actual warranty or risk protection to recommend.  For now, then, licensors should handle their own tax reporting, using the [ISO 3166-2](https://en.wikipedia.org/wiki/ISO_3166-2) codes associated with licensors, licensees, and waiver beneficiaries to guide them.

## Can License Zero packages depend one on another?

Yes.  Say that Package A depends on Package B:

- The maintainer of A will almost certainly require a private license or waiver for use of Package B, since selling software for money falls under Condition 3 of the public license.

- A not-for-profit user of Package A doesn't need any private license or waiver, either for Package A, or for Package B.

- A for-profit user of Package A needs a private license or waiver for Package A, as well as a private license or waiver for Package B.  `l0-quote` and `l0-buy` recurse all of `node_modules`, and will pick up both A and B, assuming they have proper metadata.

## How do I handle contribution?

License Zero does not mandate any particular approach to contribution management or licensing.  It's flexible.  There is room to work on new approaches, and also a few readily available options:

1.  Contributors to License Zero projects may publicly license their contributions under the terms of an Open Source license, such as [BSD-2-Clause](https://spdx.org/licenses/BSD-2-Clause).  Commercial users will still need private licenses or waivers for the primary work by the License Zero licensor-maintainer, but can use the contributions under the Open Source terms.  The maintainer might choose to reward contributors with waivers, and contributors can attempt to negotiate for waivers to secure their contributions.  `CONTRIBUTING.md` or similar can make clear that there is a standing offer: "If you publicly license your patch BSD-2-Clause, I will give you a waiver for commercial use of my original work."

2.  License Zero licensors can "stack" License Zero metadata in `package.json`'s `licensezero` property.  A fork of a License Zero package may require two private licenses or waivers to use commercially: one for the original work, one for the License Zero work on the fork.

## What's the crypto situation?

[licensezero.com](https://licensezero.com) creates and holds an [Ed25519](https://ed25519.cr.yp.to/) keypair in escrow for each licensor.  The server also has its own, "agent" keypair.

Public keys are in NaCl, rather than SUPERCOP, format.  All signatures are detached.  Everything is hex encoded.  At present, the server uses [sodium-native](https://www.npmjs.com/package/sodium-native), and the CLI uses [TweetNaCL](https://www.npmjs.com/package/tweetnacl).

NGINX terminates TLS with a certificate from [Let's Encrypt](https://letsencrypt.org/), and you can, too.
