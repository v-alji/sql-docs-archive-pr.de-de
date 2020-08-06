---
title: Abfrage-Generator (Berichts-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- sql12.rtp.rptdesigner.dataview.vdtquerydesigner.f1
- sql12.rtp.rptwizard.querybuilder.f1
helpviewer_keywords:
- Query Builder [Reporting Services]
ms.assetid: 1b0904ea-28c1-448e-b56c-c0fdfbc8b222
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 34369bc72fadae75afbc93eb03c0e40509dd27a4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608370"
---
# <a name="query-builder-report-wizard"></a><span data-ttu-id="6f179-102">Abfrage-Generator (Berichts-Assistent)</span><span class="sxs-lookup"><span data-stu-id="6f179-102">Query Builder (Report Wizard)</span></span>
  <span data-ttu-id="6f179-103">Mithilfe des Abfrage-Generators können Sie eine Abfrage angeben, die ein Resultset abruft, das in einem Bericht verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6f179-103">Use the Query Builder to specify a query that retrieves a result set to use in a report.</span></span> <span data-ttu-id="6f179-104">Sie können zwischen zwei Abfrage-Generatoren auswählen:</span><span class="sxs-lookup"><span data-stu-id="6f179-104">You can choose between two query builders:</span></span>  
  
-   <span data-ttu-id="6f179-105">Der textbasierte Abfrage-Generator (Standard) stellt einen einfachen Arbeitsbereich zum Angeben einer Abfrage und Anzeigen der Ergebnisse zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="6f179-105">The text-based query builder (default) provides a simple workspace for specifying a query and viewing the results.</span></span> <span data-ttu-id="6f179-106">Sie können mehrere [!INCLUDE[tsql](../includes/tsql-md.md)] -Anweisungen, Abfrage- oder Befehlssyntaxen für benutzerdefinierte Datenverarbeitungserweiterungen und Abfragen angeben, die als Ausdrücke angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="6f179-106">You can specify multiple [!INCLUDE[tsql](../includes/tsql-md.md)] statements, query or command syntax for custom data processing extensions, and queries that are specified as expressions.</span></span> <span data-ttu-id="6f179-107">Da der allgemeine Abfrage-Generator die Abfrage nicht zuvor verarbeitet und eine beliebige Abfragesyntax aufnehmen kann, handelt es sich hierbei um das standardmäßige Abfrage-Generator-Tool für den Berichts-Designer.</span><span class="sxs-lookup"><span data-stu-id="6f179-107">Because the generic query builder does not preprocess the query and can accommodate any kind of query syntax, it is the default query builder tool for Report Designer.</span></span>  
  
-   <span data-ttu-id="6f179-108">Der grafische Abfrage-Generator bietet mehr visuelle Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="6f179-108">The graphical query builder provides a richer visual experience.</span></span> <span data-ttu-id="6f179-109">Er kommt in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] und anderen Teilen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]zum Einsatz.</span><span class="sxs-lookup"><span data-stu-id="6f179-109">It is used in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] and in other parts of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6f179-110">Sie können den grafischen Abfrage-Generator verwenden, wenn Sie keine Ausdrücke oder mehrteilige SQL-Anweisungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="6f179-110">You can use the graphical query builder if you are not creating expressions or multi-part SQL statements.</span></span>  
  
     <span data-ttu-id="6f179-111">Um zum grafischen Abfrage-Generator zu wechseln, schalten Sie die Schaltfläche **Als Text bearbeiten** in der oberen linken Ecke des Fensters um.</span><span class="sxs-lookup"><span data-stu-id="6f179-111">To switch to the graphical query builder, toggle the **Edit As Text** button in the top left corner of the window.</span></span>  
  
 <span data-ttu-id="6f179-112">Sie können auch eine Abfrage aus einem anderen Bericht importieren.</span><span class="sxs-lookup"><span data-stu-id="6f179-112">You can also import a query from another report.</span></span>  
  
