---
title: Seite Datenbanken auswählen (Assistent für neue Verfügbarkeits Gruppen-Assistent zum Hinzufügen einer Datenbank) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.adddatabasewizard.selectdatabases.f1
- sql12.swb.newagwizard.selectdatabases.f1
ms.assetid: 929c5e15-d087-438d-b1f2-aa97c5f8bff8
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c626b8f0953f18a6dd4661124a09b7f542caeb82
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724213"
---
# <a name="select-databases-page-new-availability-group-wizard-add-database-wizard"></a><span data-ttu-id="00d06-102">Seite Datenbanken auswählen (Assistent für neue Verfügbarkeits Gruppen-Assistent zum Hinzufügen einer Datenbank)</span><span class="sxs-lookup"><span data-stu-id="00d06-102">Select Databases Page (New Availability Group Wizard-Add Database Wizard)</span></span>
  <span data-ttu-id="00d06-103"> In diesem Hilfethema werden die Optionen der Seite **Datenbanken angeben** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="00d06-103">This help topic describes the options of the **Specify Databases** page.</span></span> <span data-ttu-id="00d06-104">Dieses Thema gilt für den [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] und den [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="00d06-104">This topic applies to the [!INCLUDE[ssAoNewAgWiz](../../../includes/ssaonewagwiz-md.md)] and [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
##  <a name="select-databases-options"></a><a name="PageOptions"></a> <span data-ttu-id="00d06-105">Optionen für "Datenbanken auswählen"</span><span class="sxs-lookup"><span data-stu-id="00d06-105">Select Databases Options</span></span>  
 <span data-ttu-id="00d06-106">Im Raster **Benutzerdatenbanken auf dieser SQL Server-Instanz** wird jede lokale Benutzerdatenbank aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="00d06-106">The **User databases on this instance of SQL Server** grid lists every local user database.</span></span> <span data-ttu-id="00d06-107">Es gibt folgende Spalten:</span><span class="sxs-lookup"><span data-stu-id="00d06-107">The columns are as follows:</span></span>  
  
 <span data-ttu-id="00d06-108">**Name**</span><span class="sxs-lookup"><span data-stu-id="00d06-108">**Name**</span></span>  
 <span data-ttu-id="00d06-109">Zeigt den Namen einer lokalen Benutzerdatenbank an.</span><span class="sxs-lookup"><span data-stu-id="00d06-109">Displays the name of a local user database.</span></span>  
  
 <span data-ttu-id="00d06-110">**Größe**</span><span class="sxs-lookup"><span data-stu-id="00d06-110">**Size**</span></span>  
 <span data-ttu-id="00d06-111">Zeigt die Datenbankgröße an, wenn die Größe für den Assistenten verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="00d06-111">Displays the database size, if the size is available to the wizard.</span></span>  
  
 <span data-ttu-id="00d06-112">**Status**</span><span class="sxs-lookup"><span data-stu-id="00d06-112">**Status**</span></span>  
 <span data-ttu-id="00d06-113">Zeigt einen Link an, dessen Text angibt, ob eine bestimmte Datenbank die Voraussetzungen erfüllt, um einer Verfügbarkeitsgruppe hinzugefügt zu werden.</span><span class="sxs-lookup"><span data-stu-id="00d06-113">Displays a hyperlink whose text that indicates whether a given database meets the prerequisites for being added to an availability group.</span></span> <span data-ttu-id="00d06-114">Wenn der Status "**Voraussetzungen erfüllt**" lautet, können Sie die Datenbank der Verfügbarkeitsgruppe hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="00d06-114">If the status is "**Meets prerequisites**" you can add the database to the availability group.</span></span> <span data-ttu-id="00d06-115">Wenn eine Datenbank nicht alle Voraussetzungen erfüllt, stellt der Link **Status** eine kurze Erklärung bereit, warum die Datenbank nicht geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="00d06-115">If a database does not meet all of the prerequisites, the **Status** hyperlink provides a brief explanation of why the database is ineligible.</span></span> <span data-ttu-id="00d06-116">Um weitere Informationen zu erhalten, klicken Sie auf den Link.</span><span class="sxs-lookup"><span data-stu-id="00d06-116">For more information, click the hyperlink.</span></span>  
  
 <span data-ttu-id="00d06-117">Sie können den Assistenten auf der Seite **Datenbank auswählen** belassen, während Sie eine Datenbank bearbeiten, um eine Voraussetzung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="00d06-117">You can leave the wizard on the **Select Database** page while you take action on a database to meet a prerequisite.</span></span> <span data-ttu-id="00d06-118">Wenn Sie zur Seite **Datenbanken auswählen** zurückkehren, klicken Sie auf **Aktualisieren** , um das Raster zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="00d06-118">When you return to the **Select Databases** page, click **Refresh** to update the grid.</span></span>  
  
 <span data-ttu-id="00d06-119">**Aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="00d06-119">**Refresh**</span></span>  
 <span data-ttu-id="00d06-120">Klicken Sie, um das Raster zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="00d06-120">Click to refresh the grid.</span></span> <span data-ttu-id="00d06-121">Dies ist nützlich, nachdem Sie eine Datenbank bearbeitet haben, um eine Voraussetzung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="00d06-121">This is useful after you take action on a database to meet a prerequisite.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="00d06-122">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="00d06-122">Related Tasks</span></span>  
  
-   [<span data-ttu-id="00d06-123">Verwenden des Dialogfelds Neue Verfügbarkeitsgruppe &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="00d06-123">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="00d06-124">Verwenden des Assistenten zum Hinzufügen von Datenbanken zu Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="00d06-124">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  
## <a name="see-also"></a><span data-ttu-id="00d06-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="00d06-125">See Also</span></span>  
 <span data-ttu-id="00d06-126">[Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="00d06-126">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 [<span data-ttu-id="00d06-127">Voraussetzungen, Einschränkungen und Empfehlungen für AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="00d06-127">Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](prereqs-restrictions-recommendations-always-on-availability.md)  
  
  
