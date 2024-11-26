
# Azure AD SAML SSO

This solution is an example of an API with minimal configuration to implement authentication in Microsoft Active Directory (now called Microsoft Entra Id) Single SignOn with SAML. The point of this repository is to be able to create an api with .net 8 quickly using the Sustainsys.SAML2 package.

## Configuration

You must have an Azure account, with administrator role.

In the Microsoft Entra Id panel you must create a new business application and add the groups or people you will allow to log in using the service.

Then in Single SignOn configuration in the Entity ID field you will write down the URL identity of your service, in my case I write ```https://localhost:5001/``` which is the address of my service in development environment.

Last you should add to the Response Urls this endpoint ```https://yourApp/Saml2/Acs``` (in my case ```https://localhost:5001/Saml2/Acs```). 

Important: That's because is an endpoint created by Sustainsys.SAML2 to process the SAML response and is the return URL that the app really uses facing Azure, the final return endpoint that you create is invoked by Sustainsys.SAML2 so azure will not deal with it.

Once you have configured Azure Microsoft Entra ID write down the appsettings.json configurations following the file.

That's it you can run it and debug.

This is a simplified version of the example given by [hmacat](https://github.com/hmacat) 

Link: https://github.com/hmacat/Saml2WebAPIAndAngularSpaExample/tree/master



Thanks to [hmacat](https://github.com/hmacat).