## <a name="query-builder-options"></a><span data-ttu-id="6f179-113">Optionen des Abfrage-Generators</span><span class="sxs-lookup"><span data-stu-id="6f179-113">Query Builder Options</span></span>  
 <span data-ttu-id="6f179-114">**Als Text bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="6f179-114">**Edit As Text**</span></span>  
 <span data-ttu-id="6f179-115">Wechselt zwischen dem textbasierten und dem grafischen Abfrage-Designer, wenn beide für die Abfrage einsetzbar sind.</span><span class="sxs-lookup"><span data-stu-id="6f179-115">Toggles between the text-based and graphical query designers, if both will work for the query.</span></span>  
  
 <span data-ttu-id="6f179-116">**Importieren**</span><span class="sxs-lookup"><span data-stu-id="6f179-116">**Import**</span></span>  
 <span data-ttu-id="6f179-117">Öffnet das Dialogfeld **Abfrage importieren** und zeigt RDL- und SQL-Dateien für jeden verfügbaren Bericht an.</span><span class="sxs-lookup"><span data-stu-id="6f179-117">Opens the **Import Query** dialog box and displays .rdl and .sql files for any available report.</span></span> <span data-ttu-id="6f179-118">Sie können die importierte Abfrage so verwenden, wie sie ist, oder diese im Abfrage-Generator ändern.</span><span class="sxs-lookup"><span data-stu-id="6f179-118">You can use the imported query as it is, or you can modify it in the query builder.</span></span>  
  
 <span data-ttu-id="6f179-119">**! (Run)**</span><span class="sxs-lookup"><span data-stu-id="6f179-119">**! (Run)**</span></span>  
 <span data-ttu-id="6f179-120">Führt die Abfrage aus und gibt ein Resultset zurück, falls die Abfrage gültig ist.</span><span class="sxs-lookup"><span data-stu-id="6f179-120">Runs the query and returns a result set if the query is valid.</span></span> <span data-ttu-id="6f179-121">Beachten Sie, dass Sie die Abfrage nicht ausführen können, wenn sie ein Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="6f179-121">Note that you cannot execute the query if it is an expression.</span></span> <span data-ttu-id="6f179-122">Um eine ausdruckbasierte Abfrage zu überprüfen, müssen Sie eine Vorschau des Berichts anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6f179-122">To verify an expression-based query, you must preview the report.</span></span>  
  
 <span data-ttu-id="6f179-123">**Befehlstyp**</span><span class="sxs-lookup"><span data-stu-id="6f179-123">**Command type**</span></span>  
 <span data-ttu-id="6f179-124">Gibt Text, die gespeicherte Prozedur oder den Tabellendirektmodus (TableDirect) an.</span><span class="sxs-lookup"><span data-stu-id="6f179-124">Specifies text, stored procedure, or table direct.</span></span> <span data-ttu-id="6f179-125">Ob ein Befehlstyp verfügbar ist, hängt von der Datenverarbeitungserweiterung ab, die Sie angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="6f179-125">Availability of a command type depends on the data processing extension you specified.</span></span>  
  
 <span data-ttu-id="6f179-126">**Abfrage Bereich**</span><span class="sxs-lookup"><span data-stu-id="6f179-126">**Query pane**</span></span>  
 <span data-ttu-id="6f179-127">Geben Sie die Abfrage ein.</span><span class="sxs-lookup"><span data-stu-id="6f179-127">Type the query.</span></span>  
  
 <span data-ttu-id="6f179-128">**Ergebnisbereich**</span><span class="sxs-lookup"><span data-stu-id="6f179-128">**Result pane**</span></span>  
 <span data-ttu-id="6f179-129">Zeigt das von der Abfrage zurückgegebene Resultset an.</span><span class="sxs-lookup"><span data-stu-id="6f179-129">Shows the result set returned from the query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f179-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f179-130">See Also</span></span>  
 <span data-ttu-id="6f179-131">[Melden Sie eingebettete Datasets und freigegebene Datasets &#40;Berichts-Generator und SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6f179-131">[Report Embedded Datasets and Shared Datasets &#40;Report Builder and SSRS&#41;](report-data/report-embedded-datasets-and-shared-datasets-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="6f179-132">Hilfe des Berichts-Assistenten</span><span class="sxs-lookup"><span data-stu-id="6f179-132">Report Wizard Help</span></span>](../../2014/reporting-services/report-wizard-help.md)  
  
  
