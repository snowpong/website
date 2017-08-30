---
layout: docs
title: Troubleshooting AppVeyor Enterprise
---

# Troubleshooting AppVeyor Enterprise

During installation AppVeyor uses randomly-generated values for security keys, account passwords and other sensitive values. All these values as well as other installer data such as AppVeyor roles and versions installed can be found under this registry key:

    HKEY_LOCAL_MACHINE\SOFTWARE\Appveyor\Install

When something goes wrong:

* If build real-time log stops working there might be a transient issue with SignalR. Do F5 in browser to restart SignalR connection.
* Restart IIS and/or `Appveyor.Worker` and/or `Appveyor.BuildAgent` services.
* Nothing helps - [report the issue](/support/) to AppVeyor team. While reporting the issue look into these places for possible errors/warning:
    * Web browser's "Developer tools" - for any JavaScript-related errors.
    * `AppVeyor` event log in Event Viewer under `Applications and Services Logs\AppVeyor`. Web, Worker and Build Agent roles write logs there.