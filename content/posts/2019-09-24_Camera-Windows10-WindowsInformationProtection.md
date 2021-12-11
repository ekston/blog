---
title: Windows 10 can't save pictures from the camera.
date: 2019-09-24
draft: false
---

That was the error that a user reported which eventually landed on my desk. In the project I am responsible for Intune Device Management and so the thinking was, that there must be a policy that blocks the Camera app.
There is not. But why this error then?

{{< figure library="true" src="/img/wip-camera.png" title="Error Message with WIP" lightbox="true" >}}

Let me put the error here for Google to index:

> Sorry — we weren’t able to save the photo.
> If you nee it, here’s the error code:
> 0xA00F4253<PhotoCaptureWriteFailed> (0x80070005)

So the write failed? Well that reminded me of one of the lesser known/used Security features: Windows Information Protection (WIP).
With WIP a company defines a corporate container consisting of networks, cloud ressources and applications. Within this container applications can share data. Personal applications and cloud ressources are not allowed to write into the container.
The Camera app writes to your user-picture folder. This folder is maybe to OneDrive through “Known Folder Move”. OneDrive was defined as a corporate ressource, so could it be?

When I chose a USB stick as storage location, the Camera app worked fine.
So lets define Windows Camera App as a corporate application. The process is a bit cumbersome but well documented in Microsofts documentation.
The necessary informations for the Windows Camera App are the following:

> Microsoft.WindowsCamera_8wekyb3d8bbwe
> CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US

This is just a very small nitpicky detail, but I hope it helps someone else who has this problem.