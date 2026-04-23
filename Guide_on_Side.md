Students last year told me that developing for Pressbooks is much easier
than for Drupal so if the dept can provide the Pressbooks server they
would need for this project, I am now open to taking on a second set of
groups for this year. My call number harvester is my top priority
though, so I would only want this one if that one is definitely going
forward.

Here is the proposal:

Title: "Guide on the Side" Interactive Tutorial Building for Pressbooks
or Drupal 10

Summary: Pressbooks module/configuration to create a method for
librarians to create interactive tutorials where one part of the display
is giving them instructions and the other part is an actual live library
database where the users are attempting to follow those instructions in
order to learn how to use that database.

Background: The University of Arizona made exactly the functionality we
want many years ago, as a direct PHP/javascript/CSS implementation:

[<u>https://ualibraries.github.io/Guide-on-the-Side/about.html</u>](https://ualibraries.github.io/Guide-on-the-Side/about.html)

and

[<u>https://github.com/ualibraries/Guide-on-the-Side/tree/master</u>](https://github.com/ualibraries/Guide-on-the-Side/tree/master)

but they stopped supporting it a few years ago.

Since then, the only supported equivalent is a commercial product called
LibWizard from a company called SpringShare.

[<u>https://www.springshare.com/libwizard</u>](https://www.springshare.com/libwizard)

It actually does more than we want - we just want the interactive
tutorial part of that. UPEI does not subscribe to this expensive
product.

We have heard from prior groups in this course that Pressbooks would be
the best environment to develop something like this.

Our other option would be Drupal 10, but we will let the students choose
which to develop for.

MVP:

Create a tool that would allow librarians to develop as many different
interactive tutorials as they want, with text and quiz questions on the
left side, and some kind of interactive embedded page/object on the
right side, as in this example from Springshare:

<u><https://springylib.libwizard.com/f/searchcatalog></u>

more examples from Springshare:

[<u>https://buzz.springshare.com/producthighlights/libwizard-builder/playtime/tutorials</u>](https://buzz.springshare.com/producthighlights/libwizard-builder/playtime/tutorials)

more examples from a Springshare customer library:<u>  
https://libguides.brenau.edu/libwizard</u>

The "quiz" aspects regarding correct and incorrect answers do not need
to be saved or recorded anywhere outside of the interaction - this is
just self-paced learning, not an assessment tool for the instructors.

The right side will often be a website like our OneSearch database or
our own Catalogue, but it could be a directly stored video file like
this example:

[<u>https://ucmercedlibrary.libwizard.com/f/search-google</u>](https://ucmercedlibrary.libwizard.com/f/search-google)

The design should have the ability to scale the content of the web page
on the right so that it fits properly regardless of its native aspect
ratio.

There should be no limit on the number of "slides" that can be added,
just a minimum of two.

The designer interface that the librarians use to create these should be
task-relevant and as WYSIWYG as possible.

There should be a template option regarding CSS aspects (fonts, colors,
etc.) that the library can create to encourage librarians to design
their tutorials with a single "look and feel" but librarians can choose
to override those on a slide-by-slide/page-by-page basis.

Students will agree to release all of this work in an MIT open source
license.

Student teams can choose either Drupal 10 or Pressbooks as the content
management system they design the project for, subject to the dept
providing an appropriate development server space for that CMS.

Stretch goals:

1.  Make it possible for students to produce an "official" report of
    > their performance/successful completion, as a PDF (eg a
    > certificate design) to turn into a professor who wants to assign
    > the completion as homework to be counted towards their course
    > grade.

You can see an example of what UPEI instructors have found acceptable by
looking at what the Academic Integrity module in Moodle provides:
[<u>https://moodle31.upei.ca/course/view.php?id=444</u>](https://moodle31.upei.ca/course/view.php?id=444)

2.  Offer the ability to the tutorial designer/librarian to create a
    > branch sub-tutorial that would only be available if the student
    > gets a particular question wrong. Each question could have its own
    > sub-tutorial content. The navigation design should be clear
    > regarding what is happening and what the student needs to do to
    > get back to the main tutorial. The librarian should have the
    > option whether to make the sub-tutorial mandatory or optional to
    > complete before the user returns to the main tutorial, on a
    > question by question basis. The official report (stretch goal 1)
    > would not need to include the performance on the sub-tutorials.

3\. Give the librarians the ability to copy individual slides from one
guide to another. They should be copies, not links so the copy can be
modified in the new guide. It should include both frames's content
definitions.

4\. Give the librarians the ability to copy an entire guide into some
kind of package that can then be added on a different server. For
instance, if both UPEI and Dalhousie are using your program, the UPEI
librarian should be able to "download" their entire guide and send it to
a Dalhousie librarian who can upload it into their own Guide server.

5\. a. Allow the librarian to set the horizontal ratio between the left
"slides" and the right "interactive content/video" areas of the layout.
Ok, to create a reasonable range that their choice must be within, for
instance, it must be a minimum of 10% left/slide to 90% right/content
but the librarian would be allowed to change that up to a maximum of 50%
on the left (and therefore 50% on the right). Set a default value for
new guides so the librarian doesn't have to set this for every new guide
and have that default be configurable by the admins who actually install
it.

5 .b. Provide an option per guide (the librarian can choose to set it or
not for the entire guide) that would allow the patron/user to adjust the
proportion of the width that is on the left side versus the right side.
For instance, if the default layout set by the librarian (this assumes
5a) is 30% on the left where the slides/questions are, and 70% on the
right where the interactive content/videos are, the librarian should be
able to turn on an option so the individual user can grab the dividing
line/bar to change it to 50-50 or whatever the min and max are for the
entire project as per 5a. The user should be able to change it back and
forth at any time (throughout the tutorial) if the librarian turned on
this option.

6\. Make it possible for the librarian to embed on the right side a
Google Doc (that is a live interactive view of an actual Doc somewhere),
Google Sheet (spreadsheet), Google Slides (presentation). For Microsoft
equivalents (Word, Excel, PowerPoint) allow for any of these as a direct
embedded file (that is actually on the Guide server) or a live link to
any of those like the Google versions on an MS365 OneDrive space. The
librarian has to make sure the sharing settings are correct for the ones
that are links to a Google/MS365 account's storage.

7\. For any content on the right that changes with clicks (eg a website
or multi-page PDF) or running time (eg video), allow the librarian to
define subunits and annotate them with a few basic "callout" features -
either a colored arrow (librarian chooses the fill color) or
balloon-type callout box with text in it.

7.a. Videos: For instance, if there's a video that's 30 seconds long,
the librarian should be able to set a particular callout box/arrow that
appears in a specific spot from playing time 00:00 until 00:10 seconds
then disappears then they can add a different one from 00:10 seconds to
00:15 etc until the end of the video. Every time the user replays the
video, stops and scrubs through it, etc., these would re-appear,
synchronized to each second as defined by the librarian.

7.b. websites - the librarian should be able to define when these
callout widgets appear based on the URL at that moment. For instance, if
the activity is searching the library catalog, the librarian might want
to put a callout on the search screen, then when the user clicks to run
the search, a new callout appears on the result screen, etc. This would
only work if each step of the website has persistent/predictable URLs,
so the librarian would be matching the widget's appearance to specific
URLs rather than timing like the video. Allow the librarian to define
the persistent URLs with a wildcard or placeholder, for instance,
whenever the URL matches a pattern, the callout for that pattern would
be displayed. For example this is what a URL for UPEI's library catalog
looks like after a search is run:
https://islandpines.roblib.upei.ca/eg/opac/results?query=asme&qtype=keyword&fi%3Asearch_format=  
where the user chose to search "asme" so the librarian could substitute
a placeholder there:

https://islandpines.roblib.upei.ca/eg/opac/results?query=**{search}**&qtype=keyword&fi%3Asearch_format=

or
https://islandpines.roblib.upei.ca/eg/opac/results?query=**^^^**&qtype=keyword&fi%3Asearch_format=

I leave it to you to figure out what placeholder/wildcard string would
seem to be least likely to be part of a normal URL. I've seen {keyword}
syntax in lots of professional librarian search systems so that's
probably a good choice, but you may come up with a better idea.

7.c. static documents like a multi-page PDF that is directly linked via
a URL or is locally stored in the guide- the librarian could specify
callouts page by page

7.d figure out how to implement this callout idea for any or all of the
linked document types from goal 6, where the URLs are probably NOT
persistent, and figure out how to define the condition for which you
detect when the user took an action that is used to define the
synchronization for the callout's appearance and disappearance. In the
case of Google Sheets, when the user changes "tabs" (aka worksheets
within the entire spreadsheet) the URL does change predictably, and it
does when they change slides in a presentation, but when the user
scrolls down a single multi-page document it doesn't, and I'm not sure
what happens in the Microsoft types, either locally uploaded files or
links to MS365 docs in the cloud.

8\. Allow librarian to offer multiple "correct" answers to a text-answer
question, eg 20 or twenty.
