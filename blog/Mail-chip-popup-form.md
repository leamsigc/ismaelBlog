---
title: Mailchip Post 
---

# Mailchip pop form not working

# Deployment using FAKE

<div class="alert alert-info">
    <h5>INFO</h5>
    <p>Fake.Deploy is no longer part of FAKE 5 and is considered obsolete and fully replaced by modern deployment systems (puppet, chef, PowerShell DSC, ...). <a href"https://github.com/fsharp/FAKE/issues/1820">Announcement</a>
    You can still use fake scripts on those alternative deployment systems. Just download the fake binaries and run your scripts.</p>
</div>

This introduction assumes Fake.Deploy.exe is available in the current directory or path.

## Introduction

The FAKE deployment tool allows users to deploy applications to remote computers and to run scripts on these remote agents. A typical scenario maybe as follows:


* Build an application -> run tests -> create artifacts and save on build server (Classical FAKE build workflow)
* Extract artifacts from build server and create a NuGet deployment package
* Push the NuGet package to the desired computer this will run the package's FAKE script on the remote machine

## Installing Fake deployment services

In order to deploy application to a remote computer a deployment agent needs to be running on that server.

The simplest way to install the agent on a remote server is to use the [Nuget command line tool](http://docs.nuget.org/consume/installing-nuget) to download the FAKE nuget and extract the binaries into a _fake/tools_ subfolder.  Once  _nuget.exe_ is available on the path, use the following command in a command shell:

    [lang=batchfile]
    nuGet.exe Install FAKE -ExcludeVersion

Adding the _.../fake/tools_ folder to the path will simplify executing the Fake.Deploy.exe.

To run an agent in a console, simply run:

    Fake.Deploy

To install a windows service on that agent:

   * Open a command prompt with Administrator Privilege
   * Run Fake.Deploy /install

By default the service starts a listener on port 8080. This can however be configured by editing the Fake.Deploy.exe.config file
and changing

    <add key="ServerName" value="localhost" />
    <add key="Port" value="8080" />

to the desired value. If you use the asterisk as port no. then Fake.Deploy will assign the first open port behind of 8080.

To ensure the service is running you can navigate to http://{computer}:{port}/fake/ and you should be presented with a page giving the
status if the service

## Uninstalling Fake deployment services