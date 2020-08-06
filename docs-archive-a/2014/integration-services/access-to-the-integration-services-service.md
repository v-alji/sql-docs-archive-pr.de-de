---
title: Zugriff auf den Integration Services-Dienst | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SSIS packages, security
- viewing packages while running
- displaying packacges while running
- security [Integration Services], running packages
- packages [Integration Services], security
- current packages running
- Integration Services packages, security
- SQL Server Integration Services packages, security
ms.assetid: 1088aafc-14c5-4e7d-9930-606a24c3049b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7dd6fbed4bedc285069306ab4c400f0f67f9f293
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610025"
---
# <a name="access-to-the-integration-services-service"></a><span data-ttu-id="20b95-102">Zugriff auf den Integration Services-Dienst</span><span class="sxs-lookup"><span data-stu-id="20b95-102">Access to the Integration Services Service</span></span>
  <span data-ttu-id="20b95-103">Über Paketschutzebenen kann gesteuert werden, wer ein Paket bearbeiten und ausführen darf.</span><span class="sxs-lookup"><span data-stu-id="20b95-103">Package protection levels can limit who is allowed to edit and execute a package.</span></span> <span data-ttu-id="20b95-104">Zusätzlicher Schutz ist erforderlich, um die Anzahl der Personen einzuschränken, die die Liste der derzeit auf einem Server ausgeführten Pakete anzeigen und die Paketausführung in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]beenden dürfen.</span><span class="sxs-lookup"><span data-stu-id="20b95-104">Additional protection is needed to limit who can view the list of packages currently running on a server and who can stop currently executing packages in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
 [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] <span data-ttu-id="20b95-105">wird der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Dienst zum Auflisten der ausgeführten Pakete verwendet.</span><span class="sxs-lookup"><span data-stu-id="20b95-105">uses the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service to list running packages.</span></span> <span data-ttu-id="20b95-106">Mitglieder der Gruppe der Windows-Administratoren können alle aktuell ausgeführten Pakete anzeigen und ihre Ausführung beenden.</span><span class="sxs-lookup"><span data-stu-id="20b95-106">Members of the Windows Administrators group can view and stop all currently running packages.</span></span> <span data-ttu-id="20b95-107">Benutzer, die nicht zur Administratoren-Gruppe gehören, können nur solche ausgeführten Pakete anzeigen und deren Ausführung beenden, wenn sie selbst die Ausführung gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="20b95-107">Users who are not members of the Administrators group can view and stop only packages that they started.</span></span>  
  
 <span data-ttu-id="20b95-108">Es ist wichtig, den Zugriff auf Computer einzuschränken, auf denen ein [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Dienst ausgeführt wird. Dies gilt besonders für einen [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Dienst, der Remoteordner auflisten kann.</span><span class="sxs-lookup"><span data-stu-id="20b95-108">It is important to restrict access to computers that run an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service, especially an [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] service that can enumerate remote folders.</span></span> <span data-ttu-id="20b95-109">Jeder authentifizierte Benutzer kann die Auflistung von Paketen anfordern.</span><span class="sxs-lookup"><span data-stu-id="20b95-109">Any authenticated user can request the enumeration of packages.</span></span> <span data-ttu-id="20b95-110">Auch wenn der Dienst den Dienst nicht findet, listet der Dienst Ordner auf.</span><span class="sxs-lookup"><span data-stu-id="20b95-110">Even if the service doesn not find the service, the service enumerates folders.</span></span> <span data-ttu-id="20b95-111">Diese Ordnernamen können für böswillige Benutzer von Nutzen sein.</span><span class="sxs-lookup"><span data-stu-id="20b95-111">These folder names may be useful to a malicious user.</span></span> <span data-ttu-id="20b95-112">Wenn ein Administrator den Dienst so konfiguriert hat, dass Ordner auf einem Remotecomputer aufgelistet werden, können die Benutzer auch Ordnernamen anzeigen, die sie normalerweise nicht anzeigen könnten.</span><span class="sxs-lookup"><span data-stu-id="20b95-112">If an administrator has configured the service to enumerate folders on a remote machine, users may also be able to see folder names that they would normally not be able to see.</span></span>  
  
  
