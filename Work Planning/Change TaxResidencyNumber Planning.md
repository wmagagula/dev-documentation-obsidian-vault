* Living Annuity - Admin 

* LA investments, providing a tax number is required: have a display at the bottom/on submit? show that atleast a SA tax residency and number is required

-> Get all client goals -- InvestmentObjective should give a clear picture.

- After client enters SA tax residency and tax number; approval to make backend request is allowed

To do:
- Add Change tax residency option on the dropdown actions for client

Change tax residency page
- client details
    - Get client details Client/{identityKey}
    {
        FullName: string,
        ID: string,
        Passport: string,
        Email: string,
        PhoneNumber: string
    }

Tau tax detials:

-> Client object has Tax details array, add tax details (update them)
    -> Tax number and urn:country are used to define callback methods and implement event handling
     return type will be void.
    -> Create Investor Dto

    -> Investor URN is gotten by making a request to GetClientInvestorIdQueryArgs


* role/investors/{urn}/tax_residences
	- tax number is null always
	- Pending tax list 
- request href for inve = "https://tau-outvest-demo.lautus.net/rest/requests/urn:tau:persistent:142144863239073171:0"

Database:
- Audit table for TaxDetailsHistory


Test plan:
- When client exists in Tau delete tax details and update db - done
- When client exist in TauDon't should have more than one tax detail inorder to delete - done
- When client doesn't exist in TAU, only remove tax details from OUTvest db - pending



UI test plan 
- on page initialization
- should require sa tax details if client has LA product 
- should send update tax details if any captured successfully
- should only delete tax details from mutable tax details list and make request to backend
- on country selected should show error if already existing country is selected


Audit Table:

CREATE TABLE [Audit].[AuditTaxDetail]
    (
        [AuditId]               BIGINT              NOT NULL PRIMARY KEY IDENTITY (1,1)
      , [AuditDateTime]         DATETIMEOFFSET      NOT NULL DEFAULT SYSDATETIMEOFFSET()
      , [AuditBy]               VARCHAR(300)        NOT NULL DEFAULT REPLACE( SUSER_SNAME(), 'SUMMIT\', '' )
      , [AuditAction]           CHAR(1)             NOT NULL

	  , [IncomeTaxNumber]       NVARCHAR (50)       NULL
      , [Client_id]             INT                 NULL
      , [CountryOfResidence]    NVARCHAR (50)       NULL
	  , [UpdatedAt]             DATETIMEOFFSET      NULL DEFAULT SYSDATETIMEOFFSET()
      , [UpdatedBy]             VARCHAR(100)        NULL
      , [IsDeleted]             BIT                 NOT NULL DEFAULT 0
      , [DeletedBy]             VARCHAR(100)        NULL
      , [DeletedAt]             DATETIMEOFFSET      NULL
    )
Go


Trigger:
CREATE TRIGGER [dbo].[Trigger_TaxDetail_Audit]
	ON [dbo].[TaxDetail]
	FOR DELETE, INSERT, UPDATE
	AS
	BEGIN
		SET NOCOUNT ON

		DECLARE
              @User           VARCHAR(300)      = REPLACE( SUSER_SNAME(), 'SUMMIT\', '' )
              , @ActionDateTime DATETIMEOFFSET(7) = SYSDATETIMEOFFSET();

            IF EXISTS ( SELECT * FROM [INSERTED] )
                BEGIN
                    INSERT
                        INTO
                            [Audit].[AuditTaxDetail]
                        SELECT
                                    @ActionDateTime
                                  , @User
                                  , 'I'
                                  , i.IncomeTaxNumber
                                  , i.Client_id
                                  , i.CountryOfResidence
                            FROM
                                    [INSERTED] as i
                END
            ELSE

            IF EXISTS ( SELECT * FROM [Deleted] )
                BEGIN
                    INSERT
                        INTO
                            [Audit].[AuditTaxDetail]
                        SELECT
                                    @ActionDateTime
                                  , @User
                                  , 'D'
                                  , d.IncomeTaxNumber
                                  , d.Client_id
                                  , d.CountryOfResidence
                            FROM
                                    [DELETED] as d
                END
	END
GO


Discussion: 

- Using the updateTaxDetails controller for admin team to add and also update existing tax details
- Should we remove tax details from the table or flag them only