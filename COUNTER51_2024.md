Folder link:
[<u>https://drive.google.com/drive/folders/1-qbaWo0-gjXAEy1o_Qdt-yZEVLk2gnNa?usp=drive_link</u>](https://drive.google.com/drive/folders/1-qbaWo0-gjXAEy1o_Qdt-yZEVLk2gnNa?usp=drive_link)

General: use the Project COUNTER SUSHI API protocol to retrieve all
possible data from vendors' SUSHI servers, using 5.0 or 5.1 COUNTER
specs as supported by the individual vendor. Put the data into tsv
files, and also into an sqlite database. Code should be fully
self-contained into an executable, not requiring installation of
anything other than itself to run. Minimal compatibility for Windows 10
and 11, stretch goal to also be compatible with Mac, and separately,
Linux.

Changes between 5.0 and 5.1 include significant change to the JSON
format

Note that the older project was written for 5.0 but COUNTER now has
5.0.3 in effect now, so changes to 5.0 handling/errors may be needed.

[<u>5.1 documentation</u>](https://cop5.projectcounter.org/en/5.1/)

[<u>5.0.3 documentation</u>](https://cop5.projectcounter.org/en/5.0.3)

Changes from 5.0 to 5.0.3 and from 5.0.3 to 5.1 are documented
[<u>here</u>](https://github.com/Project-Counter/cop5/blob/5.1/CHANGELOG.rst)

Specific features:

- Vendor information/table:

  - Fields (all are text):

    - vendor name (required, unique enforced)

    - is this 5.0 or 5.1?

    - base URL for 5.0 (required) OR 5.1

    - starting year for this version (5.0 or 5.1) (required)

    - customer_id (required)

    - requestor_id

    - api_key

    - platform

    - whether it requires two attempts per report (Y/N, required)

    - whether does IP checking (Y/N, required)

    - whether needs requests throttled (Y/N, required)

    - notes

    - provider

  - Storage - needs to be password-protected in some way

  - Way to manually update this information (eg GUI form screen) -
    > add/modify/delete

  - Way to batch export to tsv and batch import from tsv

- Retrieving reports:

  - In all cases, use the vendor info re 5.0 vs 5.1 to handle the query
    > and json result correctly

  - Always start by request the list of supported reports and then get
    > each one from that list (except see below if user is selecting
    > specific reports)

  - One-click option to get all valid reports from all vendors for YTD
    > (eg if running in October, get Jan-Sept) or any full prior year

    - generate tsv files for these - store in folder tree Vendor-name
      > then all reports for all years within that

    - store data in sqlite database

    - have mechanism to overwrite past fetches when updates/re-run
      > (either entire previous year or monthly updates) (Note:
      > sometimes vendors announce that their previous data from a
      > particular period was wrong and tell everyone to re-retrieve
      > those months)

  - Option to get any specific report(s) (multi-select) from any
    > specific vendors (multi-select), with any specific
    > attributes/limiters (multi-select) for any date range (month/year
    > select)

    - don't let user select a report type not supported by the
      > vendor(s), or give warning after checking/run starts

    - specific attributes - defaults are defined by the standard

    - changes can be made to add or remove - both attributes_to_show and
      > attributes_to_include but if user makes a change to attributes
      > to include that one should also automatically be set to show

      - data_type

      - access_type

      - access_method

      - metric_type

      - YOP (whether to break out, default for TR is no)

    - TBD: how to detect and offer options to include vendor-specific
      > extensions:
      > [<u>https://www.projectcounter.org/code-of-practice-five-sections/11-extending-code-practice/</u>](https://www.projectcounter.org/code-of-practice-five-sections/11-extending-code-practice/)

  - Log all SUSHI URLs and any error messages received in an ascii
    > logfile. Separate logfile per session?

  - Use the vendor fields relating to throttling and "needs two
    > attempts" to handle these appropriately for those vendors (TBD:
    > what throttle rate? Should value be a number of secs instead of
    > Y/N?)

  - Provide appropriate notice to user for the reports that failed (not
    > just hidden in log file) and why (human readable versions of the
    > error codes)

- Other features

  - Search: Very basic title search options - search TR by title
    > substring OR issn (either print or online) OR isbn (either print
    > or online) and return all matching results in a tsv file

  - Disaster recovery - ability to rebuild sqlite database if it gets
    > corrupted:

    - rebuild from scratch/new queries to all

  - Settings in GUI:

    - Data folders directory (from the one-click option) - user can
      > set - search database, vendor data file, and yearly reports

    - Other reports directory (from the specific reports option) - user
      > can set

  - Settings not normally changed by user - should be in plain ascii
    > file for changing as needed:

    - report request interval (overriden for those vendors with the
      > throttle option)

    - request timeout

    - concurrent vendors - user can change if they find the load on
      > their desktop is too high

    - concurrent reports

    - user agent

    - TBD - option whether vendor data can be exported to clear text?
