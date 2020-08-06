---
title: Festlegen von Tool Optionen und Layout | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine [SQL Server], tutorials
ms.assetid: 43e97ce0-97bc-4a27-9485-5bbeb7190b85
author: stevestein
ms.author: sstein
ms.openlocfilehash: 96d853a85b8ee4d451c55d7ea59af3755887be22
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719216"
---
# <a name="setting-tool-options-and-layout"></a><span data-ttu-id="22f1e-102">Festlegen von Optionen und Layout</span><span class="sxs-lookup"><span data-stu-id="22f1e-102">Setting Tool Options and Layout</span></span>
  <span data-ttu-id="22f1e-103">Sie können Optionen festlegen, über die konfiguriert wird, welche grafische Benutzeroberfläche der Datenbankoptimierungsratgeber beim Starten anzeigt, welche Schriftart verwendet wird sowie weitere Funktionen, die Sie jeweils optimal unterstützen.</span><span class="sxs-lookup"><span data-stu-id="22f1e-103">You can set options that configure what the Database Engine Tuning Advisor graphical user interface (GUI) displays on startup, the font it uses, and other tool functionality to best support how you use it.</span></span> <span data-ttu-id="22f1e-104">Im Folgenden werden die Optionen erläutert, die Sie festlegen können, sowie ihre Verwendung.</span><span class="sxs-lookup"><span data-stu-id="22f1e-104">The practices on this page familiarize you with the options you can set, and how to set them.</span></span>  
  
### <a name="set-the-tool-options"></a><span data-ttu-id="22f1e-105">Festlegen der Tooloptionen</span><span class="sxs-lookup"><span data-stu-id="22f1e-105">Set the tool options</span></span>  
  
1.  <span data-ttu-id="22f1e-106">Starten Sie den Datenbankoptimierungsratgeber.</span><span class="sxs-lookup"><span data-stu-id="22f1e-106">Start the Database Engine Tuning Advisor.</span></span> <span data-ttu-id="22f1e-107">Zeigen Sie im Windows-Menü **Start** auf **Alle Programme**und dann nacheinander auf [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], **Leistungstools**und **Datenbankoptimierungsratgeber**.</span><span class="sxs-lookup"><span data-stu-id="22f1e-107">On the Windows **Start** menu, point to **All Programs**, point to [!INCLUDE[ssCurrentUI](../../includes/sscurrentui-md.md)], point to **Performance Tools**, and click **Database Engine Tuning Advisor**.</span></span>  
  
2.  <span data-ttu-id="22f1e-108">Klicken Sie im Menü **Extras** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="22f1e-108">On the **Tools** menu, click **Options**.</span></span>  
  
3.  <span data-ttu-id="22f1e-109">Verwenden Sie das Dialogfeld **Optionen** , um folgende Optionen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="22f1e-109">In the **Options** dialog box, view the following options:</span></span>  
  
    -   <span data-ttu-id="22f1e-110">Erweitern Sie die Liste **Beim Start** , um festzustellen, welche Anzeigemöglichkeiten der Datenbankoptimierungsratgeber beim Start bietet.</span><span class="sxs-lookup"><span data-stu-id="22f1e-110">Expand the **On startup** list to view what Database Engine Tuning Advisor can display when it is started.</span></span> <span data-ttu-id="22f1e-111">Standardmäßig ist **Neue Sitzung anzeigen** ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="22f1e-111">By default, **Show a new session** is selected.</span></span>  
  
    -   <span data-ttu-id="22f1e-112">Klicken Sie auf **Schriftart ändern** , um die Schriftarten anzuzeigen, die Sie für die Listen der Datenbanken und Tabellen auf der Registerkarte **Allgemein** auswählen können. Die Schriftarten, die Sie für diese Option auswählen, werden auch in Datenbankoptimierungsratgeber Empfehlungs Raster und-Berichten verwendet, nachdem Sie die Optimierung durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="22f1e-112">Click **Change Font** to see what fonts you can choose for the lists of databases and tables on the **General** tab. The fonts you choose for this option also are used in Database Engine Tuning Advisor recommendation grids and reports after you have performed tuning.</span></span> <span data-ttu-id="22f1e-113">Standardmäßig verwendet der Datenbankoptimierungsratgeber die Systemschriftarten.</span><span class="sxs-lookup"><span data-stu-id="22f1e-113">By default, Database Engine Tuning Advisor uses system fonts.</span></span>  
  
    -   <span data-ttu-id="22f1e-114">Für **Anzahl der Elemente in der Liste zuletzt verwendeter Objekte** kann ein Wert von **1** bis **10**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="22f1e-114">The **Number of items in most recently used lists** can be set between **1** and **10**.</span></span> <span data-ttu-id="22f1e-115">Damit wird die maximale Anzahl von Elementen in der Liste festgelegt, die angezeigt wird, wenn Sie im Menü **Datei** auf **Zuletzt geöffnete Sitzungen** oder **Zuletzt geöffnete Dateien** klicken.</span><span class="sxs-lookup"><span data-stu-id="22f1e-115">This sets the maximum number of items in the lists displayed by clicking **Recent Sessions** or **Recent Files** on the **File** menu.</span></span> <span data-ttu-id="22f1e-116">Standardmäßig ist der Wert **4**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="22f1e-116">By default, this option is set to **4**.</span></span>  
  
    -   <span data-ttu-id="22f1e-117">Wenn das Kontrollkästchen **Die letzten Optimierungsoptionen speichern** aktiviert ist, verwendet der Datenbankoptimierungsratgeber standardmäßig die Optimierungsoptionen, die Sie bei der letzten Sitzung angegeben haben, auch für die nächste Optimierungssitzung.</span><span class="sxs-lookup"><span data-stu-id="22f1e-117">When **Remember my last tuning options** is checked, by default Database Engine Tuning Advisor uses the tuning options you specified for your last tuning session for the next tuning session.</span></span> <span data-ttu-id="22f1e-118">Deaktivieren Sie das Kontrollkästchen, wenn Sie die Standardeinstellungen für den Datenbankoptimierungsratgeber verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="22f1e-118">Clear this check box to use Database Engine Tuning Advisor tuning option defaults.</span></span> <span data-ttu-id="22f1e-119">Diese Option ist standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="22f1e-119">By default, this option is selected.</span></span>  
  
    -   <span data-ttu-id="22f1e-120">Standardmäßig ist das Kontrollkästchen **Dauerhaftes Löschen von Sitzungen bestätigen** aktiviert, um ein versehentliches Löschen von Optimierungssitzungen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="22f1e-120">By default, **Ask before permanently deleting sessions** is checked to avoid accidentally deleting tuning sessions.</span></span>  
  
    -   <span data-ttu-id="22f1e-121">Standardmäßig ist **Vor dem Beenden der Sitzungsanalyse fragen** aktiviert, damit nicht eine Optimierungssitzung aus Versehen beendet wird, bevor die Analyse einer Arbeitsauslastung durch den Datenbankoptimierungsratgeber abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="22f1e-121">By default, **Ask before stopping session analysis** is checked to avoid accidentally stopping a tuning session before Database Engine Tuning Advisor has finished analyzing a workload.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="22f1e-122">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="22f1e-122">Next Lesson</span></span>  
 [<span data-ttu-id="22f1e-123">Lektion 2: Verwenden des Datenbankoptimierungsratgebers</span><span class="sxs-lookup"><span data-stu-id="22f1e-123">Lesson 2: Using Database Engine Tuning Advisor</span></span>](../../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
