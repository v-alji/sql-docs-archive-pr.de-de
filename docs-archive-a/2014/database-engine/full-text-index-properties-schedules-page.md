---
title: Voll Text Index-Eigenschaften (Seite "Zeitpläne") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: search
ms.topic: conceptual
f1_keywords:
- sql12.swb.fulltextsearch.fulltextindexproperties.schedule.f1
ms.assetid: a828e284-097e-4854-8c49-931934eb73bf
author: rothja
ms.author: jroth
ms.openlocfilehash: f49fb37295f0b3eb2f1a2dd04d44ab86236f109a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622838"
---
# <a name="full-text-index-properties-schedules-page"></a><span data-ttu-id="5549e-102">Volltextindex-Eigenschaften (Seite "Zeitpläne")</span><span class="sxs-lookup"><span data-stu-id="5549e-102">Full-Text Index Properties (Schedules Page)</span></span>
  <span data-ttu-id="5549e-103">Auf dieser Seite können Sie Zeitpläne zum Ausführen eines SQL Server-Agent-Auftrags anzeigen und erstellen, mit dem eine inkrementelle Auffüllung von Aktualisierungen für die Basistabelle des Volltextindexes gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="5549e-103">Use this page to view and create schedules for running a SQL Server Agent job that starts an incremental population of updates to the base table of the full-text index.</span></span> <span data-ttu-id="5549e-104">Wenn die Basistabelle oder Sicht keine Spalte für den Datentyp `timestamp` enthält, wird eine vollständige Auffüllung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5549e-104">If the base table or view does not contain a column of the `timestamp` data type, a full population is performed.</span></span>  
  
 <span data-ttu-id="5549e-105">**So zeigen Sie die Eigenschaften eines Volltextindexes an oder ändern diese**</span><span class="sxs-lookup"><span data-stu-id="5549e-105">**To view or change the properties of a full-text index**</span></span>  
  
-   [<span data-ttu-id="5549e-106">Verwalten von Volltextindizes</span><span class="sxs-lookup"><span data-stu-id="5549e-106">Manage Full-Text Indexes</span></span>](../relational-databases/indexes/indexes.md)  
  
## <a name="ui-element-list"></a><span data-ttu-id="5549e-107">Liste der Benutzeroberflächenelemente</span><span class="sxs-lookup"><span data-stu-id="5549e-107">UI element list</span></span>  
 <span data-ttu-id="5549e-108">**Zeitpläne**</span><span class="sxs-lookup"><span data-stu-id="5549e-108">**Schedules**</span></span>  
 <span data-ttu-id="5549e-109">Führt ggf. jede geplante inkrementelle Auffüllung in der Basistabelle für den Volltextindex auf.</span><span class="sxs-lookup"><span data-stu-id="5549e-109">Lists each scheduled incremental population, if any, on the base table for the full-text index.</span></span>  
  
 <span data-ttu-id="5549e-110">**Name**</span><span class="sxs-lookup"><span data-stu-id="5549e-110">**Name**</span></span>  
 <span data-ttu-id="5549e-111">Zeigt die Namen der einzelnen geplanten Auffüllungen an.</span><span class="sxs-lookup"><span data-stu-id="5549e-111">Displays the name of the each scheduled population.</span></span>  
  
 <span data-ttu-id="5549e-112">**Auffüllungstyp**</span><span class="sxs-lookup"><span data-stu-id="5549e-112">**Population Type**</span></span>  
 <span data-ttu-id="5549e-113">Zeigt die Typen der einzelnen geplanten Auffüllungen an.</span><span class="sxs-lookup"><span data-stu-id="5549e-113">Displays the type of each scheduled population.</span></span>  
  
 <span data-ttu-id="5549e-114">**Aktiviert**</span><span class="sxs-lookup"><span data-stu-id="5549e-114">**Enabled**</span></span>  
 <span data-ttu-id="5549e-115">Gibt an, ob die geplante Auffüllung derzeit aktiviert oder deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="5549e-115">Indicates whether the scheduled population is currently enabled or disabled.</span></span>  
  
 <span data-ttu-id="5549e-116">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="5549e-116">**Description**</span></span>  
 <span data-ttu-id="5549e-117">Zeigt die Beschreibung an, die beim Erstellen des Zeitplans  angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="5549e-117">Displays the description that was specified when the schedule was created.</span></span>  
  
 <span data-ttu-id="5549e-118">**Neu**</span><span class="sxs-lookup"><span data-stu-id="5549e-118">**New**</span></span>  
 <span data-ttu-id="5549e-119">Klicken Sie, um einen neuen Zeitplan zum Auffüllen des Volltextindexes zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5549e-119">Click to create a new schedule for populating the full-text index.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5549e-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5549e-120">See Also</span></span>  
 <span data-ttu-id="5549e-121">[Verwenden des Volltextindizierungs-Assistenten](../relational-databases/search/use-the-full-text-indexing-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="5549e-121">[Use the Full-Text Indexing Wizard](../relational-databases/search/use-the-full-text-indexing-wizard.md) </span></span>  
 [<span data-ttu-id="5549e-122">Auffüllen von Volltextindizes</span><span class="sxs-lookup"><span data-stu-id="5549e-122">Populate Full-Text Indexes</span></span>](../relational-databases/search/populate-full-text-indexes.md)  
  
  
