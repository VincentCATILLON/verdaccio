13 Mar 2014, version 0.7.0

- config changes:
  - breaking change: all time intervals are now specified in *seconds* instead of *milliseconds* for the sake of consistency. Change `timeout` if you have one!
  - all time intervals now can be specified in [nginx notation](http://wiki.nginx.org/ConfigNotation), for example `1m 30s` will specify a 90 seconds timeout
  - added `maxage` option to avoid asking public registry for the same data too often (issue #47)
  - added `max_fails` and `fail_timeout` options to reduce amount of requests to public registry when it's down (issue #7)

- bug fixes:
  - fix crash when headers are sent twice (issue #52)
  - all tarballs are returned with `Content-Length`, which allows [yapm](https://github.com/rlidwka/yapm) to estimate download time
  - when connection to public registry is interrupted when downloading a tarball, we no longer save incomplete tarball to the disk

- other changes:
  - 404 errors are returned in couchdb-like manner (issue #56)

5 Mar 2014, version 0.6.7

- pin down express@3 version, since sinopia doesn't yet work with express@4

28 Feb 2014, version 0.6.5

- old SSL keys for npm are removed, solves `SELF_SIGNED_CERT_IN_CHAIN` error

3 Feb 2014, version 0.6.3

- validate tags and versions (issue #40)
- don't crash when process.getuid doesn't exist (issue #41)

18 Jan 2014, version 0.6.2

- adding config param to specify upload limits (issue #39)
- making loose semver versions work (issue #38)

13 Jan 2014, version 0.6.1

- support setting different storage paths for different packages (issue #35)

30 Dec 2013, version 0.6.0

- tag support (issue #8)
- adding support for npm 1.3.19+ behaviour (issue #31)
- removing all support for proxying publish requests to uplink (too complex)

26 Dec 2013, version 0.5.9

- fixing bug with bad Accept header (issue #32)

20 Dec 2013, version 0.5.8

- fixed a warning from js-yaml
- don't color multiline strings in logs output
- better error messages in various cases
- test format changed

15 Dec 2013, version 0.5.7

- try to fetch package from uplinks if user requested a tarball we don't know about (issue #29)
- security fix: set express.js to production mode so we won't return stack traces to the user in case of errors

11 Dec 2013, version 0.5.6

- fixing a few crashes related to tags

8 Dec 2013, version 0.5.4

- latest tag always shows highest version available (issue #8)
- added a configurable timeout for requests to uplinks (issue #18)
- users with bad authentication header are considered not logged in (issue #17)

24 Nov 2013, version 0.5.3

- added proxy support for requests to uplinks (issue #13)
- changed license from default BSD to WTFPL

26 Oct 2013, version 0.5.2

- server now supports unpublishing local packages
- added fs-ext dependency (flock)
- fixed a few face conditions

20 Oct 2013, version 0.5.1

- fixed a few errors related to logging

12 Oct 2013, version 0.5.0

- using bunyan as a log engine
- pretty-formatting colored logs to stdout by default
- ask user before creating any config files

5 Oct 2013, version 0.4.3

- basic tags support for npm (read-only)
- npm star/unstar calls now return proper error

29 Sep 2013, version 0.4.2

28 Sep 2013, version 0.4.1

- using mocha for tests now
- making use of streams2 api, doesn't work on 0.8 anymore
- basic support for uploading packages to other registries

27 Sep 2013, version 0.4.0

- basic test suite
- storage path in config is now relative to config file location, not cwd
- proper cleanup for temporary files

12 Jul 2013, version 0.3.2

4 Jul 2013, version 0.3.1

- using ETag header for all json output, based on md5

20 Jun 2013, version 0.3.0

- compression for http responses
- requests for files to uplinks are now streams (no buffering)
- tarballs are now cached locally

19 Jun 2013, version 0.2.0

- config file changed, packages is now specified with minimatch
- ability to retrieve all packages from another registry (i.e. npmjs)

14 Jun 2013, version 0.1.1

- config is now autogenerated
- tarballs are now read/written from fs using streams (no buffering)

9 Jun 2013, version 0.1.0

- first npm version
- ability to publish packages and retrieve them locally
- basic authentication/access control

22 May 2013, version 0.0.0

- first commits
