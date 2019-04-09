## U4.ExtensionsKit.PowerShell module

### Getting Started

Unit4 Extensions Kit provides a set of PowerShell commandlets to support / simplify / automate administrative tasks. These commandlets are published at the Unit4 PP Nuget store.

### Index
1. [Install the U4.ExtensionsKit.PowerShell module](#Install-the-U4.ExtensionsKit.PowerShell-module)
2. [Update to the latest version](#Update-to-the-latest-version)
3. [Get commands available](#Get-commands-available)
4. [Get help for a command](#Get-help-for-a-command)
5. [Handling of the session](#Handling-of-the-session)


### Install the U4.ExtensionsKit.PowerShell module

Check if the People Platform nuget repository is already registered on your computer:

```
Get-PSRepository
```

If not listed, register it:

```
Register-PSRepository -Name U4PP -SourceLocation "https://packages.u4pp.com/nuget/nuget/" -PublishLocation "https://packages.u4pp.com/nuget/nuget/" -PackageManagementProvider NuGet -InstallationPolicy Trusted
```

You can now search for modules like U4.ExtensionsKit.PowerShell:

```
Find-module -Name U4.ExtensionsKit.PowerShell
```

>Before instaling the module, **make sure you have the latest version of .NET installed** when running the Identity Services PowerShell commandlets. **The powershell commandlets have been verified on .NET 4.7.2.** Always start a new PowerShell session if you have upgraded the .NET framework.

To install the module:
```
Install-Module -Name U4.ExtensionsKit.PowerShell -Repository U4PP -Scope AllUsers
```
### Update to the latest version
> We recommend that you check for new versions of the Identity Services powershell commandlets regularly. To avoid dependency conflicts always make sure you start a new PowerShell session or window after an upgrade.

To keep the module up to date run the following command:
```
Update-Module -Name U4.ExtensionsKit.PowerShell -Force
```

### Get commands available

To find supported commands:

```
Get-Command -Module U4.ExtensionsKit.PowerShell
```

### Get help for a command

The latest documentation is always available by using Get-Help, for instance:

```
Get-Help -Name Connect-U4EK -Full
```
### Handling of the session

To use the Unit4 ExtensionsKit PowerShell commandlets, the user (and/or client) must be authenticated and authorized. The commandlet pair `Connect-U4EK / Disconnect-U4EK` is used to establish/close the session. When establishing a session we can use two different authentication methods, `ClientCredentialAuth` and `ImplicitFlowAuth`.

Once the session is established with Connect-U4EK and the desired operations were executed, **it is highly recommended to close the session with the Disconnect-U4EK commandlet.** This commandlet does not have any parameters. All session data will be cleared.

>Note If you can't connect with error "An error occurred while sending the request", it could be the TLS 1.2 issue. Try setting the SecurityProtocol variable in PowerShell or update your registry settings as shown below

**Example: Set SecurityProtocol variable from PowerShell command prompt**
```
[System.Net.ServicePointManager]::SecurityProtocol = [System.Net.SecurityProtocolType]::Tls12
```

**Example: Set Tls1.2 "permanently" in Registry**
```
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]
"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\v4.0.30319]
"SchUseStrongCrypto"=dword:00000001
```

#### ClientCredentialAuth

**Parameter** | **Description**
--- | --- 
EKApiUri | The Uri of the Unit4 ExtensionsKit API
ClientId | An administrative client configured in the Unit4 Identity Services using ClientCredentials flow
ClientSecret | The secret defined for the administrative client configured in the Unit4 Identity Services

Sample:
```
Connect-U4EK -ClientCredentialAuth -EKApiUri "https://ek-sandbox-api.u4pp.com/"  -ClientId "u4-ek-develop-powershell"  -ClientSecret "fake7bb6-582e-4c7a-8bb2-190f05d2f3dd"
```

#### ImplicitFlowAuth

**Parameter** | **Description**
--- | --- 
EKApiUri | The Uri of the Unit4 ExtensionsKit API
ClientId | An administrative client configured in the Unit4 Identity Services using ClientCredentials flow
Tenant | The Tenant for which the commands will be executed. An interactive login process will be initiated.

Sample:
```
Connect-U4EK -ImplicitFlowAuth -EKApiUri "https://ek-sample-api.u4pp.com/"  -ClientId "u4-ek-client"  -Tenant "bb493cc3-fake-4b55-ac17-36a741c5e9bb"

```