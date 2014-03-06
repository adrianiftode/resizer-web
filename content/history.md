# History of ImageResizer

The ImageResizer was created in January 2007 to simplify the process of changing website layouts and slideshow sizes. Resizing images manually was taking hours each day, so I decided to fix the problem.

ImageResizer was designed with security, stability, and performance in mind from day 1. It was never a hack. It has always used proper memory (and resource) management techniques, and has leveraged disk caching to provide ideal scalability. Compatibility with XP through Windows 8 (and Server 2000 through Server 8) has always been maintained.

It has always been source-included, although I charged a 'download fee' for V1 and V2, which was the best way I could think of to fund development without restricting developer rights. I've also always had a no-questions-asked refund policy... which only 1 person (of 400+ V2 users) ever took advantage of - and only because their project was cancelled. No V3 user has requested a refund yet.

I've always supported the product 100%, and I (believe) I have resolved every issue every user has sent me. Once I spent an entire week helping a user debug their application since they (incorrectly) suspected the ImageResizer of causing a memory leak. This issue ended up being caused by a different component.

I'm pretty sure this is better support than you can get anywhere else.

# Release History 

Version 1 was released to the public August 6, 2008 after 1.5 years of testing on several high-traffic sites.

Version 2 was a complete rewrite, and was released to users of v1 in January 2009, and was published in May 2009. 

V2 introduced IIS7 support (HttpModule instead of HttpHandler design), nice managed API, and support for Octree GIF quantization and lots of other stuff. See [the V2 changelog if you want details](/docs/v2/changelog).

V2 was used by hundreds of developers, integrated into roughly a dozen content management systems, and used by a couple of hosting companies.

After two years of improving V2, I realized that another rewrite was needed. I decided to maintain full compatibility with the V2 URL syntax, but the managed API needed an overhaul.

The goal of the v3 rewrite was to make everything open and extendable. V2 was a monolithic design that, while elegant and very concise, was hard to extend except through source code modification. V3 introduced the concept of Plugins and added an array of Events that can be used to customize the behavior of the pipeline.
It also introduced a dedicated configuration section for the Resizer and its plugins.

V3 was released [Apr. 24](/releases/3-alpha-2) after 4 months of coding and testing. [Alpha 7](/releases/3-alpha-7) was released May 26, and I back-ported many bug fixes to V2 with the [May 27, 2011 release of 2.8](/releases/2-8). A collection of pages on the V2 to V3 differences is [available here](/docs/2to3/).

The V3 core is under [an MIT-like license](/licenses/freedom). This license is much clearer than the V2 license (something I had lots of complaints and confusion about). 

Some V3 plugins are under a [slightly more restrictive license](/licenses), but even those give you redistribution and sub-licensing rights. If your project needs a different license, [contact me](/support). I'm flexible about licensing, and I can probably get you what you need.

# Imazen

When [Support Contracts](/support/contracts) were introduced on May 1st 2012, I knew that if the offering reached the quota, I would have to open a separate bank account to ensure the contract funds were used evenly over time. Imazen LLC was formed on May 18th, and is now the official business entity behind ImageResizer and all related support contracts, offerings, and products, as well as [WindowsGit](http://windowsgit.com). By separating the finances I will be able to track income and expenses more carefully and avoid any surprises. 

I also am now hiring a significant number of part-time contract workers to help with the workload, and I am eventually looking to add a full-time employee. 

# Interesting statistics

* From Feb 2011 to December 2011, 889 commits were made to the project, an average of 3 per day. Each commit contains between 1 and 5 improvements to the project.
* In 2011, 70% of support e-mails were answered in under 1 hour. Please note that roughly 30% of support e-mails arrive between 12am and 7am in my timezone. 
* Between June and December 2011, 24 nuget packages for the ImageResizer were published. Nearly all plugins are nuget compatible. 
* The ImageResizer handles image processing for (several) photo album sites each containing 10-20TB of images.
* Has been integrated into nearly every popular ASP.NET CMS with a CMS-specific plugin, yet doesn't actually need a CMS-specific plugin to be compatible with any of the CMSes..
* Over 650 support questions were answered between August and December 2011
