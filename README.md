<!-- ********** DO NOT EDIT THESE LINKS ********** -->
<p align="center">
    <a href="https://www.asbuiltreport.com/" alt="AsBuiltReport"></a>
            <img src='https://raw.githubusercontent.com/AsBuiltReport/AsBuiltReport/master/AsBuiltReport.png' width="8%" height="8%" /></a>
</p>
<p align="center">
    <a href="https://www.powershellgallery.com/packages/AsBuiltReport.Fortinet.FortiGate/" alt="PowerShell Gallery Version">
        <img src="https://img.shields.io/powershellgallery/v/AsBuiltReport.Fortinet.FortiGate.svg" /></a>
    <a href="https://www.powershellgallery.com/packages/AsBuiltReport.Fortinet.FortiGate/" alt="PS Gallery Downloads">
        <img src="https://img.shields.io/powershellgallery/dt/AsBuiltReport.Fortinet.FortiGate.svg" /></a>
    <a href="https://www.powershellgallery.com/packages/AsBuiltReport.Fortinet.FortiGate/" alt="PS Platform">
        <img src="https://img.shields.io/powershellgallery/p/AsBuiltReport.Fortinet.FortiGate.svg" /></a>
</p>
<p align="center">
    <a href="https://github.com/AsBuiltReport/AsBuiltReport.Fortinet.FortiGate/graphs/commit-activity" alt="GitHub Last Commit">
        <img src="https://img.shields.io/github/last-commit/AsBuiltReport/AsBuiltReport.Fortinet.FortiGate/master.svg" /></a>
    <a href="https://raw.githubusercontent.com/AsBuiltReport/AsBuiltReport.Fortinet.FortiGate/master/LICENSE" alt="GitHub License">
        <img src="https://img.shields.io/github/license/AsBuiltReport/AsBuiltReport.Fortinet.FortiGate.svg" /></a>
    <a href="https://github.com/AsBuiltReport/AsBuiltReport.Fortinet.FortiGate/graphs/contributors" alt="GitHub Contributors">
        <img src="https://img.shields.io/github/contributors/AsBuiltReport/AsBuiltReport.Fortinet.FortiGate.svg"/></a>
</p>
<p align="center">
    <a href="https://twitter.com/AsBuiltReport" alt="Twitter">
            <img src="https://img.shields.io/twitter/follow/AsBuiltReport.svg?style=social"/></a>
</p>
<!-- ********** DO NOT EDIT THESE LINKS ********** -->

# Fortinet FortiGate As Built Report

