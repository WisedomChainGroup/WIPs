# WIPs [![Gitter](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/ethereum/EIPs?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)
Wisdom Improvement Proposals (WIPs) describe standards for the Ethereum platform, including core protocol specifications, client APIs, and contract standards.

A browsable version of all current and draft WIPs can be found on [the official WIP site](http://eips.ethereum.org/).

# Contributing

 1. Review [WIP-1](WIPS/wip-1.md).
 2. Fork the repository by clicking "Fork" in the top right.
 3. Add your WIP to your fork of the repository. There is a [template WIP here](wip-X.md).
 4. Submit a Pull Request to Wisdom's [WIPs repository](https://github.com/ethereum/EIPs).

Your first PR should be a first draft of the final WIP. It must meet the formatting criteria enforced by the build (largely, correct metadata in the header). An editor will manually review the first PR for a new WIP and assign it a number before merging it. Make sure you include a `discussions-to` header with the URL to a discussion forum or open GitHub issue where people can discuss the WIP as a whole.

If your WIP requires images, the image files should be included in a subdirectory of the `assets` folder for that WIP as follow: `assets/wip-X` (for wip **X**). When linking to an image in the WIP, use relative links such as `../assets/wip-X/image.png`.

Once your first PR is merged, we have a bot that helps out by automatically merging PRs to draft WIPs. For this to work, it has to be able to tell that you own the draft being edited. Make sure that the 'author' line of your WIP contains either your Github username or your email address inside <triangular brackets>. If you use your email address, that address must be the one publicly shown on [your GitHub profile](https://github.com/settings/profile).

When you believe your WIP is mature and ready to progress past the draft phase, you should do one of two things:

 - **For a Standards Track WIP of type Core**, ask to have your issue added to [the agenda of an upcoming All Core Devs meeting](https://github.com/ethereum/pm/issues), where it can be discussed for inclusion in a future hard fork. If implementers agree to include it, the WIP editors will update the state of your WIP to 'Accepted'.
 - **For all other WIPs**, open a PR changing the state of your WIP to 'Final'. An editor will review your draft and ask if anyone objects to its being finalised. If the editor decides there is no rough consensus - for instance, because contributors point out significant issues with the WIP - they may close the PR and request that you fix the issues in the draft before trying again.

# WIP Status Terms
* **Draft** - an WIP that is undergoing rapid iteration and changes
* **Last Call** - an WIP that is done with its initial iteration and ready for review by a wide audience
* **Accepted** - a core WIP that has been in Last Call for at least 2 weeks and any technical changes that were requested have been addressed by the author
* **Final (non-Core)** - an WIP that has been in Last Call for at least 2 weeks and any technical changes that were requested have been addressed by the author.
* **Final (Core)** - an WIP that the Core Devs have decide to implement and release in a future hard fork or has already been released in a hard fork
* **Deferred** - an WIP that is not being considered for immediate adoption. May be reconsidered in the future for a subsequent hard fork.

# Preferred Citation Format

The canonical URL for a WIP that has achieved draft status at any point is at https://eips.ethereum.org/. For example, the canonical URL for WRC-165 is https://eips.ethereum.org/EIPS/eip-165.
