|| Webhost Projects - Hosting modules for an Angular application ||

- Their IIS configuration and setting up already done in the WebApi documentation
	- Move this documentation for (admin/advice/dash) to WebApps 

- Generally web projects can be hosted statically on their own, alternatively to have server side 
abilities, a server side host application may be built to satisfy some requirements on the server
side before the browser (client) even shows the first icon; some instructions may be first met
- They don't directly serve the application UI, but it's an ASP.NET infrastructure to perform some
instructions before the serving of the actual apps

A distribution folder is created when the Angular app is published
- saved in the wwwroot folder in the ASP.NET WEB-host project(s)

- Web host modules allow checks to be made in the server-side before the application may be permitted
to be downloaded to the client to run (loaded) on their browser application (security decisions)
	- Client side logging (client app loggs to its parent which in turn the parent loggs it 
forward to our logging (seq))
	- Middleware (API has validation) is able to catch tampering of the source code of 
the application (even if a client has done something to the application)