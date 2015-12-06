---
title: The Perfect GIF Workflow Using Alfred and Dropbox
date: 2013-07-20 05:50:00 -04:00
color: 6b269b
blocks:
- figure:
    image: "/uploads/blog/gif-workflow/hero.jpg"
- body: Like many internet dwellers, I prefer to use [GIFs](http://en.wikipedia.org/wiki/Graphics_Interchange_Format)
    as a form of response rather than words. Why *say* you’re angry when you can [show
    it](http://dl.dropboxusercontent.com/u/121678/gifs/wwf-wrestling-girl-mad.gif).
    On Twitter, I’m [quick](https://twitter.com/garbnzgh/status/340135598700498944)
    to respond with a GIF, which catches most people off guard—they wonder how I found
    an appropriate GIF so fast. Some [assume](https://twitter.com/dezinezync/status/345745470959792128)
    I already have the URL copied to my clipboard, and this is partly true, but how
    did it get there? In this post, I’ll walk through my GIF workflow, detailing how
    I combine Dropbox and Alfred to optimize my TTGIF, or *time to GIF*.
- header: Dropbox
  body: "[Dropbox](http://db.tt/sUwztpQ) is an essential tool for storing and linking
    GIFs. Sure, it can be used to backup important files or seamlessly share folders
    between computers, but I pay for the GIF-specific features—the most important
    of these being predictable URLs for files within your public folder."
- figure:
    image: "/uploads/blog/gif-workflow/dock.jpg"
  wide?: true
- body: In my public Dropbox folder, I have a folder named, “gifs.” For ease of accessibility,
    I keep this folder in my dock, with the contents displayed as a grid. If I stumble
    across a GIF I want to save, I simply drag it to this folder and it is added to
    the collection. In the background, Dropbox syncs the GIF to my online storage
    and within seconds, it’s available for use.
- figure:
    image: "/uploads/blog/gif-workflow/dock-stack.png"
- body: Clicking the folder opens a temporary window with rows upon rows of GIF thumbnails.
    Here, I can browse through my collection and find the perfect GIF for the occasion.
    I keep the folder sorted by “Date Added,” so I have a general memory of where
    each GIF is located. And because the files are local, I don’t need to wait for
    the GIFs to load.
- figure:
    image: "/uploads/blog/gif-workflow/stack-preview.jpg"
- body: |-
    For times when I need more than just a thumbnail, I can preview a GIF using “Quick Look” by pressing the spacebar while hovering its thumbnail. This spawns a popup window that loops through the hovered GIF. Unfortunately, GIFs on OS X play at a slower framerate locally than on the web, so be sure to preview in the browser prior to responding.

    At this point, I *could* right-click one of the files, select “Copy Public Link,” and have a URL ready to paste—but why stop there? We can easily shave off a few clicks and greatly improve search with the help of my friend, Alfred.
- header: Alfred
  body: "[Alfred](http://www.alfredapp.com/) is undoubtedly the best productivity
    app out there. For years, it has been my go-to app launcher, but recently, I’ve
    taken advantage of Alfred’s true power by writing several custom extensions. Each
    refines one of my daily workflows by automating a given task."
- figure:
    image: "/uploads/blog/gif-workflow/alfred-workflow.jpg"
- body: In the latest version of Alfred, you can wire several actions together into
    a chain, called a “Workflow.” With these workflows, you can write all sorts of
    complex scripts and trigger them with a single key command. For my [GIF workflow](/uploads/blog/gif-workflow/gif-filter.zip),
    I only use two actions—file filter and bash script.
- figure:
    image: "/uploads/blog/gif-workflow/alfred-filter.jpg"
- body: In the file filter settings, I use the keyword, “gif,” so whenever I type
    “gif” into Alfred, it triggers this filter. Alfred will search for files that
    include any text that comes after “gif.” This is too broad when used system-wide,
    but I can add a scope to restrict Alfred to a specific folder.
- figure:
    image: "/uploads/blog/gif-workflow/alfred-search-scope.jpg"
- body: In the “Search Scope” tab, I use the “gif” folder from my public Dropbox folder
    as a whitelisted path. Now, Alfred will search only this folder when we use the
    “gif” keyword.
- figure:
    image: "/uploads/blog/gif-workflow/alfred-code.jpg"
- body: The second action in this workflow is a bash script. The script first takes
    the filename from the selected file in our filter and appends it to the public
    Dropbox base URL. Then, it runs `pbcopy` on the URL to copy it to the clipboard.
- figure:
    image: "/uploads/blog/gif-workflow/alfred-search.jpg"
- body: Since Alfred searches filenames, I manually set each GIF’s filename with several
    descriptive keywords. Because I’m the one writing each keyword, it’s much easier
    to recall a relevant search term for any GIF in my collection. Now I can start
    to type “troll,” select the classic GIF of Duck Hunt’s laughing dog, and paste
    it in a tweet.
- header: Wrapping up
  body: So that’s it. With Dropbox and Alfred, I can copy a GIF’s URL to my clipboard
    in seconds and respond like a pro. Think you have a better workflow? If so, I’d
    love to [hear](http://twitter.com/destroytoday) about it.
---

