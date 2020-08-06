---
title: Reporting Services in SQL Server Management Studio (SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report servers [Reporting Services], how-to topics
ms.assetid: 60685458-9108-47bf-820a-5e7db454d408
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3f4083d8b288c8816925723f4cfaef4342dd0298
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721043"
---
# <a name="reporting-services-in-sql-server-management-studio-ssrs"></a><span data-ttu-id="d94bd-102">Reporting Services in SQL Server Management Studio (SSRS)</span><span class="sxs-lookup"><span data-stu-id="d94bd-102">Reporting Services in SQL Server Management Studio (SSRS)</span></span>
  <span data-ttu-id="d94bd-103">Berichtsserveradministratoren können [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] für folgende Aufgaben verwenden:</span><span class="sxs-lookup"><span data-stu-id="d94bd-103">Report server administrators can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to:</span></span>  
  
-   <span data-ttu-id="d94bd-104">Aktivieren Sie Funktionen, legen Sie Serverstandards fest, und verwalten Sie ausgeführte Aufträge.</span><span class="sxs-lookup"><span data-stu-id="d94bd-104">Enable features, set server defaults, and manage running jobs.</span></span>  
  
-   <span data-ttu-id="d94bd-105">Zeigen Sie benutzerdefinierte Berichte an, oder erstellen Sie diese.</span><span class="sxs-lookup"><span data-stu-id="d94bd-105">View and create custom reports.</span></span> <span data-ttu-id="d94bd-106">im Objekt-Explorer wird für viele Knoten ein Satz von Standardberichten angezeigt, die mit [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]installiert werden.</span><span class="sxs-lookup"><span data-stu-id="d94bd-106">In Object Explorer, many nodes display a set of standard reports that are installed with [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="d94bd-107">Sie benötigen Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="d94bd-107">You must have administrator permissions.</span></span> <span data-ttu-id="d94bd-108">Das Schema eines benutzerdefinierten Berichts muss mit dem Schema der installierten Berichte übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d94bd-108">The schema of a custom report must match the schema of the installed reports.</span></span> <span data-ttu-id="d94bd-109">Weitere Informationen finden Sie unter [Benutzerdefinierte Berichte in Management Studio](../../ssms/object/custom-reports-in-management-studio.md) und [Suchen der Berichtsdefinitions-Schemaversion (SSRS)](../reports/find-the-report-definition-schema-version-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="d94bd-109">For more information, see [Custom Reports in Management Studio](../../ssms/object/custom-reports-in-management-studio.md) and [Find the Report Definition Schema Version &#40;SSRS&#41;](../reports/find-the-report-definition-schema-version-ssrs.md).</span></span>  
  
 <span data-ttu-id="d94bd-110">Berichtsautoren können [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] für folgende Aufgaben verwenden:</span><span class="sxs-lookup"><span data-stu-id="d94bd-110">Report authors can use [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] to:</span></span>  
  
-   <span data-ttu-id="d94bd-111">Stellen Sie räumliche Daten aus einem Abfrageresultset für einen Kartenbericht visuell dar.</span><span class="sxs-lookup"><span data-stu-id="d94bd-111">Visualize spatial data from a query result set for a map report.</span></span> <span data-ttu-id="d94bd-112">Verwenden Sie nach dem Ausführen der Abfrage die Registerkarte **Räumliche Ergebnisse** im Resultsetbereich.</span><span class="sxs-lookup"><span data-stu-id="d94bd-112">After you run the query, use the **Spatial results** tab in the result set pane.</span></span> <span data-ttu-id="d94bd-113">Weitere Informationen finden Sie unter [View Spatial Data in Object Explorer](../../relational-databases/scripting/view-spatial-data-in-object-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="d94bd-113">For more information, see [View Spatial Data in Object Explorer](../../relational-databases/scripting/view-spatial-data-in-object-explorer.md).</span></span>  
  
 <span data-ttu-id="d94bd-114">Dieser Abschnitt enthält ausführliche Anweisungen zum Ausführen verschiedener berichtsspezifischer Aufgaben in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d94bd-114">This section contains step-by-step instructions for performing various reporting tasks using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span> <span data-ttu-id="d94bd-115">Die Erstellung und Verwaltung freigegebener Zeitpläne kann auch mit dem Berichts-Manager erfolgen.</span><span class="sxs-lookup"><span data-stu-id="d94bd-115">Creating and managing shared schedules can also be performed using Report Manager.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d94bd-116">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d94bd-116">In This Section</span></span>  
  
-   [<span data-ttu-id="d94bd-117">Vorgehensweise: Herstellen einer Verbindung mit einem Berichtsserver in Management Studio</span><span class="sxs-lookup"><span data-stu-id="d94bd-117">Connect to a Report Server in Management Studio</span></span>](connect-to-a-report-server-in-management-studio.md)  
  
-   [<span data-ttu-id="d94bd-118">Festlegen von Berichtsservereigenschaften &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d94bd-118">Set Report Server Properties &#40;Management Studio&#41;</span></span>](set-report-server-properties-management-studio.md)  
  
-   [<span data-ttu-id="d94bd-119">Erstellen, Löschen oder Ändern einer Rolle &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d94bd-119">Create, Delete, or Modify a Role &#40;Management Studio&#41;</span></span>](../security/role-definitions-create-delete-or-modify.md)  
  
-   [<span data-ttu-id="d94bd-120">Löschen eines Elements &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d94bd-120">Delete an Item &#40;Management Studio&#41;</span></span>](delete-an-item-management-studio.md)  
  
-   [<span data-ttu-id="d94bd-121">Berichtsserveraufträge abbrechen &#40;Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="d94bd-121">Cancel Report Server Jobs &#40;Management Studio&#41;</span></span>](cancel-report-server-jobs-management-studio.md)  
  
## <a name="see-also"></a><span data-ttu-id="d94bd-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d94bd-122">See Also</span></span>  
 <span data-ttu-id="d94bd-123">[Berichts Server in Management Studio F1-Hilfe](report-server-in-management-studio-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="d94bd-123">[Report Server in Management Studio F1 Help](report-server-in-management-studio-f1-help.md) </span></span>  
 [<span data-ttu-id="d94bd-124">Einführung in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d94bd-124">Introducing SQL Server Management Studio</span></span>](../../ssms/sql-server-management-studio-ssms.md)  
  
  
