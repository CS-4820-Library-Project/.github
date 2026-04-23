Minimum deliverables:

User context:

Library staff who need to check if they have perpetual access rights
(PAR) to a particular ebook on a particular platform.

CRKN is a consortium of libraries that provides licenses for some ebook
packages for its member libraries. In those cases, CRKN provides the
spreadsheets listing exactly which ebooks it has licensed, and for which
members. There will be one spreadsheet per platform (eg Proquest, Taylor
& Francis, De Gruyter, etc.). There will be one tab, labeled pa-rights,
which contains all of the information needed by this project.

Those spreadsheets will be accessible on their public website, on a
specific page (URL to be provided), with a file naming convention that
allows the program to determine the last update date.

In other cases, the library itself tracks its own licenses. Some of
those ebook licenses are on some of the same platforms as the CRKN
licenses, and some are on other platforms. Libraries will provide
spreadsheets, one per platform, following exactly the same format as the
CRKN ones except for having just one column for the local library rather
than the 70+ columns for all of the CRKN members.

In both sets of spreadsheets, the institution's column (indicating
whether the institution has PAR for the title) will be headed by exactly
the same institutional abbreviation. At the first run of the installed
program, it will prompt the user to supply that exact abbreviation,
which will then be stored for re-use.

Desktop app

- runs on Windows or Mac \[stretch goal to work on Linux too\]

- does not touch the Windows registry

- runs entirely self-contained within a single folder/directory tree

- Does not require the user to install anything else for it to work (eg
  > no Apache local server, no .Net framework, no programming language
  > interpreter/modules)

- The entire program could be installed multiple times in different
  > folders on the same desktop computer and not interfere with each
  > other (ok if they can't literally be running at the same time).

- Allows the user to search by title (case-insensitive substring match),
  > ISBN (exact match), or OCN (exact match)

- Returns to the user a tsv file showing all of the metadata matching
  > the provided search query from that row of all spreadsheets that
  > matched it, CRKN and local, except just showing that institution's
  > column value, not all of the CRKN members' values (local files will
  > have only the local institution's column).

- Program should loop so user can run multiple queries without
  > restarting the program each time, getting a different tsv file each
  > time.

- User should be able to modify the tsv output filename and location to
  > save it at the point at which it is ready to be saved. The default
  > filename should be report.tsv.

- Upon each program start, the program should check the CRKN website to
  > see if any of the files have been updated, based on their filenames,
  > and if any have been, tell the user that CRKN data has been updated
  > and do they want to perform the update now? If the user says yes, do
  > a complete re-load of the changed files. \[Stretch goal - provide
  > some kind of progress indicator\]

- Another option available to the user before they start a search is to
  > upload/replace any local files they have available. The dialogue box
  > should let them navigate to the file's local location and pick the
  > file using the usual operating system dialogue for such picks. The
  > files will follow the same naming convention as CRKN and should
  > add/replace the data based on whether a previous version of that
  > filename had been uploaded.
