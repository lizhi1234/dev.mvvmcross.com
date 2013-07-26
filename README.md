# TODO:

Nab this: 

http://www.gregshackles.com/2012/11/returning-results-from-view-models-in-mvvmcross/


* Make the main MvvmCross readme more welcoming
* The N+1 videos are all in the ghuntley documentation repo (even if it's just a copy of the Mvvmcross.wordpress.com index)
* plus we can add links to the Evolve video, to the Xaminar, to the Azure Cloud-to-Client video, to the NDC video (when available), to the spanish intro (if available), to Gitte's TechDays talk, to Daniel's BUILD talk, etc
* The TipCalc tutorial is updated and copied into the ghuntley documentation
* We've completed the high level pages and also written a few more basic pages - e.g. one on data-binding (but I'm not sure we need that many more in order to get a basic site up and running)
* All of the empty/example pages are removed or hidden - e.g. https://github.com/ghuntley/MvvmCross-Documentation/blob/gh-pages/_posts/1970-01-01-background-tasks.markdown is too empty to be included
* The styling is improved - I like the default GitHub code styling - but not the yellow code on http://d559ko54.com/docs/
* A links page is added?
* A good home page for the docs site is added - do we need a quick intro video for this?

I don't want to plan a big docs site with lots of pages right now - let's do this agile with a small functioning site which we can then grow.

If we can get a first set of pages done, then:

* I'll move slodge/mvvmcross over to mvvmcross/mvvmcross and copy in whatever the new readme is.
* we can move ghuntley/mvvmcross-documentation into a mvvmcross/ repo too (and do whatever DNS magic is required
* we can move forwards :)

Please post here whatever anyone wants to contribute to this :)


Other pages we could bring in from @JohannesRudolph's fab work:

https://github.com/JohannesRudolph/MvvmCross/wiki/HowTo:-Perform-work-on-the-Main-Thread
the 3 binding pages from https://github.com/JohannesRudolph/MvvmCross/wiki/MvvmCross.Binding
I'd also like to include:

http://slodge.blogspot.co.uk/2013/03/the-mvvmcross-manifesto-draft-1.html


# CSS Framework

We use ZURB Foundation, to upgrade to latest release via:

	# cd $projectDirectory
	# [sudo] gem upgrade zurb-foundation
	# compass install -r zurb-foundation foundation/upgrade

See [http://foundation.zurb.com/docs/sass.html](http://foundation.zurb.com/docs/sass.html) for specifics.

# Code Highlighting
We use Pygments and the GitHub style, which can be rebuilt from source via:

	# [sudo] [easy_install|pip] pygments-style-github
	# cd $projectDirectory
	# pygmentize -S github -f html > sass/_pygments-github.scss

