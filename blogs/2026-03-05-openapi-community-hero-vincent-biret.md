---
title: "OpenAPI Community Hero – Vincent Biret"
url: "https://www.openapis.org/blog/2026/03/05/openapi-community-hero-vincent-biret"
date: "Thu, 05 Mar 2026 16:42:27 +0000"
author: "Chris Wood"
feed_url: "https://www.openapis.org/feed"
---
<div class="wpb_row vc_row-fluid vc_row top-level" id="fws_69ef910d8e49c" style="padding-top: 0px; padding-bottom: 0px;"><div class="row-bg-wrap"><div class="inner-wrap row-bg-layer"><div class="row-bg viewport-desktop"></div></div></div><div class="row_col_wrap_12 col span_12 dark left">
	<div class="vc_col-sm-12 wpb_column column_container vc_column_container col no-extra-padding inherit_tablet inherit_phone flex_gap_desktop_10px ">
		<div class="vc_column-inner">
			<div class="wpb_wrapper">
				<div class="wpb_row vc_row-fluid vc_row inner_row" id="fws_69ef910d92efa"><div class="row-bg-wrap"> <div class="row-bg"></div> </div><div class="row_col_wrap_12_inner col span_12  left">
	<div class="vc_col-sm-6 wpb_column column_container vc_column_container col child_column no-extra-padding inherit_tablet inherit_phone ">
		<div class="vc_column-inner">
		<div class="wpb_wrapper">
			
<div class="wpb_text_column wpb_content_element ">
	<p><em>Welcome to our next Community Hero! After his recent efforts in contributing to Overlay v1.1.0, we spoke to Vincent Biret.</em></p>
<p><em>Vincent is a Principal Software Developer at Microsoft AI Foundry, and previously worked on Microsoft Graph. He is a long time open source contributor, international public speaker, and is passionate about developer experience.</em></p>
<p><em>Vincent gave us his thoughts on the Overlay, the Open Initiative specifications in general, and why being involved in contributing to the specifications is so valuable.</em></p>
</div>




		</div> 
	</div>
	</div> 

	<div class="vc_col-sm-6 wpb_column column_container vc_column_container col child_column no-extra-padding inherit_tablet inherit_phone flex_gap_desktop_10px ">
		<div class="vc_column-inner">
		<div class="wpb_wrapper">
			<div class="img-with-aniamtion-wrap center mask_shape_circle mask_size_contain ">
      <div class="inner">
        <div class="hover-wrap"> 
          <div class="hover-wrap-inner">
            <img alt="" class="img-with-animation skip-lazy" height="512" src="https://www.openapis.org/wp-content/uploads/sites/31/2026/03/2026-03-03-community-hero-vincent-biret-01.jpg" width="512" />
          </div>
        </div>
        
      </div>
    </div>
		</div> 
	</div>
	</div> 
</div></div>
<div class="wpb_text_column wpb_content_element ">
	<h3 id="what-drives-your-interest-and-involvement-in-the-openapi-specification">What drives your interest and involvement in the OpenAPI Specification?</h3>
