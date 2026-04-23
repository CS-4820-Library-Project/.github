There are three major components for you to design/code into the Drupal
module: the admin config tools, the librarian content creation/editing
tools, and the rendering of the content for public view

Everything should draw from existing Drupal modules as much as possible,
including the default "theme" of the site, the layout options available
(e.g. columns, block layout options), modules that provide HTML editing
and file uploading/linking, available content types for embedding,
taxonomies for creating pick-lists, existing views for embedding, etc.
The Drupal concept of "views" may also be very useful especially for
building the patron (anonymous user) view and filter functionality.

Note that this should NOT be specifically written for the particular
modules that Robertson Library's site uses, but should be written more
generally for any Drupal 10 site. For instance, if another site using
this module installs it but uses TinyMCE instead of CKEditor, your
module should not try to look for CKEditor but just use the site's
default editor. Ditto for file uploader, media embedding, and whatever
content types are available.

Admin tools (module installation):

- Define fixed list of guide types and allow site install to re-label
  > any of these categories (eg "general purpose" might be relabeled
  > "How-To") - use a taxonomy (vocabulary)

- Define fixed list of subjects - use taxonomy (vocabulary)

- Define fixed list of groups - use another taxonomy (vocabulary)

- Define base path within the server, eg library.upei.ca/guides/\*

- Create/edit set of librarian profile boxes (Drupal content type:
  > blocks)

- Define proxy prefix for proxied links in content items (see boxes) -
  > stretch goal

Permissions: tell Drupal to offer Create/Edit/Delete/ guides, pages, and
boxes - and break down Edit and Delete to "own" and "any" - this
wouldn't be within the rest of the admin tools above, but be part of the
Drupal integration

Librarian Creation/Editing:

Needs to have published/unpublished status for the librarian to
"release" when it's done, at the guide, page, and box levels (Drupal
already has concept of unpublished "nodes" to leverage for this)

Types of guides:

- General purpose

- Subject

- Topic

- Course

These types are just categories for presenting the types in groups to
the patrons and for patrons to search by type - there are no differences
in terms of the creation/content editing template/process.

Options at start of librarian content process:

- Create a new guide

- Edit an existing guide

- Copy then edit an existing guide

Layout template

- always side navigation, not tabs option - probably best to implement
  > as Drupal content type "blocks"

- Allow two layers of depth

- allow just one column of boxes

