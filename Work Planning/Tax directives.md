- Add Tax Directive option to client actions

- client details
    - [x]  Get client details Client/{identityKey}

* Get Tax Directive info -- check in TAU, then respond to frontend
	{
	 TaxRate: number,
	 TaxDirectiveNumber: number,
	 EffectiveDate: datetimeoffset,
	 ExpiryDate: datetimeoffset
	}

	Available Endpoints for configuring tax directive 
	- Get tax directive info for client (the user's structure path): 
		- GET => investors/{investor_urn}/paye_tax_configurations

* Update Tax Directive info model
	{
	 TaxRate: number,
	 TaxDirectiveNumber: number,
	 EffectiveDate: datetimeoffset,
	 ExpiryDate: datetimeoffset,
	}

	Since there needs to be only one active tax directive for an investor
	- Delete Existing PAYE config => POST paye/{paye_urn}/delete
	* Post tax directive info for investor
		* POST => paye/
- Save tax directive doc in AdminDocumentsTable
	* Endpoint: Admin/Client/{clientId}/Upload/{documentType}" -- UploadAdminDocumentController*
	* Endpoint for system docs

Questions to ask: 
	- What kind of document wil the tax directive? -- received from SARS directing us how to tax
		- client only indicates they have a tax directive on the onboarding journey
	- Is the document going to be downloaded again?
		- Transfer area screen we would display infor from the document?
		- Should be able to view even expired ones -- yes as part of the documentation
		- Are we saving this to our db? Is it going to TAU? -- our db

To do as of 28th
- [ ] TAU endpoints to find for tax configs...
	- When is the {annuity_urn} created? During 'goal-approval'?
	- We need the approval of the LA product first (to have the investor and annuity_urn created first)

	
	"I'm just gonna look what's there and make an implementation plan then I'll get back to you, to confirm for a story telling session" -- Respond this way when asked if you're clear on everything needed


In the two journeys

* Transfer - what an investor is currently investing with another company
	* Only in the process when the admin team is working with the other company to find out all those information
	* 

* In the RLA the user can indicate
* Double check which one is active in TAU; if you can have many uploaded and existing there
* Should show doc in uploaded documentation


PAYE_configuration 
- tax_basis:
	- Enum to specify whether we use Rate/Amount for the TaxDirectiveValue

PAYE_configuration for Tax directive

- In TAU an Investor can have multiple tax directive configs but they cannot overlap 
	- the effective dates must be past the expiry date of the previous tax directive configuration

- There always should be "only one" active tax directive config

Since we retrive info from TAU for tax directive

