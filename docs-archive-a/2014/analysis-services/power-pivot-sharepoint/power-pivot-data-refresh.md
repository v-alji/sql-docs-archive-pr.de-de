---
title: Power Pivot-Datenaktualisierung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- unattended data refresh [Analysis Services with SharePoint]
- scheduled data refresh [Analysis Services with SharePoint]
- data refresh [Analysis Services with SharePoint]
ms.assetid: ac8358a3-ee71-44c7-8ee6-ac7afe3ebaa4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6f7d5ed5c2f8882cbc0c47a1c711748d26e0193c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618329"
---
# <a name="powerpivot-data-refresh"></a><span data-ttu-id="d6a97-102">PowerPivot-Datenaktualisierung</span><span class="sxs-lookup"><span data-stu-id="d6a97-102">PowerPivot Data Refresh</span></span>
  <span data-ttu-id="d6a97-103">Nachdem Sie eine Arbeitsmappe mit PowerPivot-Daten erstellt haben, können Sie die Daten in regelmäßigen Abständen aktualisieren, indem Sie eine Abfrage oder einen Befehl wiederholt ausführen, um aktualisierte Informationen aus den Quellen abzurufen, die ursprünglich zum Erstellen der Arbeitsmappe verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="d6a97-103">After you create a workbook that contains PowerPivot data, you might want to periodically refresh the data by rerunning a query or command to get updated information from the sources you used originally to create the workbook.</span></span> <span data-ttu-id="d6a97-104">Dieses Verfahren wird als `data refresh` bezeichnet. Sie können Daten bedarfsgesteuert in [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)] oder in einem geplanten Vorgang aktualisieren, der als [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Prozess auf einem Anwendungsserver in einer SharePoint-Farm ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d6a97-104">This process is called `data refresh`, and you can refresh data on demand in [!INCLUDE[ssGeminiClient](../../includes/ssgeminiclient-md.md)], or as a scheduled operation that runs as an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] process on an application server in a SharePoint farm.</span></span> <span data-ttu-id="d6a97-105">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="d6a97-105">For more information, see:</span></span>  
  
-   [<span data-ttu-id="d6a97-106">PowerPivot-Datenaktualisierung mit SharePoint 2010</span><span class="sxs-lookup"><span data-stu-id="d6a97-106">PowerPivot Data Refresh with SharePoint 2010</span></span>](../powerpivot-data-refresh-with-sharepoint-2010.md)  
  
-   [<span data-ttu-id="d6a97-107">Konfigurieren Sie das unbeaufsichtigte Daten Aktualisierungs Konto für Power Pivot &#40;PowerPivot für SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="d6a97-107">Configure the PowerPivot Unattended Data Refresh Account &#40;PowerPivot for SharePoint&#41;</span></span>](../configure-unattended-data-refresh-account-powerpivot-sharepoint.md)  
  
-   [<span data-ttu-id="d6a97-108">Gespeicherte Anmelde Informationen für die Power Pivot-Datenaktualisierung &#40;PowerPivot für SharePoint konfigurieren&#41;</span><span class="sxs-lookup"><span data-stu-id="d6a97-108">Configure Stored Credentials for PowerPivot Data Refresh &#40;PowerPivot for SharePoint&#41;</span></span>](../configure-stored-credentials-data-refresh-powerpivot-sharepoint.md)  
  
-   [<span data-ttu-id="d6a97-109">Planen einer Datenaktualisierung &#40;PowerPivot für SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="d6a97-109">Schedule a Data Refresh &#40;PowerPivot for SharePoint&#41;</span></span>](../schedule-a-data-refresh-powerpivot-for-sharepoint.md)  
  
-   [<span data-ttu-id="d6a97-110">Anzeigen des Daten Aktualisierungs Verlaufs &#40;PowerPivot für SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="d6a97-110">View Data Refresh History &#40;PowerPivot for SharePoint&#41;</span></span>](view-data-refresh-history-power-pivot-for-sharepoint.md)  
  
> [!NOTE]
>  [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] <span data-ttu-id="d6a97-111">und Excel Services von SharePoint Server 2013 verwenden eine andere Architektur für die Datenaktualisierung bei PowerPivot-Datenmodellen.</span><span class="sxs-lookup"><span data-stu-id="d6a97-111">and SharePoint Server 2013 Excel Services use a different architecture for data refresh of PowerPivot data models.</span></span> <span data-ttu-id="d6a97-112">In der von SharePoint 2013 unterstützten Architektur wird Excel Services als Hauptkomponente zum Laden von PowerPivot-Datenmodellen genutzt.</span><span class="sxs-lookup"><span data-stu-id="d6a97-112">The SharePoint 2013 supported architecture utilizes Excel Services as the primary component to load PowerPivot data models.</span></span> <span data-ttu-id="d6a97-113">In der vorherigen Datenaktualisierungsarchitektur wurden Datenmodelle mithilfe eines Servers geladen, auf dem der PowerPivot-Systemdienst und [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] im SharePoint-Modus ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="d6a97-113">The previous data refresh architecture used relied on a server running PowerPivot System Service and [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] in SharePoint mode to load data models.</span></span> <span data-ttu-id="d6a97-114">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="d6a97-114">For more information, see the following:</span></span>  
> 
>  -   [<span data-ttu-id="d6a97-115">PowerPivot-Datenaktualisierung mit SharePoint 2013</span><span class="sxs-lookup"><span data-stu-id="d6a97-115">PowerPivot Data Refresh with SharePoint 2013</span></span>](power-pivot-data-refresh-with-sharepoint-2013.md)  
> -   [<span data-ttu-id="d6a97-116">Aktualisieren von Arbeitsmappen und planmäßige Datenaktualisierung &#40;SharePoint 2013&#41;</span><span class="sxs-lookup"><span data-stu-id="d6a97-116">Upgrade Workbooks and Scheduled Data Refresh &#40;SharePoint 2013&#41;</span></span>](../instances/install-windows/upgrade-workbooks-and-scheduled-data-refresh-sharepoint-2013.md)  
  
  
