What is CS-4820-Library Project?

This organization exists as a place to organize various projects done by teams of University of Prince Edward Island computer science students through the "capstone" CS4810-CS4820 2-semester course. The projects in this organization are all done with the UPEI librarian Melissa Belvadi acting in the role of "client", providing the project requirements and primary design support and guidance. The projects included here span multiple years ("cohorts") of student teams taking that course.

Projects completed by year (always completed in spring of the year or as UPEI calls it "winter semester"):

# 2026:
There were two projects in 2026, with 3 different teams working on each, independently.  All of the teams did excellent work and there are features of particular strength for each.

## LCCN Harvester Project

This project provides python3/PyQt6 code to enable librarians who have a list of ISBNs to "harvest" LC Call Numbers (and also NLMCNs if desired) using 3 major APIs as well as Z39.50 connections to library catalogues of their choice. The project puts the data both in a tsv output file, but also an sqlite database file.
For more information, read [the project specs](https://github.com/CS-4820-Library-Project/.github/blob/main/LCCN_2026.md).

* [LCCN-harvester-team6-2026](https://github.com/CS-4820-Library-Project/LCCN-harvester-team6-2026)
* [LibraryMetadataHarvester_Team5](https://github.com/CS-4820-Library-Project/LibraryMetadataHarvester_Team5)
* [LCCN_Harvester (Team 4)](https://github.com/UPEI-LCCN-harvester-group-4/LCCN_Harvester)

## Guide on the Side Project

This project asks the students to use WordPress and Pressbooks to develop a tool that librarians can use to create interactive tutorials, with a split page design, so the left pane gives the instructions and self-quiz questions and the right pane provides some kind of "live" content, either binary objects (PDFs, videos, etc.) loaded directly to the server, or URLs, eg to the library's website, catalog, research databases, etc.
We didn't discover until well into the project that most library websites are now protected by Cloudflare which prevents them from being embedded in an iframe. One team came up with a creative solution to that, but all three at least offer an "open in new window/tab" option so users can easily switch between the guided steps and the live session.
For more information read [The project specs](https://github.com/CS-4820-Library-Project/.github/blob/main/Guide_on_Side.md)

Repositories coming soon!

* [Team 7]
* [Team 8]
* [Team 9]

# 2024

Four (!) projects with multiple independent teams this year. Most of these are public, but contact me if you want access to a private one.

## Ebooks perpetual access tracking

UPEI belongs to a Canadian academic library consortion called [CRKN](https://www.crkn-rcdr.ca/en). CRKN is developing a standard spreadsheet system for libraries to keep track of their perpetual access rights (PAR) for ebooks licensed from various publishers/platforms, including licenses through CRKN and also directly from the vendor.
This project was to build a desktop app that can "harvest" from the CRKN websites the spreadsheets with that data, and also ingest locally maintained spreadsheets following the same structure. Then it would provide an easy to use GUI to search that data and keep track of the PAR licenses in case the library needs to dispute their rights with any provider/publisher. [Specs](https://github.com/CS-4820-Library-Project/.github/blob/main/CRKN_Ebooks_PAR.md)

* [EPAT Team 8](https://github.com/CS-4820-Library-Project/EPAT_Team8)
* [EPAT Team 3](https://github.com/CS-4820-Library-Project/Ebook_Perpetual_Access_Tracking)

## LCCN Harvester (2024)

I first tried the LCCN harvester project in 2024. Unfortunately I had designed the project to rely heavily on OCLC's API to get the data, but mid-way through the academic year, OCLC abruptly eliminated their API. That left the teams and me scrambling.  The teams did a great job under the circumstances, but I have to recommend the use of one of the 2026 projects at this point.  But I still appreciate the work these teams did and want to showcase their code. [Specs](https://github.com/CS-4820-Library-Project/.github/blob/main/LCCN_Metadata.md)

* [Library-Metadata-Harvester-2024 (Team 2)](https://github.com/CS-4820-Library-Project/Library-Metadata-Harvester-2024)
* [LibraryMetadataHarvester_Team5 (2024)](https://github.com/CS-4820-Library-Project/LibraryMetadataHarvester_Team5)

## Research Guide management system for Drupal sites

UPEI's library uses the open source Drupal web content management system. This project was to create a Drupal module that would help librarians create and manage systems of "guides", as a kind of simplified and open source version of the commercial service known as "LibGuides".
The students did excellent work and produced fine modules for the library Drupal (9 and 10) community.[Specs](https://github.com/CS-4820-Library-Project/.github/blob/main/drupal_guides.md)

* [Library-Research_Guides_Drupal10](https://github.com/CS-4820-Library-Project/Library-Research_Guides_Drupal10)
* [LGMS (Library Guide Management System)](https://github.com/CS-4820-Library-Project/LGMS)

## COUNTER 5.1 API Harvester

This was meant to be the upgrade to the 2020 COUNTER 5.0 Harvester. The students did a lot of good work on this.  Unfortunately, the timing was off - none of the expected library content providers (eg publishers) had their Code of Practice 5.1 API up and running in time for these students to have test servers to work with.
Their GUI designs were very good. One used Python and the other used Electron.
I have kept both repositories private so some poor librarian doesn't stumble into either and try to install them. If you want access to the code, contact me.
[Specs](https://github.com/CS-4820-Library-Project/.github/blob/main/COUNTER51_2024.md)

In 2025, after discovering the magic of using genAI to help write code, I developed my own COUNTER 5.1 Harvester, not as part of a CS 4820 class. I had a UPEI CS student write the GUI for me. I keep that in [my own repository](https://github.com/Melissa-Belvadi-Library-Projects/C5.1_Harvester), and maintain it (because I use it too, all the time!). It is a desktop app written in Python3 with PyQt.


* [COUNTER-5.1-Report-Harvester](https://github.com/CS-4820-Library-Project/COUNTER-5.1-Report-Harvester) - based on Electron
* [COUNTER_Harvester_5.1](https://github.com/CS-4820-Library-Project/COUNTER_Harvester_5.1) - based on Python

# 2020:

The project this year was to develop a GUI based desktop app that would use the COUNTER Metrics usage data API system (called "SUSHI API" back then) so libraries could collect all of the COUNTER usage data from all of their content providers (eg publishers, aggregator platforms) easily and put all the data into an sqlite3 database for more advanced analysis than the traditional method, manually downloading all those spreadsheets one at a time per provider.
COUNTER Metrics is now (as of 2025) on Code of Practice 5.1, which included major changes, so this project app is only relevant for providers who haven't yet updated their systems to support 5.1.  But as of April 2026, that's still quite a few smaller but important content providers.
This app was incredibly useful to UPEI over these past years.

[COUNTER-5-Report-Tool-2020-5.0](https://github.com/CS-4820-Library-Project/COUNTER-5-Report-Tool-2020-5.0)
