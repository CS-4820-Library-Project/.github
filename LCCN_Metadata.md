Input: given a list of either ISBNs or OCNs, use various internet
sources to return related metadata.

Specifically, return the metadata two ways:

1.  save it in an sqlite database AND

2.  give back to the user a tab-delimited file with the metadata.

The list of sources includes several APIs plus webscraping a list of
Blacklight-based library catalogues and a list of Worldcat-based library
catalogs.

The user should be asked the following questions (this might be
command-prompt or GUI):

1.  the name/path to the file containing the list

2.  whether the list is ISBNs or OCNs

3.  which of the sources do they want to be used (let them select
    > multiple, or an easy way to say "all")

4.  If the answer to \#2 was ISBNs, ask if they also want OCNs

5.  If the answer to \#2 was OCNs, ask if they also want OCNs

6.  Ask if they want LCCNs (Library of Congress Call Numbers, not to be
    > confused with Library of Congress Catalog Numbers which is often
    > also abbreviated LCCN!)

7.  Ask if they want DOIs (stretch goal)

Always check for the existence of the sqlite database first. If it
exists, always check it for the desired metadata before using the
internet sources. If it doesn't exist, create it and use this query to
start populating it.

The tab-delimited file should include first the header row:

ISBN \[tab\] OCN \[tab\] LCCN \[tab\] LCCN-source \[tab\] DOI

If they didn't want any of those, leave those columns blank

For instance if they wanted all of them it might look like:

9781234567890\[tab\]123456789\[tab\]BF123.C4.J12
2015\[tab\]OCLC\[tab\]10.1002/123.57483

If they wanted only the LCCN it might look like:

9781234567890\[tab\]\[tab\]BF123.C4.J12 2015\[tab\]OCLC

If they wanted just the OCN, it might look like:

9781234567890\[tab\]123456789

If the list was OCN and they only wanted the LCCN it would look like:

\[tab\]123456789\[tab\]BF123.C4.J12 2015\[tab\]OCLC

I leave it up to you to decide how to structure this in the sqlite
database, whether it's all one table or multiple pairwise tables (eg one
table is that is just ISBN-OCN, another that is just
ISBN-LCCN-LCCN-source, another that is just ISBN-DOI but always keep the
LCCN and its source together).

Stretch goal: sometimes OCLC will return multiple LCCN options and/or
multiple OCN options for a single ISBN. Usually you will also have for
those the number of libraries that used one versus the other. In that
situation, choose the highest-count for the tab-delimited file, but
think of a way to save all of it in the sqlite database (getting
"relational" in structure for this).
