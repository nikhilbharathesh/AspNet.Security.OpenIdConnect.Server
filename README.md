AspNet.Security.OpenIdConnect.Server
==================================

**AspNet.Security.OpenIdConnect.Server** is an **OpenID Connect server middleware** that you can use in **any ASP.NET 5 application** and that works with the official **OpenID Connect client middleware** developed by Microsoft or with any **standards-compliant OAuth2/OpenID Connect client**.

**The latest nightly builds can be found here**: **[https://www.myget.org/F/aspnet-contrib/](https://www.myget.org/F/aspnet-contrib/)**

[![Build status](https://ci.appveyor.com/api/projects/status/tyenw4ffs00j4sav/branch/vNext?svg=true)](https://ci.appveyor.com/project/aspnet-contrib/aspnet-security-openidconnect-server/branch/vNext)
[![Build status](https://travis-ci.org/aspnet-contrib/AspNet.Security.OpenIdConnect.Server.svg?branch=vNext)](https://travis-ci.org/aspnet-contrib/AspNet.Security.OpenIdConnect.Server)

## Dependencies

The current version relies on the latest version of **ASP.NET 5** and the **OpenID Connect extensions** that can be found on **MyGet.org**:

* **[https://www.myget.org/gallery/aspnetvnext](https://www.myget.org/gallery/aspnetvnext)**

* **[https://www.myget.org/gallery/azureadwebstacknightly](https://www.myget.org/gallery/azureadwebstacknightly)**

## Get started

Based on `OAuthAuthorizationServerMiddleware` from **Katana 3**, **AspNet.Security.OpenIdConnect.Server** exposes similar primitives and can be directly registered in **Startup.cs** using the `UseOpenIdConnectServer` extension method:

    app.UseOpenIdConnectServer(options => {
        options.Issuer = "http://localhost:55938/";
        options.SigningCredentials = new SigningCredentials(
            new X509SecurityKey(certificate),
            SecurityAlgorithms.RsaSha256Signature,
            SecurityAlgorithms.Sha256Digest);
    
        options.Provider = new CustomAuthorizationProvider();
    });

See [https://github.com/aspnet-security/AspNet.Security.OpenIdConnect.Server/tree/vNext/samples/Mvc](https://github.com/aspnet-security/AspNet.Security.OpenIdConnect.Server/tree/vNext/samples/Mvc) for a sample **using MVC 6 and showing how to configure a new OpenID Connect server using a custom `OpenIdConnectServerProvider` implementation to validate client applications**.

## Contributors

**AspNet.Security.OpenIdConnect.Server** is actively maintained by **[Kévin Chalet](https://github.com/PinpointTownes)**. Contributions are welcome and can be submitted using pull requests.

## License

This project is licensed under the **Apache License**. This means that you can use, modify and distribute it freely. See [http://www.apache.org/licenses/LICENSE-2.0.html](http://www.apache.org/licenses/LICENSE-2.0.html) for more details.