Fortinet FortiGate As Built Report is a PowerShell module which works in conjunction with [AsBuiltReport.Core](https://github.com/AsBuiltReport/AsBuiltReport.Core).

[AsBuiltReport](https://github.com/AsBuiltReport/AsBuiltReport) is an open-sourced community project which utilises PowerShell to produce as-built documentation in multiple document formats for multiple vendors and technologies.

Please refer to the AsBuiltReport [website](https://www.asbuiltreport.com) for more detailed information about this project.

# :books: Sample Reports

## Sample Report

Sample FortiGate Fortinet As Built report HTML file: [Sample Fortinet FortiGate As-Built Report.html](https://htmlpreview.github.io/?https://raw.githubusercontent.com/AsBuiltReport/AsBuiltReport.Fortinet.FortiGate/dev/Samples/Fortinet%20FortiGate%20As%20Built%20Report.html)

Sample FortiGate Fortinet As Built report Word file: [Sample Fortinet FortiGate As-Built Report.docx](https://raw.githubusercontent.com/AsBuiltReport/AsBuiltReport.Fortinet.FortiGate/dev/Samples/Fortinet%20FortiGate%20As%20Built%20Report.txt)

# :beginner: Getting Started
Below are the instructions on how to install, configure and generate a Fortinet FortiGate As Built report.

## :floppy_disk: Supported Versions
<!-- ********** Update supported FortiGate versions ********** -->
The Fortinet FortiGate As Built Report supports the following FortiGate versions;

### PowerShell
This report is compatible with the following PowerShell versions;

<!-- ********** Update supported PowerShell versions ********** -->
| Windows PowerShell 5.1 |     PowerShell 7    |
|:----------------------:|:--------------------:|
|   :white_check_mark:   | :white_check_mark: |
## :wrench: System Requirements
<!-- ********** Update system requirements ********** -->
PowerShell 5.1 or PowerShell 7, and the following PowerShell modules are required for generating a Fortinet FortiGate As Built Report.

- [AsBuiltReport.Fortinet.FortiGate Module](https://www.powershellgallery.com/packages/AsBuiltReport.Fortinet.FortiGate/)
- [PowerFGT Module](https://www.powershellgallery.com/packages/PowerFGT/)

### Linux & macOS
* .NET Core is required for cover page image support on Linux and macOS operating systems.
    * [Installing .NET Core for macOS](https://docs.microsoft.com/en-us/dotnet/core/install/macos)
    * [Installing .NET Core for Linux](https://docs.microsoft.com/en-us/dotnet/core/install/linux)

❗ If you are unable to install .NET Core, you must set `ShowCoverPageImage` to `False` in the report JSON configuration file.
### :closed_lock_with_key: Required Privileges
You need to have an account (user/password) with only Read Only on the FortiGate

The use of an API Token in not currently supported.

## :package: Module Installation

### PowerShell
```powershell
Install-Module PowerFGT
Install-Module AsBuiltReport.Fortinet.FortiGate
```

### GitHub
If you are unable to use the PowerShell Gallery, you can still install the module manually. Ensure you repeat the following steps for the [system requirements](https://github.com/AsBuiltReport/AsBuiltReport.Fortinet.FortiGate#wrench-system-requirements) also.

1. Download the code package / [latest release](https://github.com/AsBuiltReport/AsBuiltReport.Fortinet.FortiGate/releases/latest) zip from GitHub
2. Extract the zip file
3. Copy the folder `AsBuiltReport.Fortinet.FortiGate` to a path that is set in `$env:PSModulePath`.
4. Open a PowerShell terminal window and unblock the downloaded files with
    ```powershell
    $path = (Get-Module -Name AsBuiltReport.Fortinet.FortiGate -ListAvailable).ModuleBase; Unblock-File -Path $path\*.psd1; Unblock-File -Path $path\Src\Public\*.ps1; Unblock-File -Path $path\Src\Private\*.ps1
    ```
5. Close and reopen the PowerShell terminal window.

_Note: You are not limited to installing the module to those example paths, you can add a new entry to the environment variable PSModulePath if you want to use another path._

## :pencil2: Configuration

The Fortinet FortiGate As Built Report utilises a JSON file to allow configuration of report information, options, detail and healthchecks.

A Fortinet FortiGate report configuration file can be generated by executing the following command;
```powershell
New-AsBuiltReportConfig -Report Fortinet.FortiGate -FolderPath <User specified folder> -Filename <Optional>
```

Executing this command will copy the default Fortinet FortiGate report JSON configuration to a user specified folder.

All report settings can then be configured via the JSON file.

The following provides information of how to configure each schema within the report's JSON file.

<!-- ********** DO NOT CHANGE THE REPORT SCHEMA SETTINGS ********** -->
### Report
The **Report** schema provides configuration of the Fortinet FortiGate report information.

| Sub-Schema          | Setting      | Default                        | Description                                                  |
|---------------------|--------------|--------------------------------|--------------------------------------------------------------|
| Name                | User defined | Fortinet FortiGate As Built Report | The name of the As Built Report                              |
| Version             | User defined | 1.0                            | The report version                                           |
| Status              | User defined | Released                       | The report release status                                    |
| ShowCoverPageImage  | true / false | true                           | Toggle to enable/disable the display of the cover page image |
| ShowTableOfContents | true / false | true                           | Toggle to enable/disable table of contents                   |
| ShowHeaderFooter    | true / false | true                           | Toggle to enable/disable document headers & footers          |
| ShowTableCaptions   | true / false | true                           | Toggle to enable/disable table captions/numbering            |

### Options
The **Options** schema allows certain options within the report to be toggled on or off.

<!-- ********** Add/Remove the number of InfoLevels as required ********** -->
### InfoLevel
The **InfoLevel** schema allows configuration of each section of the report at a granular level. The following sections can be set.

There are 4 levels (0-3) of detail granularity for each section as follows;

| Setting | InfoLevel         | Description                                                                                                                                |
|:-------:|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------|
|    0    | Disabled          | Does not collect or display any information                                                                                                |
|    1    | Enabled / Summary | Provides summarised information for a collection of objects                                                                                |
|    2    | Adv Summary       | Provides condensed, detailed information for a collection of objects                                                                       |
|    3    | Detailed          | Provides detailed information for individual objects                                                                                       |

The table below outlines the default and maximum InfoLevel settings for each *Forticare* section.

| Sub-Schema | Default Settings | Maximum Settings |
|:----------:|------------------|------------------|
| Status     | 1                | 1                |
| Firmware   | 1                | 1                |

The table below outlines the default and maximum InfoLevel settings for each *System* section.

| Sub-Schema | Default Settings | Maximum Settings |
|:----------:|------------------|------------------|
| Global     | 1                | 1                |
| Settings   | 1                | 1                |
| GUI        | 1                | 1                |
| DNS        | 1                | 1                |
| DNSServer  | 1                | 1                |
| Admin      | 1                | 1                |
| GUI        | 1                | 1                |
| Interface  | 1                | 1                |

The table below outlines the default and maximum InfoLevel settings for each *Route* section.

| Sub-Schema | Default Settings | Maximum Settings |
|:----------:|------------------|------------------|
| Summary    | 1                | 1                |
| Monitor    | 1                | 1                |
| Static     | 1                | 1                |
| Policy     | 1                | 1                |


The table below outlines the default and maximum InfoLevel settings for each *Firewall* section.

| Sub-Schema | Default Settings | Maximum Settings |
|:----------:|------------------|------------------|
| Summary    | 1                | 1                |
| Address    | 1                | 1                |
| Group      | 1                | 1                |
| IPPool     | 1                | 1                |
| VIP        | 1                | 1                |
| Policy     | 1                | 1                |

The table below outlines the default and maximum InfoLevel settings for each *User* section.

| Sub-Schema | Default Settings | Maximum Settings |
|:----------:|------------------|------------------|
| Summary    | 1                | 1                |
| Local      | 1                | 1                |
| Group      | 1                | 1                |
| LDAP       | 1                | 1                |
| RADIUS     | 1                | 1                |
| Policy     | 1                | 1                |


### Healthcheck
The **Healthcheck** schema is used to toggle health checks on or off.

Health checks are yet to be developed.

## :computer: Examples
There are a few examples listed below on running the AsBuiltReport script against a FortiGate. Refer to the README.md file in the main AsBuiltReport project repository for more examples.

```powershell
# Generate a Fortinet FortiGate As Built Report for FortiGate fortigate.fortidemo.com using specified credentials. Export report to HTML & DOCX formats. Use default report style. Append timestamp to report filename. Save reports to 'C:\Users\PowerFGT\Documents'
PS C:\> New-AsBuiltReport -Report Fortinet.FortiGate -Target fortigate.fortidemo.com -Username demo -Password demo -Format Html,Word -OutputFolderPath 'C:\Users\PowerFGT\Documents' -Timestamp

# Generate a Fortinet FortiGate As Built Report for FortiGate fortigate.fortidemo.com using specified credentials and report configuration file. Export report to Text, HTML & DOCX formats. Use default report style. Save reports to 'C:\Users\PowerFGT\Documents'. Display verbose messages to the console.
PS C:\>  New-AsBuiltReport -Report Fortinet.FortiGate -Target fortigate.fortidemo.com -Username demo -Password 'demo' -Format Text,Html,Word -OutputFolderPath 'C:\Users\PowerFGT\Documents' -ReportConfigFilePath 'C:\Users\Jon\AsBuiltReport\AsBuiltReport.Fortinet.FortiGate.json' -Verbose

# Generate a Fortinet FortiGate As Built Report for FortiGate fortigate.fortidemo.com using stored credentials. Export report to HTML & Text formats. Use default report style. Highlight environment issues within the report. Save reports to 'C:\Users\PowerFGT\Documents'.
PS C:\> $Creds = Get-Credential
PS C:\>  New-AsBuiltReport -Report Fortinet.FortiGate -Target fortigate.fortidemo.com -Credential $Creds -Format Html,Text -OutputFolderPath 'C:\Users\PowerFGT\Documents' -EnableHealthCheck

# Generate a Fortinet FortiGate As Built Report for FortiGate fortigate.fortidemo.com using stored credentials. Export report to HTML & DOCX formats. Use default report style. Reports are saved to the user profile folder by default. Attach and send reports via e-mail.
PS C:\>  New-AsBuiltReport -Report Fortinet.FortiGate -Target fortigate.fortidemo.com-Username demo -Password 'demo' -Format Html,Word -OutputFolderPath 'C:\Users\PowerFGT\Documents' -SendEmail
```
