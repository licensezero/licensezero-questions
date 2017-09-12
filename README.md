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
