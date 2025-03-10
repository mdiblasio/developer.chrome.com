---
layout: layouts/doc-post.njk
title: FAQs
subhead: The Privacy Sandbox is a series of proposals to satisfy cross-site use cases without third-party cookies or other tracking mechanisms.
description: "Frequently asked questions about the Privacy Sandbox proposals"
date: 2021-09-21
updated: 2021-09-22
authors:
	- samdutton
---

{% Aside %}
This page answers some common questions about the Privacy Sandbox. The range of questions in this
initial version is in no way comprehensive, and we expect the list of topics under each heading to
grow substantially over time.

Contributions are welcome.  If you have a Privacy Sandbox question that's not answered here:

-  Ask the question on the
   [Privacy Sandbox Developer Support repo](https://github.com/GoogleChromeLabs/privacy-sandbox-dev-support).
-  Ask the question in a
   [feature request](https://github.com/GoogleChrome/developer.chrome.com/issues/new?assignees=&labels=feature+request%2CP2&template=feature_request.md&title=)
   on the repo for this site.

If you have an answer to your question, feel free to add it.
{% endAside %}


## General questions

### Why do we need the Privacy Sandbox?

The Privacy Sandbox initiative has two core aims:

-  Develop replacement solutions to support web use cases and business models without enabling
   users to be tracked across sites, and avoiding cross-site tracking users aren't aware of.
-  Phase out support for third-party cookies and other forms of tracking when new solutions are
   in place.

### Who is working on the Privacy Sandbox?

The Privacy Sandbox is a set of proposed web standards.  
Chrome and other browser vendors, as well as ad companies and other stakeholders, have offered more
than 30 proposals to date, which can be found in the
[public resources of W3C groups](https://github.com/w3c/web-advertising#ideas-and-proposals-links-outside-this-repo).
These proposals cover a wide variety of use cases and requirements.

### How can I get involved?

-  Participate in incubation, testing and refinement of the APIs:  
   [How to participate in the Privacy Sandbox initiative](https://developer.chrome.com/blog/privacy-sandbox-participate/)
-  As a developer, join discussions or ask questions:  
   [Privacy Sandbox Developer Support](https://github.com/GoogleChromeLabs/privacy-sandbox-dev-support)

For questions about specific APIs you can also file an issue on the [GitHub repo for an API
Explainer](https://developer.chrome.com/docs/privacy-sandbox/status/).

### I don't understand the terminology in the API explainers. Is there a glossary?

Yes: the [Privacy Sandbox glossary](https://deploy-preview-543--dcc-private.netlify.app/docs/privacy-sandbox/glossary/).

### When will the Privacy Sandbox APIs be implemented?

The [Privacy Sandbox timeline](https://privacysandbox.com/timeline/) shows the roadmap to phasing
out third-party cookies. Additional current information for individual APIs is available on the
[implementation status page](https://deploy-preview-543--dcc-private.netlify.app/docs/privacy-sandbox/status/).

### Are the Privacy Sandbox APIs in Chromium or Chrome?

The APIs are implemented in [Chromium](https://en.wikipedia.org/wiki/Chromium_(web_browser)), which
is the open-source browser used to make Chrome. Code for the Privacy Sandbox APIs can be accessed
via [Chromium Code Search](https://source.chromium.org/search?q=floc). You can [download
Chromium](http://chromium.org/getting-involved/download-chromium), then [run it with
flags](https://www.chromium.org/developers/how-tos/run-chromium-with-flags) to enable access to APIs
that are in the process of implementation.

### How can I try out Privacy Sandbox APIs that aren't yet enabled in Chrome by default?

As an API progresses through development in Chrome, there are multiple ways it may be made available
for testing.

-  **For a single user via command line flags**  
   Early features may often provide a specific command line flag to allow a developer to launch the
   browser with the new feature enabled.
-  **For a single user via chrome://flags**  
   As a feature progresses, it's often made available as an experimental flag within the more
   accessible chrome://flags interface. These can also be enabled via the command line. The
   #enable-experimental-web-platform-features bundles together current experimental features.
-  **For your users, in an origin trial**  
   Once an iteration of a new feature is code-complete and relatively stable, an [origin
   trial](https://web.dev/origin-trials) may be provided to allow individual sites to enable the
   feature for Chrome users on their site. If an [origin trial](https://web.dev/origin-trials) is
   available for an API you want to test with your users, [register for the origin
   trial](https://developer.chrome.com/origintrials/#/trials/active) and provide a valid trial
   token with every page load.
-  **For users of early Chrome releases** When a feature is approved to ship in a given release, 
   it will progress through Canary and Beta channels before reaching Stable. The feature will be 
   enabled by default for all users of those channels.

{% Aside %}  
Chrome offers the ability for users to opt-out of Privacy Sandbox trials in browser settings, so
Privacy Sandbox features may not be enabled for all your users, even if the page they're viewing
provides a valid origin trial token.  
{% endAside%}  

### I registered for the origin trial of a Privacy Sandbox API, but the API isn't working on my site

See [Troubleshooting Chrome's origin trials](https://developer.chrome.com/blog/origin-trial-troubleshooting/#chrome).

### Will Privacy Sandbox origin trials work in Chromium, or in other browsers?

Chrome origin trials are designed to work for Chrome users. Don't rely on Chrome origin trial tokens
to enable trial features in other browsers, including Chromium, and other Chromium-based browsers.
For more detailed information, 
see [Troubleshooting Chrome's origin trials](https://developer.chrome.com/blog/origin-trial-troubleshooting/#chrome).
In particular, Chrome on iOS and iPadOS does not support Chrome origin trials.


## Trust Tokens

### Is tooling available for Trust Tokens?

Chrome DevTools enables trust token inspection from the Network and Application tabs: see [Getting
started with Trust Tokens](https://web.dev/trust-tokens/#summary).


## FLEDGE

### What's the difference between FLEDGE and TURTLEDOVE?

[FLEDGE](https://deploy-preview-543--dcc-private.netlify.app/docs/privacy-sandbox/fledge) is the
first experiment to be implemented in Chromium within the
[TURTLEDOVE](https://github.com/WICG/turtledove) family of proposals.  
The differences are mostly about separating the on-device role of the buyer and seller:

-  FLEDGE enables a 'trusted server' to provide access to real time data used by a worklet
   during bidding (without compromising privacy). Each interest group can have a
   `trusted_bidding_signals_url` and `trusted_bidding_signals_keys` attribute. At auction time, the
   browser communicates with the trusted server to fetch the values for those keys, and then makes
   those values available to the `generate_bid()` function.
-  The advertiser (ad buyer) can store additional metadata along with the interest group, to help
   it do better on-device bidding.  


## Attribution Reporting

### Is Attribution Reporting the same as the Event Conversion Measurement API?

Yes: [the name was changed](https://developer.chrome.com/docs/privacy-sandbox/attribution-reporting-introduction/),
as the original event-level scope expanded to cover additional measurement use cases.


## First-Party Sets

### What does 'sharded' mean in the context of First-Party Sets?

Not joined across first parties.


## Shared Storage

No FAQs yet! [Add yours in the repo](https://github.com/GoogleChrome/developer.chrome.com/blob/main/site/en/docs/privacy-sandbox/faq/index.md).


## CHIPS

No FAQs yet! [Add yours in the repo](https://github.com/GoogleChrome/developer.chrome.com/blob/main/site/en/docs/privacy-sandbox/faq/index.md).


## Storage Partitioning

No FAQs yet! [Add yours in the repo](https://github.com/GoogleChrome/developer.chrome.com/blob/main/site/en/docs/privacy-sandbox/faq/index.md).


## Fenced Frames

### What are the use cases for Fenced Frames?

The API proposes [a new form of embedded document](https://github.com/shivanigithub/fenced-frame)
that will enable new APIs to isolate themselves from their embedders, preventing cross-site
recognition.  
For ads use cases, see
[Fenced frames for Ads Design Doc](https://docs.google.com/document/d/17rtX55WkxMcfh6ipuhP4mNULIVxUApvYt4ZYXfX2x-s/edit#heading=h.jy0hectpkl95).


## Network State Partitioning

No FAQs yet! [Add yours in the repo](https://github.com/GoogleChrome/developer.chrome.com/blob/main/site/en/docs/privacy-sandbox/faq/index.md).


## WebID

### What is WebID?

The name "WebID" can be confusing! WebID is not a type of user identifier. Rather, WebID is a
proposal for a privacy-preserving approach to federated identity services (such as "Sign in with
...") where users can log into sites without sharing their personal information with the identity
service or the site. WebID is still [in incubation in the W3C](https://github.com/WICG/WebID).