<p>Participation in the OpenAPI initiative is a growing opportunity. It also enables so much of the work I do at Microsoft. And I’m a long believer of the “contribute back to the things you’re using” model.</p>
<p>About 5 years ago, I started to work on a client code generator, Kiota, which meant I needed to learn a lot about the OpenAPI Specification. The TDC felt like a “natural place” for me to learn was to sit (at first quietly). This call felt welcoming and taught me a lot about “how standards work, and who are the people behind it”. I gradually felt comfortable contributing back.</p>
<p>Thanks to the help of many others, some of them featured in this blog series, I’ve been able to make meaningful contributions to OpenAPI 3.2.0, and lately to Overlays as well.</p>
<h3 id="the-openapi-initiative-is-now-a-multi-specification-organisation.-how-do-you-see-the-project-changing-now-that-we-deliver-more-specifications-to-the-api-community">The OpenAPI Initiative is now a multi-specification organisation. How do you see the project changing now that we deliver more specifications to the API community?</h3>
<p>Before getting involved in the OpenAPI initiative, I didn’t suspect how much work and coordination goes into standards authoring. The bigger the standard, the more work required to put together a new version. And that growth is not linear.</p>
<p>The size of the standard also impacts the “consumer” side, implementers need to keep more context in mind, users require more effort to discover any given feature, etc…</p>
<p>There is a general recognition among the regular contributors that we can move faster with a set of “dedicated and interconnected specifications” rather than a monolithic one. This structure unlocks additional value for consumers through better focus and clarity, faster releases with more features, easiness to implement, etc…</p>
<p>A clear demonstration of this approach works:</p>
<p>About 2 years ago, the main repository had about 1000 open issues, this was not manageable. Now we’re at about 100. Thanks to the hard work of <a href="https://www.linkedin.com/in/lornajane/">Lorna</a>, <a href="https://github.com/handrews">Henry</a> and others, some of those issues were “grouped by problem areas” into Arazzo or Overlays. Those issues were then handled by dedicated teams. This approach facilitated the 3.2.0 release of the core specification through better focus on the core concerns.</p>
<h3 id="you-recently-contributed-to-v1.1.0-of-overlay.-what-was-your-motivation-for-implementing-the-new-features-you-provided-to-the-community">You recently contributed to v1.1.0 of Overlay. What was your motivation for implementing the new features you provided to the community</h3>
<p>I now work on Microsoft AI Foundry, which provides a superset of the REST API provided by OpenAI. To enable those experiences, we use TypeSpec as a design language and as a support for a lot of our tooling.</p>
<p>In that context, we need TypeSpec definitions for the OpenAI surface of the API but we don’t want to handcraft them. After all, we’re talking about approximately 300 operations, hundreds of models, all of which change weekly.</p>
<p>In our import process, we use Overlays to massage the OpenAPI description OpenAI provides into something that better fits our needs. At some point we found ourselves maintaining a lot of “update actions” that contained duplicated sections from the source description. Those duplicated sections quickly became stale and unmanageable.</p>
<p>After scanning through the Overlays repository, I quickly noticed this was a common limitation others were sharing. So not only to enable a better workflow for my team, but also to give back to the community, I thought I’d propose a solution to that problem. And thanks to the help of many others, like <a href="https://www.linkedin.com/in/ralfhandl/">Ralf Handl</a> and <a href="https://www.linkedin.com/in/michael-kistler/">Mike Kistler</a>, we finalized the feature!</p>
<p>This feature, and additional contributions from many others eventually became version 1.1.0 for everyone to enjoy.</p>
<h3 id="the-moonwalk-sig-continues-to-look-to-the-future-of-openapi-and-investigate-new-features-that-could-be-of-value-to-our-specifications.-what-are-you-most-excited-about-as-a-future-feature-of-any-of-the-specifications">The Moonwalk SIG continues to look to the future of OpenAPI, and investigate new features that could be of value to our specifications. What are you most excited about as a future feature of any of the specifications?</h3>
<p>Although I’m not involved in the Moonwalk SIG (there are only so many hours in a day), we have a great model here: Moonwalk is the “think tank” for large, fundamental and long-term concerns that are not addressed today in the specification. Where possible, some of that thinking gets ported in a 3.X version.</p>
<p>This approach has many benefits:</p>
<ul>
<li>The community gets value sooner than waiting for a big-bang release for years.</li>
<li>The specification authors get feedback on any solution, leading to a more mature iteration in the “big release”.</li>
</ul>
<p>Beyond this process that feeds features into the minor releases, I’m excited about a few foundational breaking changes that are needed to enable additional scenarios:</p>
<ul>
<li>The notion of “parameters groups/sets”: today you can’t really express “if you provide query parameters X/Y/Z, you’ll get response alpha, but if you provide A/B/C, you’ll get beta”. (especially useful when the API provides the ability to select fields from the response).</li>
<li>Better integration with RFC6570 URI template. This will simplify the specification a great deal, and enable a more structured approach to code generation, etc… This will also solve once and for all ambiguities around whether paths might be conflicting or not based on their path parameters/constants.</li>
<li>Maybe new things around how authentication and authorization can be discovered by agents/code-generators to enable better automation? This has been an historical gap of the specification.</li>
<li>Maybe support for additional protocols? (we’re started some work with webhooks, and in 3.2.0 streaming)</li>
<li>Maybe better lifecycle information? (read and write only are “left to interpretation” today)</li>
</ul>
<p>(this is just my wishlist, I don’t actually know whether the SIG is working on any of those things)</p>
<h3 id="what-do-you-see-in-the-future-for-the-openapi-specification">What do you see in the future for the OpenAPI Specification?</h3>
<p>Keep in mind that I’ve only been involved (as in more than just using) in the specification about 3 or 4 years ago, so I might not have sufficient perspective here to provide an accurate answer.</p>
<p>But from my perspective, it seems to me the OpenAPI Specification is both charting the course in the API space, and also closely listening to where the broader IT industry is going.</p>
<p>Right now, the industry has a HUGE focus on the LLM/AI/agentic space. And OpenAPI fits well in that space because it’s text based, broadly adopted, mechanically parsable, etc… So I think we’re going to see that at least some of the investments will cater to that problem space.</p>
<p>Longer term, I think I can see two challenges arise:</p>
<p>This is a lot of work done by people. We need to ensure this work remains sustainable by supporting the people working (funding etc…). Especially contributors who are not on the payroll of big corporations like I’m fortunate to be. All the great additional features in newer versions are only beneficial if end users are aware of them, and if tooling supports it. We probably have a lot of work on the advocacy side.</p>
<h3 id="what-other-standards-developments-do-you-consider-particularly-significant-for-the-api-economy">What other standards developments do you consider particularly significant for the API economy?</h3>
<p>I’d like to acknowledge we rest (pun intended) on the shoulders of giants: HTTP, TLS, TCP/IP, DNS,etc… All of that is infrastructure, and like any infrastructure it requires ongoing investments to operate safely and at peak efficiency.</p>
<p>Additionally, we’re seeing co-benefits from adopting existing standards as much as possible in the API space: JSON Schema, RFC 6570 Uri template, RFC 9535 JSONPath query expressions for JSON, and many more. Re-using existing standards allows us to focus on the additional value we can provide, while unlocking efficiencies from integrating with existing eco-systems.</p>
<p>I’m also keeping an eye on emerging standards from the AI space: MCP, A2A, UTCP…</p>
<h3 id="why-should-more-people-like-yourself-get-involved-in-developing-the-openapi-initiative-specifications">Why should more people like yourself get involved in developing the OpenAPI Initiative specifications?</h3>
<p>It’s a tremendous learning opportunity, the community is super nice, there’s work to do, and giving back (your time, money, etc…) is generally speaking a nice thing to do. It can seem like a scary new space, but with time and dedication you’ll get used to it.</p>
<p>I also especially encourage people who are not like me to join, because having too many “individuals like me” would be a disaster <img alt="😉" class="wp-smiley" src="https://s.w.org/images/core/emoji/17.0.2/72x72/1f609.png" style="height: 1em;" />.</p>
<p>Author: <a href="https://www.linkedin.com/in/vincentbiret/">Vincent Biret</a></p>
</div>




			</div> 
		</div>
	</div> 

	<div class="vc_col-sm-12 wpb_column column_container vc_column_container col no-extra-padding inherit_tablet inherit_phone flex_gap_desktop_10px ">
		<div class="vc_column-inner">
			<div class="wpb_wrapper">
				
			</div> 
		</div>
	</div> 
</div></div>