Hierarchy - see
[<u>https://www.youtube.com/watch?v=JJErl2d_Thk</u>](https://www.youtube.com/watch?v=JJErl2d_Thk)

Fields in a new guide:

- Guide name:

- Guide description:

- Guide type:

- Group assignment

- Subjects: \[allow select multiple\]

- Librarian profile to display on all pages

- URL Alias - this is a Drupal built-in concept

- Author: should pick up from who in Drupal is creating it

- Libguide features we don't need: layout template, password, share

Then:

- Create page - see libguides example:
  > [<u>https://www.youtube.com/watch?v=heXTS4dcto4</u>](https://www.youtube.com/watch?v=heXTS4dcto4)

  - Allow copy existing page from any other guide or link to an existing
    > page

  - Fields - page type, name, description, position, draft mode
    > (checkbox)

  - Display at the bottom in tiny gray print the last updated date

  - Page level - top or subpage of another page - just two layers deep -
    > Guide main, page, subpage

  - Boxes -
    > [<u>https://www.youtube.com/watch?v=6p23nRpL6-o</u>](https://www.youtube.com/watch?v=6p23nRpL6-o)

    - these might act the same as "blocks" in Drupal - consider using
      > those

    - create or reuse existing

    - name, position (above/below other boxes on this page, edit should
      > allow reorder - could use blocks which come with positioning)

    - add content items:

      - HTML text - normal basic nodes

      - database - content type "database" - let librarian scroll
        > through options to select from

      - link - new content type - let librarian scroll through options
        > to select from or create one on the fly that gets added as a
        > new link "node" for other re-use

        - link name/title, URL, window target (same or blank,
          > default=blank), description to display beneath link,
          > hovertext for over the title/link, proxied (yes/no), include
          > image (use IMCE to pick/upload/link, control size, location
          > to left/right/below link), hidden field - type: article,
          > website (make this another taxonomy?), hidden field -
          > platform (for articles etc.)

      - media/widget - new content type - let librarian scroll through
        > options to select from or create on the fly to add as a new
        > node; some of these might be made as blocks, and the librarian
        > could select the block to add

      - books - new content type - let librarian create on the fly,
        > reuse existing ones, have different fields to handle a print
        > book (call number, location, link to cat record) vs an ebook
        > (link to Pub Finder record for it), eg
        > [<u>https://ask.springshare.com/libguides/faq/961</u>](https://ask.springshare.com/libguides/faq/961)
        > look at step 8 under Add section for ideas of fields to
        > include, and step 5 under Reuse for an idea of what that
        > dialogue might look like;  
        > title, author/editor, publisher, year, edition, optional cover
        > picture, URL, note, hidden checkbox for print vs e that can be
        > used to change formatting

      - images - thumbnail and click to open full size in (new tab?) -
        > new content type(already standard with Drupal?)

      - other content types in the Drupal installation eg "Interactive
        > Content" (aka H5P)

      - functionality to reorder within box

    - Stretch goal - allow for creation of tabbed boxes, see examples:
      > [<u>https://ask.springshare.com/libguides/faq/849</u>](https://ask.springshare.com/libguides/faq/849)
      > and
      > [<u>https://guides.lib.uni.edu/youthbooks/ebooks</u>](https://guides.lib.uni.edu/youthbooks/ebooks)

Patron view of created content:

- This is an excellent example of what we're going for, but within our
  > Drupal theme:
  > [<u>https://libguides.kpu.ca/</u>](https://libguides.kpu.ca/)

- Filters to limit by type of guide and/or group and/or subject - see
  > sample video:
  > [<u>https://www.youtube.com/watch?v=uIUJV_3eWEw&t=23s</u>](https://www.youtube.com/watch?v=uIUJV_3eWEw&t=23s)

- Render the guide using the default site theme as much as possible

- Stretch goal - printability of an entire guide - pull all of the
  > content into a single PDF in the order they are in the nav

Nov 21, 2023update:

On the functionality of linking an existing page or box to another
guide, I would like for the option to link (Libguides calls it
"mapping") an existing page into another guide, or an existing box into
another page, as "read only" by which I mean the linking user can add or
remove it from their own guide/page, but not edit it at all and not
delete it from the system, so only the creating user can actually edit
and delete it. That will have some permission implications for you, but
will make other aspects much simpler (no need for a dialogue involving
trying to report what other guides/pages are using the content and are
you sure you want to delete it for everyone!).

Basically the issue is how to handle reusing existing content, eg a page
that already exists as part of a guide when another user wants to use it
in their own guide, and what should happen if the second user wants to
delete it, and all of that ditto for boxes within pages.

The idea is that the original guide/page owner controls the page's/box's
content and existence, and anyone else can make what I'll call a "read
only" link (instead of making a full copy that becomes their own
separate node), and if they do that, they cannot edit or delete it, but
just remove it later from their own guide/page. The original owner can
edit it and remove it from their own page, or delete it entirely, but if
they delete it entirely, it will create a broken "link" for the other
guide/page. A stretch goal would be to actually detect if the page/box
is linked in another guide/page when the owner seeks to delete it fully,
and warns them.

***November 26*** update: Roles, Permissions, Users - text copied from
Drupal 10 admin settings pages:

**Roles:**

A role defines a group of users that have certain privileges. These
privileges are defined on the Permissions page. Here, you can define the
names and the display sort order of the roles on your site. It is
recommended to order roles from least permissive (for example, Anonymous
user) to most permissive (for example, Administrator user). Users who
are not logged in have the Anonymous user role. Users who are logged in
have the Authenticated user role, plus any other roles granted to their
user account.

**Permissions:**

Permissions let you control what users can do and see on your site. You
can define a specific set of permissions for each role. (See the Roles
page to create a role.) Any permissions granted to the Authenticated
user role will be given to any user who is logged in to your site. On
the Role settings page, you can make any role into an Administrator role
for the site, meaning that role will be granted all permissions. You
should be careful to ensure that only trusted users are given this
access and level of control of your site.
