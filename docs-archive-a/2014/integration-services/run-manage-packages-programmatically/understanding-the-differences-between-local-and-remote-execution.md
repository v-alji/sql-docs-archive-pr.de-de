---
title: Grundlegendes zu den Unterschieden zwischen der lokalen und der Remoteausführung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Integration Services packages, running
- packages [Integration Services], running
- packages [Integration Services], troubleshooting
ms.assetid: 610ee7d9-4fea-4aba-9395-57add826923b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 399584c790f4c5a5dd136121c58a5ff7743f4969
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698444"
---
# <a name="understanding-the-differences-between-local-and-remote-execution"></a><span data-ttu-id="84895-102">Grundlegendes zu den Unterschieden zwischen der lokalen und der Remoteausführung</span><span class="sxs-lookup"><span data-stu-id="84895-102">Understanding the Differences between Local and Remote Execution</span></span>
  <span data-ttu-id="84895-103">Paketentwickler und Administratoren sollten die Beschränkungen hinsichtlich des Ausführungsorts eines [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Pakets beachten.</span><span class="sxs-lookup"><span data-stu-id="84895-103">Package developers and administrators should be aware that there are restrictions related to where an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package runs.</span></span>  
  
-   <span data-ttu-id="84895-104">**Ein Paket wird auf dem gleichen Computer ausgeführt wie das Programm, das es startet**.</span><span class="sxs-lookup"><span data-stu-id="84895-104">**A package runs on the same computer as the program that launches it**.</span></span> <span data-ttu-id="84895-105">Auch wenn ein Progamm ein Paket lädt, das auf einem anderen Server remote gespeichert ist, wird das Paket auf dem lokalen Computer ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="84895-105">Even when a program loads a package that is stored remotely on another server, the package runs on the local computer.</span></span>  
  
-   <span data-ttu-id="84895-106">**Sie können ein Paket außerhalb der Entwicklungsumgebung nur auf Computern ausführen, auf denen Integration Services installiert ist**.</span><span class="sxs-lookup"><span data-stu-id="84895-106">**You can only run a package outside the development environment on a computer that has Integration Services installed**.</span></span> <span data-ttu-id="84895-107">Sie können Pakete außerhalb von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] nur auf Clientcomputern ausführen, auf denen [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installiert ist, wobei die Bedingungen Ihrer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Lizenz möglicherweise die Installation von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] auf weiteren Computern nicht zulassen.</span><span class="sxs-lookup"><span data-stu-id="84895-107">You cannot run packages outside of [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] on a client computer that does not have [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] installed, and the terms of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] licensing may not permit you to install [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] on additional computers.</span></span> <span data-ttu-id="84895-108">Bei [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] handelt es sich um eine Serverkomponente, die nicht an Clientcomputer weitergegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="84895-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] is a server component and is not redistributable to client computers.</span></span> <span data-ttu-id="84895-109">Um Pakete von einem Clientcomputer aus auszuführen, müssen Sie diese so starten, dass die Ausführung auf dem Server sichergestellt ist.</span><span class="sxs-lookup"><span data-stu-id="84895-109">To run packages from a client computer, you need to launch them in a manner that ensures that the packages run on the server.</span></span>  
  
 <span data-ttu-id="84895-110">Weitere Informationen zum Laden und Ausführen eines gespeicherten Pakets finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="84895-110">For more information about loading and running a saved package, see:</span></span>  
  
-   [<span data-ttu-id="84895-111">Programmgesteuertes Laden und Ausführen eines lokalen Pakets</span><span class="sxs-lookup"><span data-stu-id="84895-111">Loading and Running a Local Package Programmatically</span></span>](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md)  
  
-   [<span data-ttu-id="84895-112">Programmgesteuertes Laden und Ausführen eines Remotepakets</span><span class="sxs-lookup"><span data-stu-id="84895-112">Loading and Running a Remote Package Programmatically</span></span>](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md)  
  
 <span data-ttu-id="84895-113">Weitere Informationen zum Ausführen eines Pakets und Laden von dessen Ausgabe in ein benutzerdefiniertes Programm finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="84895-113">For more information about running a package and loading its output into a custom program, see:</span></span>  
  
-   [<span data-ttu-id="84895-114">Laden der Ausgabe eines lokalen Pakets</span><span class="sxs-lookup"><span data-stu-id="84895-114">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
<span data-ttu-id="84895-115">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="84895-115">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="84895-116">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="84895-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="84895-117">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="84895-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="84895-118">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="84895-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84895-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="84895-119">See Also</span></span>  
 <span data-ttu-id="84895-120">[Programm gesteuertes laden und Ausführen eines lokalen Pakets](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="84895-120">[Loading and Running a Local Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-local-package-programmatically.md) </span></span>  
 <span data-ttu-id="84895-121">[Programm gesteuertes laden und Ausführen eines Remote Pakets](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span><span class="sxs-lookup"><span data-stu-id="84895-121">[Loading and Running a Remote Package Programmatically](../run-manage-packages-programmatically/loading-and-running-a-remote-package-programmatically.md) </span></span>  
 [<span data-ttu-id="84895-122">Laden der Ausgabe eines lokalen Pakets</span><span class="sxs-lookup"><span data-stu-id="84895-122">Loading the Output of a Local Package</span></span>](../run-manage-packages-programmatically/loading-the-output-of-a-local-package.md)  
  
  
