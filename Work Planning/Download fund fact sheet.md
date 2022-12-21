- limitations: rushing to get it in
- zip on the api and unzip on the ui browser and blob them out 
- send them as an attachment on the email
- open tabs to open the docs

- image url might not work since it's still pointing to old website.
	- Need to move these images to advice then update the urls
	- Styling for the image sizes

DTO - wi

GetFundsController
- 

- Show modal with all fund sheets available for the user to download


Inputs from reveal pages

- Fund reveal gives FundId - tax free savings (doesn't have InstrumentData)
- RA & Pres gives instrumentCode
- LA gives InstrumentAllocation list
- LA custom selection gives InstrumentName
- LA selection recommended gives InstrumentName


Important things to think about:
- Always look for a way to make it easy for a lot of things not to change
- Root of the domain then to webApi


FinInstrumentServiceProps

Instrument table is the most up to  date since these have information to get richer properties (get )

- Instrument code may change
- We don't want to show the fixedOutcome
Get all unittustandetfInstrumentProps -- into that type T we want (where the properties and their types; then we deserialize according to the matches the 'fromJson' finds)... We don't 

-1 for anything that doesn't have fundId

Instruments are the new but funds are old (we still reference using the fundId)
- For each product you must show the valid funds (which are specific regulation)

InstrumentData
* If the requirements change in future to show all the funds

Note: fix code for the url's
* build the component in such a way that it is resistant to change -- but it must trust the API in bringing it the right information; it doesn't care where it's coming from*

appsettings.json as global settings

* How can the backend get to do most of this work*
* https://local.outvest.co.za/MobileApp/GetFundFactSheet/4 -- pres fund test
* https://local.outvest.co.za/MobileApp/GetFundFactSheet/2 -- tax free, fund reveal
* https://local.outvest.co.za/MobileApp/GetFundFactSheet/5 -- LA 
* https://local.outvest.co.za/MobileApp/GetFundFactSheet/3