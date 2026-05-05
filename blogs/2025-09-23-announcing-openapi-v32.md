---
title: "Announcing OpenAPI v3.2"
url: "https://www.openapis.org/blog/2025/09/23/announcing-openapi-v3-2"
date: "Tue, 23 Sep 2025 07:00:43 +0000"
author: "Chris Wood"
feed_url: "https://www.openapis.org/feed"
---
<p>We are delighted and proud to announce the release of v3.2.0 of the OpenAPI Specification!</p>
<p>Our latest minor version brings a host of new features across a number of areas including supported HTTP methods, a new tag structure, support for streaming media types, and a whole lot more!</p>
<p>Here’s a quick rundown of the headline features.</p>
<h3 id="multipurpose-tags-with-nesting">Multipurpose Tags with Nesting</h3>
<p>One of the most significant changes, particularly for rendering a graphical view of an OpenAPI description, is the change to the <a href="https://spec.openapis.org/oas/v3.2.0.html#tag-object">Tags</a> object. The new Tag Object structure introduces <span style="font-family: monospace; font-weight: bold;">summary</span> for short descriptions, <span style="font-family: monospace; font-weight: bold;">parent</span> for nesting, and <span style="font-family: monospace; font-weight: bold;">kind</span> for classifying Tags, allow a taxonomy to be developed, supported by a <a href="https://spec.openapis.org/registry/tag-kind/index.html">registry</a> of commonly supported values.</p>
<p><span style="font-family: monospace; font-weight: bold;">kind</span> is useful because it allows tooling to selectively include and ignore Tags when parsing an OpenAPI description, as shown in the example below.</p>
<p>
<span style="font-family: monospace; font-weight: bold;">tags:</span><br />
&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;"># Only used for rendering</span></p>
<p>&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;">&#8211; name: products</span><br />
&nbsp;&nbsp;&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;">summary: Products</span><br />
&nbsp;&nbsp;&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;">description: All product operations</span><br />
&nbsp;&nbsp;&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;">kind: nav</span></p>
<p>&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;">&#8211; name: books</span><br />
&nbsp;&nbsp;&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;">summary: Books &amp; Literature</span><br />
&nbsp;&nbsp;&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;">description: Book catalog and recommendations</span><br />
&nbsp;&nbsp;&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;">parent: products</span><br />
&nbsp;&nbsp;&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;">kind: nav</span></p>
<p>&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;"># Used for grouping Badge related operations in generated code</span></p>
<p>&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;">&#8211; name: digital-delivery</span><br />
&nbsp;&nbsp;&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;">summary: Digital Delivery</span><br />
&nbsp;&nbsp;&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;">description: Instantly delivered digital products</span><br />
&nbsp;&nbsp;&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;">kind: badge</span>
</p>
<p>Tags can therefore be created for different purposes, making the structure of the Tag Object much more flexible.</p>
<p>As you migrate to v3.2.0, be sure to contribute to the Kind registry to share useful Tags across the community!</p>
<h3 id="http-method-changes">HTTP Method Changes</h3>
<p>v3.2.0 also includes a number of new features for more advanced HTTP method support.</p>
<p>Firstly, the new version offers built-in support for the <span style="font-family: monospace; font-weight: bold;">query</span> HTTP method. <span style="font-family: monospace; font-weight: bold;">query</span> provides support for safely querying the state of a resource in an idempotent way using a <strong>query payload</strong>. You can therefore define more complex query terms in your OpenAPI descriptions, with support from Schema Objects, with a separation from <span style="font-family: monospace; font-weight: bold;">post</span> methods that you might have used in the past for such operations.</p>
<p>Support for other HTTP methods that are not first-class citizens in OpenAPI is now provided by the <span style="font-family: monospace; font-weight: bold;">additionalOperations</span>. You can define a Map of HTTP methods you choose to include in your API design, and that can be processed by tooling, that are implemented as standard Operation Objects:</p>
<p>
<span style="font-family: monospace; font-weight: bold;">paths:</span><br />
&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;">/:</span><br />
&nbsp;&nbsp;&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;">additionalOperations:</span><br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;">connect:</span><br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;">operationId:</span><br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="font-family: monospace; font-weight: bold;">## A standard Operation Object</span>
</p>
<p>The other major enhancement is the introduction of <span style="font-family: monospace; font-weight: bold;">querystring</span>, which provides the means to define all query parameters as a Schema Object, allowing for greater control in defining how query parameters are defined and coexist in a given API operation.</p>
<h3 id="sequential-and-streaming-data">Sequential and Streaming Data</h3>
<p>A welcome addition in this version of OpenAPI is increased support for streaming data, which is a critical enhancement to support creating well-described APIs across so many use cases, including chat, AI, IoT, and financial services.</p>
<p>OpenAPI now supports the following types:</p>
<ul>
<li><strong>Server-Sent Events</strong>: <span style="font-family: monospace; font-weight: bold;">text/event-stream</span></li>
<li><strong>JSON Lines</strong>: <span style="font-family: monospace; font-weight: bold;">application/jsonl</span></li>
<li><strong>JSON Sequences</strong>: <span style="font-family: monospace; font-weight: bold;">application/json-seq</span></li>
<li><strong>Multipart Mixed</strong>: <span style="font-family: monospace; font-weight: bold;">multipart/mixed</span></li>
</ul>
<p>These types work in tandem with the <span style="font-family: monospace; font-weight: bold;">itemSchema</span> keyword, which defines what a streamed event looks like over the wire. The addition of this support is a significant enhancement for both understanding streaming APIs <strong>and</strong> for tooling makers who typically need to ingest many different data structures, represented by many Schema Objects, through a single Operation.</p>
<h3 id="new-security-features">New Security Features</h3>
<p>There are also a number of new features in Security.</p>
<p>v3.2.0 introduces support for OAuth 2.0 Device Authorization Flow. <a href="https://datatracker.ietf.org/doc/html/rfc8628">Device Authorization Flow</a> is an OAuth profile that supports End User authorization on limited input devices &#8211; think smart TVs and kiosks &#8211; and therefore requires a specialized flow to cater for handoff to an input device. Given the proliferation of such limited input devices providing support for Device Authorization Flow is a real boost for API Providers bringing their APIs to broadcasting platforms.</p>
<p>The core OAuth Flow object has also been enhanced to include the <span style="font-family: monospace; font-weight: bold;">oauth2MetadataUrl</span> property, which defines a URL at which <a href="https://datatracker.ietf.org/doc/html/rfc8414">OAuth 2.0 Server Metadata</a> can be retrieved, supporting OAuth flows. Providing links to metadata, in the same way as the OpenID property <span style="font-family: monospace; font-weight: bold;">openIdConnectUrl</span> allows an OpenAPI description to be a key reference point for API Consumers, providing both functional and security information. Such reference points are particularly important in sectors like open finance, which rely heavily on publishing OAuth and OpenID Connect metadata for automatic discovery of services.</p>
<h3 id="other-features">Other Features</h3>
<p>We’ve only covered some headline changes here, in an effort to bring together the most impactful changes in this release.</p>
<p>For more details please review:</p>
<ul>
<li>The Specification <a href="https://spec.openapis.org/oas/v3.2.0.html">page</a> for v3.2.0.</li>
<li>The <a href="https://github.com/OAI/OpenAPI-Specification/releases/tag/3.2.0">Release Notes</a> on GitHub, which provides a headline list of all changes.</li>
<li>Our Learn site, where you’ll find a <a href="https://learn.openapis.org/upgrading/v3.1-to-v3.2.html">migration guide</a>.</li>
</ul>
<p>As ever, our thanks and appreciation go to our great community members who worked so hard to bring this version together! Special thanks go to <a href="https://github.com/handrews">Henry Andrews</a> and <a href="https://www.linkedin.com/in/lornajane/">Lorna Mitchell</a> for their significant contributions to this effort!</p>
<p>Contributors: <a href="https://www.linkedin.com/in/lornajane/">Lorna Mitchell</a>, <a href="https://www.linkedin.com/in/sensiblewood/">Chris Wood</a></p>
