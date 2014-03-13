# Installation guide for ASP.NET developers


1. [Download and unzip the package](/download) or [install the NuGet package](/docs/nuget). If you're not using ASP.NET, [read this guide](/docs/howto/use-without-asp-net).
2. In Visual Studio, right click your project and choose "Add reference". Browse to the extracted folder, and choose `dlls\release\ImageResizer.dll`. Or just copy it into the 'bin' folder. Whichever you prefer. (Compatible with .NET 2-4).
3. Modify or create the /Web.Config file for your site:
	
		<?xml version="1.0" encoding="utf-8" ?>
		<configuration>
			<configSections>
				<section name="resizer" type="ImageResizer.ResizerSection,ImageResizer"  requirePermission="false"  />
			</configSections>

			<resizer>
				<!-- Unless you (a) use Integrated mode, or (b) map all reqeusts to ASP.NET, 
						 you'll need to add .ashx to your image URLs: image.jpg.ashx?width=200&height=20 -->
				<pipeline fakeExtensions=".ashx" />

				<plugins>
					<add name="MvcRoutingShim" />
					<!-- <add name="DiskCache" /> -->
					<!-- <add name="PrettyGifs" /> -->
				</plugins>  
			</resizer>

			<system.web>
				<httpModules>
					<!-- This is for IIS5, IIS6, and IIS7 Classic, and Cassini/VS Web Server-->
					<add name="ImageResizingModule" type="ImageResizer.InterceptModule"/>
				</httpModules>
			</system.web>

			<system.webServer>
				<validation validateIntegratedModeConfiguration="false"/>
				<modules>
					<!-- This is for IIS7+ Integrated mode -->
					<add name="ImageResizingModule" type="ImageResizer.InterceptModule"/>
				</modules>
			</system.webServer>
		</configuration>
	
4. Start your web site, then visit [/resizer.debug.ashx](/plugins/diagnostics) to verify you've done everything correctly. If you ever encounter issues, simply revisit that page to access the self-diagnostics. If you need help, [just ask](/support)! ASP.NET MVC is fully supported, just install the MvcRoutingShim plugin and review the [Best Practices Guide](/docs/best-practices).

5. Relax and have fun! This software has been refined and improved since its creation in 2007, with a focus on security, stability, and performance. Unlike all the sample code you find on the internet, it avoids [the 29 common image resizing pitfalls](http://nathanaeljones.com/163/20-image-resizing-pitfalls/). Over 10K websites use the ImageResizer; why not read a few [recent testimonials from some of the more well-known people & companies?](/testimonials).

6. Spread the word! Tell your friends and co-workers about this library. And click the +1 button to tell [Google Plus](http://plus.google.com/) that this is an awesome site. Have ideas or feedback? [Share them on our UserVoice site, so others can vote up your proposals](http://resizer.uservoice.com).

7. Ready to go live? Get the [Performance Edition](/plugins/editions/performance), which includes [disk caching](/plugins/diskcache) and several other invaluable plugins. This project requires my full-time attention (and part-time help from others), so please support it by purchasing [a paid edition](/buy) or [an all-inclusive support contract](/support/contracts). 

8. Add [third-pary plugins](/docs/wrappers) and contribute your own:
	* Use [Ben Foster's Fluent API](https://github.com/benfoster/ImageResizer.FluentExtensions) instead of building query strings with the `Instructions` class
	* Want a UI for ImageResizer? [Try StudioJS](https://github.com/nathanaeljones/studiojs)
	* Responsive web design requires responsive images. [Check out the ResponsivePresets system](https://github.com/mindrevolution/ImageResizer-ResponsivePresets) from [marc303](https://github.com/marc303).

Can't afford any mistakes? Ensure your content architecture is scalable and secure by having a **30-minute Q&A session with the author for just $70**.
Or, get [a support contract](/support/contracts) that includes all of the above *and* licenses for everything. 
