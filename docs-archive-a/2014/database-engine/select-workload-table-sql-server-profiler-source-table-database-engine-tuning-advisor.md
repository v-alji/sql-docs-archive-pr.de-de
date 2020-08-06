---
title: SQL Server Profiler Quell Tabelle-Datenbankoptimierungsratgeber-Arbeits Auslastungs Tabelle auswählen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.pro.replay.tools.sourcetable.f1
helpviewer_keywords:
- Select Workload Table dialog box
- Source Table dialog box
ms.assetid: 51185be7-7092-480a-a52c-cf7786c4a0a0
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: d10899c01df8e7fbc7ee45d108841a18d3248500
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616666"
---
# <a name="sql-server-profiler---source-table-database-engine-tuning-advisor---select-workload-table"></a><span data-ttu-id="19601-102">Tabellen Datenbankoptimierungsratgeber-Arbeits Auslastungs Tabelle für SQL Server Profiler Quelle</span><span class="sxs-lookup"><span data-stu-id="19601-102">SQL Server Profiler - Source Table-Database Engine Tuning Advisor - Select Workload Table</span></span>
  <span data-ttu-id="19601-103">In Microsoft [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] und im Optimierungsratgeber von [!INCLUDE[ssDE](../includes/ssde-md.md)] dient dieses Dialogfeld zur Auswahl von Tabellen.</span><span class="sxs-lookup"><span data-stu-id="19601-103">Microsoft [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] and [!INCLUDE[ssDE](../includes/ssde-md.md)] Tuning Advisor use this dialog box to select tables.</span></span>  
  
 <span data-ttu-id="19601-104">In [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] können Sie mithilfe des Dialogfelds **Quelltabelle** eine Quelltabelle für eine Ablaufverfolgungstabelle angeben.</span><span class="sxs-lookup"><span data-stu-id="19601-104">In [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)], use the **Source Table** dialog box to specify a source table for a trace table.</span></span> <span data-ttu-id="19601-105">Dabei handelt es sich um eine Tabelle, aus der eine Ablaufverfolgung geladen wird. Deren Inhalte können angezeigt oder zur Wiedergabe der Ablaufverfolgung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="19601-105">This is a table from which a trace is loaded, and the contents of which are viewed or used for replaying the trace.</span></span>  
  
 <span data-ttu-id="19601-106">Wählen Sie mithilfe des Dialogfelds [!INCLUDE[ssDE](../includes/ssde-md.md)]Arbeitsauslastungstabelle auswählen **im Optimierungsratgeber von** eine Datenbanktabelle mit Ablaufverfolgungsinformationen von [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] aus, die als zu optimierende Arbeitsauslastung oder zur Vorschau der Tabelleninhalte vor dem Starten der Optimierungsanalyse verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="19601-106">In [!INCLUDE[ssDE](../includes/ssde-md.md)] Tuning Advisor, use the **Select Workload Table** dialog box to select a database table that contains [!INCLUDE[ssSqlProfiler](../includes/sssqlprofiler-md.md)] trace information to use as a tuning workload, or to preview the table contents before starting tuning analysis.</span></span>  
  
## <a name="options"></a><span data-ttu-id="19601-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="19601-107">Options</span></span>  
 <span data-ttu-id="19601-108">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="19601-108">**SQL Server**</span></span>  
 <span data-ttu-id="19601-109">Gibt die Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] an, zu der zurzeit eine Verbindung besteht.</span><span class="sxs-lookup"><span data-stu-id="19601-109">Specifies the instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] currently connected.</span></span> <span data-ttu-id="19601-110">Dieses Feld wird automatisch ausgefüllt und kann nicht aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="19601-110">This field is populated automatically and cannot be updated.</span></span>  
  
 <span data-ttu-id="19601-111">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="19601-111">**Database**</span></span>  
 <span data-ttu-id="19601-112">Geben Sie die Datenbank an, in der die Ablaufverfolgungstabelle gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="19601-112">Specify the database where the trace table is located.</span></span>  
  
 <span data-ttu-id="19601-113">**Besitzer**</span><span class="sxs-lookup"><span data-stu-id="19601-113">**Owner**</span></span>  
 <span data-ttu-id="19601-114">Specifies the owner of the trace table.</span><span class="sxs-lookup"><span data-stu-id="19601-114">Specifies the owner of the trace table.</span></span> <span data-ttu-id="19601-115">Dieses Feld wird automatisch mit **dbo**ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="19601-115">This field is populated automatically as **dbo**.</span></span>  
  
 <span data-ttu-id="19601-116">**Tabelle**</span><span class="sxs-lookup"><span data-stu-id="19601-116">**Table**</span></span>  
 <span data-ttu-id="19601-117">Geben Sie den Namen der Ablaufverfolgungstabelle an, aus der die Ablaufverfolgung gelesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="19601-117">Specify the name of the trace table from which the trace should be read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19601-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="19601-118">See Also</span></span>  
 <span data-ttu-id="19601-119">[Speichern von Ablaufverfolgungsergebnissen in einer Tabelle &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) </span><span class="sxs-lookup"><span data-stu-id="19601-119">[Save Trace Results to a Table &#40;SQL Server Profiler&#41;](../tools/sql-server-profiler/save-trace-results-to-a-table-sql-server-profiler.md) </span></span>  
 <span data-ttu-id="19601-120">[Vorlagen und Berechtigungen in SQL Server Profiler](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="19601-120">[SQL Server Profiler Templates and Permissions](../tools/sql-server-profiler/sql-server-profiler-templates-and-permissions.md) </span></span>  
 [<span data-ttu-id="19601-121">Datenbankoptimierungsratgeber</span><span class="sxs-lookup"><span data-stu-id="19601-121">Database Engine Tuning Advisor</span></span>](../relational-databases/performance/database-engine-tuning-advisor.md)  
  
  
