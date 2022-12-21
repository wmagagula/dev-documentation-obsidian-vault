Our current Branch coverage report generator for WebAPI uses 'opencover' instead of 'cobertura'
- These two report generators tend to be different in their assessment of branch code test coverage

[ExcludeFromCodeCoverage] Nick Chapsas "you're littering your code; it's something it doesn't need to know about"
- Wherever you include this attribute it will treat the file as covered

What are we trying to do?
- Figure out why code coverage is at 0% for the tla branch (branched from la-main) which is being PR'd to la-main on this PR [out-it-dev / outvest.webapi / Pull Request #206: Feature/OVT-8562 tla reveal page — Bitbucket](https://bitbucket.org/out-it-dev/outvest.webapi/pull-requests/206/feature-ovt-8562-tla-reveal-page?link_source=email). There is also a test branch which also does the same [out-it-dev / outvest.webapi / Pull Request #209: A minor change to test sonarqube analysis — Bitbucket](https://bitbucket.org/out-it-dev/outvest.webapi/pull-requests/209). 

STEPS:
Carike - added coverage steps

