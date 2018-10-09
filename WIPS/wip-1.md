---
wip: 1
title: WIP Purpose and Guidelines
author: Martin Becze <mb@ethereum.org>, Hudson Jameson <hudson@ethereum.org>, and others
        https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1.md
status: Active
type: Meta
created: 2015-10-27, 2017-02-01
---

## What is an WIP?

WIP stands for Wisdom Improvement Proposal. An WIP is a design document providing information to the Wisdom community, or describing a new feature for Wisdom or its processes or environment. The WIP should provide a concise technical specification of the feature and a rationale for the feature. The WIP author is responsible for building consensus within the community and documenting dissenting opinions.

## WIP Rationale

We intend WIPs to be the primary mechanisms for proposing new features, for collecting community technical input on an issue, and for documenting the design decisions that have gone into Wisdom. Because the WIPs are maintained as text files in a versioned repository, their revision history is the historical record of the feature proposal.

For Wisdom implementers, WIPs are a convenient way to track the progress of their implementation. Ideally each implementation maintainer would list the WIPs that they have implemented. This will give end users a convenient way to know the current status of a given implementation or library.

## WIP Types

There are three types of WIP:

- A **Standard Track WIP** describes any change that affects most or all Wisdom implementations, such as a change to the the network protocol, a change in block or transaction validity rules, proposed application standards/conventions, or any change or addition that affects the interoperability of applications using Wisdom. Furthermore Standard WIPs can be broken down into the following categories. Standards Track WIPs consist of three parts, a design document, implementation, and finally if warranted an update to the [formal specification].
  - **Core** - improvements requiring a consensus fork (e.g. [WIP5], [WIP101]), as well as changes that are not necessarily consensus critical but may be relevant to [“core dev” discussions](https://github.com/ethereum/pm) (for example, [WIP90], and the miner/node strategy changes 2, 3, and 4 of [WIP86]).
  - **Networking** - includes improvements around [devp2p] ([WIP8]) and [Light Wisdom Subprotocol], as well as proposed improvements to network protocol specifications of [whisper] and [swarm].
  - **Interface** - includes improvements around client [API/RPC] specifications and standards, and also certain language-level standards like method names ([WIP59], [WIP6]) and [contract ABIs]. The label “interface” aligns with the [interfaces repo] and discussion should primarily occur in that repository before an WIP is submitted to the WIPs repository.
  - **WRC** - application-level standards and conventions, including contract standards such as token standards ([WRC20]), name registries ([WRC26], [WRC137]), URI schemes ([WRC67]), library/package formats ([WIP82]), and wallet formats ([WIP75], [WIP85]).
- A **Meta WIP** describes a process surrounding Wisdom or proposes a change to (or an event in) a process. Process WIPs are like Standards Track WIPs but apply to areas other than the Wisdom protocol itself. They may propose an implementation, but not to Wisdom's codebase; they often require community consensus; unlike Informational WIPs, they are more than recommendations, and users are typically not free to ignore them. Examples include procedures, guidelines, changes to the decision-making process, and changes to the tools or environment used in Wisdom development. Any meta-WIP is also considered a Process WIP.

It is highly recommended that a single WIP contain a single key proposal or new idea. The more focused the WIP, the more successful it tends to be. A change to one client doesn't require an WIP; a change that affects multiple clients, or defines a standard for multiple apps to use, does.

An WIP must meet certain minimum criteria. It must be a clear and complete description of the proposed enhancement. The enhancement must represent a net improvement. The proposed implementation, if applicable, must be solid and must not complicate the protocol unduly.

## WIP Work Flow

Parties involved in the process are you, the champion or *WIP author*, the [*WIP editors*](#WIP-editors), and the [*Wisdom Core Developers*](https://github.com/ethereum/pm).

:warning: Before you begin, vet your idea, this will save you time. Ask the Wisdom community first if an idea is original to avoid wasting time on something that will be be rejected based on prior research (searching the Internet does not always do the trick). It also helps to make sure the idea is applicable to the entire community and not just the author. Just because an idea sounds good to the author does not mean it will work for most people in most areas where Wisdom is used. Examples of appropriate public forums to gauge interest around your WIP include [the Wisdom subreddit], [the Issues section of this repository], and [one of the Wisdom Gitter chat rooms]. In particular, [the Issues section of this repository] is an excellent place to discuss your proposal with the community and start creating more formalized language around your WIP.

Your role as the champion is to write the WIP using the style and format described below, shepherd the discussions in the appropriate forums, and build community consensus around the idea. Following is the process that a successful WIP will move along:

```
[ DRAFT ] -> [ ACCEPTED ] -> [ WIP ] -> [ ACTIVE ] -> [ FINAL ]
```

Each status change is requested by the WIP author and reviewed by the WIP editors. Use a pull request to update the status. Please include a link to where people should continue discussing your WIP. The WIP editors will process these requests as per the conditions below.

* **Draft** -- Once the first draft has been merged, you may submit follow-up pull requests with further changes to your draft until such point as you believe the WIP to be mature and ready to proceed to the next status. An WIP in draft status must be implemented to be considered for promotion to the next status (ignore this requirement for core WIPs).
  * :arrow_right: Last Call -- If agreeable, the WIP editor will assign Last Call status and set a review end date, normally 14 days later.
  * :x: Last Call -- A request for Last Call status will be denied if material changes are still expected to be made to the draft. We hope that WIPs only enter Last Call once, so as to avoid unnecessary noise on the RSS feed.
* **Accepted (Core WIPs only)** -- This WIP is in the hands of the Wisdom client developers.  Their process for deciding whether to encode it into their clients as part of a hard fork is not part of the WIP process.
  * :arrow_right: Final -- Standards Track Core WIPs must be implemented in at least three viable Wisdom clients before it can be considered Final. When the implementation is complete and adopted by the community, the status will be changed to “Final”.
* **Work in progress (WIP)** -- Once the champion has asked the Wisdom community whether an idea has any chance of support, they will write a draft WIP as a [pull request]. Consider including an implementation if this will aid people in studying the WIP.
  * :arrow_right: Draft -- If agreeable, WIP editor will assign the WIP a number (generally the issue or PR number related to the WIP) and merge your pull request. The WIP editor will not unreasonably deny an WIP.
  * :x: Draft -- Reasons for denying draft status include being too unfocused, too broad, duplication of effort, being technically unsound, not providing proper motivation or addressing backwards compatibility, or not in keeping with the [Wisdom philosophy](https://github.com/ethereum/wiki/wiki/White-Paper#philosophy).
* **Active** -- Some Informational and Process WIPs may also have a status of “Active” if they are never meant to be completed. E.g. WIP 1 (this WIP).
* **Final** -- This WIP represents the current state-of-the-art. A Final WIP should only be updated to correct errata.

Other exceptional statuses include:

* Deferred -- This is for core WIPs that have been put off for a future hard fork.
* Rejected -- An WIP that is fundamentally broken or a Core WIP that was rejected by the Core Devs and will not be implemented.
* Active -- This is similar to Final, but denotes an WIP which which may be updated without changing its WIP number.
* Superseded -- An WIP which was previously final but is no longer considered state-of-the-art. Another WIP will be in Final status and reference the Superseded WIP.

## What belongs in a successful WIP?

Each WIP should have the following parts:

- Preamble - RFC 822 style headers containing metadata about the WIP, including the WIP number, a short descriptive title (limited to a maximum of 44 characters), and the author details. See [below](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1.md#eip-header-preamble) for details.
- Simple Summary - “If you can’t explain it simply, you don’t understand it well enough.” Provide a simplified and layman-accessible explanation of the WIP.
- Abstract - a short (~200 word) description of the technical issue being addressed.
- Motivation (*optional) - The motivation is critical for WIPs that want to change the Ethereum protocol. It should clearly explain why the existing protocol specification is inadequate to address the problem that the WIP solves. WIP submissions without sufficient motivation may be rejected outright.
- Specification - The technical specification should describe the syntax and semantics of any new feature. The specification should be detailed enough to allow competing, interoperable implementations for any of the current Ethereum platforms (cpp-ethereum, go-ethereum, parity, ethereumJ, ethereumjs-lib, [and others](https://github.com/ethereum/wiki/wiki/Clients).
- Rationale - The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the feature is supported in other languages. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.
- Backwards Compatibility - All WIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The WIP must explain how the author proposes to deal with these incompatibilities. WIP submissions without a sufficient backwards compatibility treatise may be rejected outright.
- Test Cases - Test cases for an implementation are mandatory for WIPs that are affecting consensus changes. Other WIPs can choose to include links to test cases if applicable.
- Implementations - The implementations must be completed before any WIP is given status “Final”, but it need not be completed before the WIP is merged as draft. While there is merit to the approach of reaching consensus on the specification and rationale before writing code, the principle of “rough consensus and running code” is still useful when it comes to resolving many discussions of API details.
- Copyright Waiver - All WIPs must be in the public domain. See the bottom of this WIP for an example copyright waiver.

## WIP Formats and Templates

WIPs should be written in [markdown] format.
Image files should be included in a subdirectory of the `assets` folder for that WIP as follow: `assets/wip-X` (for wip **X**). When linking to an image in the WIP, use relative links such as `../assets/wip-X/image.png`.

## WIP Header Preamble

Each WIP must begin with an RFC 822 style header preamble, preceded and followed by three hyphens (`---`). The headers must appear in the following order. Headers marked with "*" are optional and are described below. All other headers are required.

` wip:` <WIP number> (this is determined by the WIP editor)

` title:` <WIP title>

` author:` <a list of the author's or authors' name(s) and/or username(s), or name(s) and email(s). Details are below.>

` * discussions-to:` \<a url pointing to the official discussion thread\>

 - :x: `discussions-to` can not be a Github `Pull-Request`.

` status:` <Draft | Last Call | Accepted | Final | Active | Deferred | Rejected | Superseded>

`* review-period-end: YYYY-MM-DD

` type: `<Standards Track (Core, Consensus, Crypto, Networking, WRC, Interface)  | Meta>

` * category:` <Core | Consensus | Crypto | Networking | WRC | Interface>

` created:` <date created on, in ISO 8601 (yyyy-mm-dd) format>

` * requires:` <WIP number(s)>

` * replaces:` <WIP number(s)>

` * superseded-by:` <WIP number(s)>

` * resolution:` \<a url pointing to the resolution of this WIP\>

#### Author header

The author header optionally lists the names, email addresses or usernames of the authors/owners of the WIP. Those who prefer anonymity may use a username only, or a first name and a username. The format of the author header value must be:

Random J. User &lt;address@dom.ain&gt;

or

Random J. User (@username)

if the email address or GitHub username is included, and

Random J. User

if the email address is not given.

Note: The resolution header is required for Standards Track WIPs only. It contains a URL that should point to an email message or other web resource where the pronouncement about the WIP is made.

While an WIP is a draft, a discussions-to header will indicate the mailing list or URL where the WIP is being discussed. As mentioned above, examples for places to discuss your WIP include [Ethereum topics on Gitter](https://gitter.im/ethereum/topics), an issue in this repo or in a fork of this repo, [Ethereum Magicians](https://ethereum-magicians.org/) (this is suitable for WIPs that may be contentious or have a strong governance aspect), and [Reddit r/ethereum](https://www.reddit.com/r/ethereum/). No discussions-to header is necessary if the WIP is being discussed privately with the author.

The type header specifies the type of WIP: Standards Track, Meta, or Informational. If the track is Standards please include the subcategory (core, consensus, crypto, networking, interface, or wRC).

The category header specifies the WIP's category. This is required for standards-track WIPs only.

The created header records the date that the WIP was assigned a number. Both headers should be in yyyy-mm-dd format, e.g. 2001-08-14.

WIPs may have a requires header, indicating the WIP numbers that this WIP depends on.

WIPs may also have a superseded-by header indicating that an WIP has been rendered obsolete by a later document; the value is the number of the WIP that replaces the current document. The newer WIP must have a Replaces header containing the number of the WIP that it rendered obsolete.

Headers that permit lists must separate elements with commas.

## Auxiliary Files

WIPs may include auxiliary files such as diagrams. Such files must be named WIP-XXXX-Y.ext, where “XXXX” is the WIP number, “Y” is a serial number (starting at 1), and “ext” is replaced by the actual file extension (e.g. “png”).

## Transferring WIP Ownership

It occasionally becomes necessary to transfer ownership of WIPs to a new champion. In general, we'd like to retain the original author as a co-author of the transferred WIP, but that's really up to the original author. A good reason to transfer ownership is because the original author no longer has the time or interest in updating it or following through with the WIP process, or has fallen off the face of the 'net (i.e. is unreachable or isn't responding to email). A bad reason to transfer ownership is because you don't agree with the direction of the WIP. We try to build consensus around an WIP, but if that's not possible, you can always submit a competing WIP.

If you are interested in assuming ownership of an WIP, send a message asking to take over, addressed to both the original author and the WIP editor. If the original author doesn't respond to email in a timely manner, the WIP editor will make a unilateral decision (it's not like such decisions can't be reversed :)).

## WIP Editors

The current WIP editors are

` * Nick Johnson (@arachnid)`

` * Casey Detrio (@cdetrio)`

` * Hudson Jameson (@Souptacular)`

` * Vitalik Buterin (@vbuterin)`

` * Nick Savers (@nicksavers)`

` * Martin Becze (@wanderer)`

## WIP Editor Responsibilities

For each new WIP that comes in, an editor does the following:

- Read the WIP to check if it is ready: sound and complete. The ideas must make technical sense, even if they don't seem likely to get to final status.
- The title should accurately describe the content.
- Check the WIP for language (spelling, grammar, sentence structure, etc.), markup (Github flavored Markdown), code style

If the WIP isn't ready, the editor will send it back to the author for revision, with specific instructions.

Once the WIP is ready for the repository, the WIP editor will:

- Assign an WIP number (generally the PR number or, if preferred by the author, the Issue # if there was discussion in the Issues section of this repository about this WIP)

- Merge the corresponding pull request

- Send a message back to the WIP author with the next step.

Many WIPs are written and maintained by developers with write access to the Ethereum codebase. The WIP editors monitor WIP changes, and correct any structure, grammar, spelling, or markup mistakes we see.

The editors don't pass judgment on WIPs. We merely do the administrative & editorial part.

## History

This document was derived heavily from [Bitcoin's BIP-0001] written by Amir Taaki which in turn was derived from [Python's PEP-0001]. In many places text was simply copied and modified. Although the PEP-0001 text was written by Barry Warsaw, Jeremy Hylton, and David Goodger, they are not responsible for its use in the Ethereum Improvement Process, and should not be bothered with technical questions specific to Ethereum or the WIP. Please direct all comments to the WIP editors.

December 7, 2016: WIP 1 has been improved and will be placed as a PR.

February 1, 2016: WIP 1 has added editors, made draft improvements to process, and has merged with Master stream.

March 21, 2018: Minor edits to accommodate the new automatically-generated WIP directory on [WIPs.ethereum.org](http://eips.ethereum.org/).

May 29, 2018: A last call process was added.

See [the revision history for further details](https://github.com/ethereum/EIPs/commits/master/EIPS/eip-1.md), which is also available by clicking on the History button in the top right of the WIP.

### Bibliography

[devp2p]: https://github.com/ethereum/wiki/wiki/%C3%90%CE%9EVp2p-Wire-Protocol
[Light Ethereum Subprotocol]: https://github.com/ethereum/wiki/wiki/Light-client-protocol
[whisper]: https://github.com/ethereum/go-ethereum/wiki/Whisper-Overview
[swarm]: https://github.com/ethereum/go-ethereum/pull/2959
[API/RPC]: https://github.com/ethereum/wiki/wiki/JSON-RPC
[contract ABIs]: https://github.com/ethereum/wiki/wiki/Ethereum-Contract-ABI
[interfaces repo]: https://github.com/ethereum/interfaces
[the Ethereum subreddit]: https://www.reddit.com/r/ethereum/
[one of the Ethereum Gitter chat rooms]: https://gitter.im/ethereum/
[pull request]: https://github.com/ethereum/EIPs/pulls
[formal specification]: https://github.com/ethereum/yellowpaper
[the Issues section of this repository]: https://github.com/ethereum/EIPs/issues
[markdown]: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet
[Bitcoin's BIP-0001]: https://github.com/bitcoin/bips
[Python's PEP-0001]: https://www.python.org/dev/peps/

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
