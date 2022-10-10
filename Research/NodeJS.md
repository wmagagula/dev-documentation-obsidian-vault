NodeJS

	|| YARN VS NPM ||
https://www.sitepoint.com/yarn-vs-npm/
https://phoenixnap.com/kb/yarn-vs-npm

* (yarn vs npm) Both package managers carry out a series of tasks when installing packages and the
 main difference in their performance:
	- npm executes its installation tasks sequentially per package (this blocks continuation of
installing other packages till the current install is finished). With yarn these installation tasks 
per package are done simultenously (parallel is the word often used), edging npm.
	- yarn offers a better caching implementation (called a zero-install paradigm), saves package
installs on disk so in next installs of the package even without internet connection, it can be quicker
since it does not go to the registry again

What is it?
- Open source, cross-platform

