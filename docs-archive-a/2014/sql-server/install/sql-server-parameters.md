---
title: SQL Server Parameter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Database Engine analysis [Upgrade Advisor]
- SQL Server Upgrade Advisor, Database Engine
- Upgrade Advisor [SQL Server], Database Engine
- analyzing system [Upgrade Advisor], Database Engine
ms.assetid: 44a18bfe-e593-47a5-995f-382c01d3f618
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 2b885e7616506fd08cae99166cc794dbfb5dac7d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720806"
---
# <a name="sql-server-parameters"></a><span data-ttu-id="beef1-102">SQL Server-Parameter</span><span class="sxs-lookup"><span data-stu-id="beef1-102">SQL Server Parameters</span></span>
  <span data-ttu-id="beef1-103">Legen Sie auf dieser Seite Parameter fest, die der Analyzer für die [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Analyse verwendet.</span><span class="sxs-lookup"><span data-stu-id="beef1-103">On this page, set parameters that the analyzer will use for [!INCLUDE[ssDE](../../includes/ssde-md.md)] analysis.</span></span> <span data-ttu-id="beef1-104">Sie können eine, mehrere oder alle Datenbanken sowie Ablaufverfolgungsdateien, die mit [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] erstellt wurden, und SQL-Batchdateien analysieren.</span><span class="sxs-lookup"><span data-stu-id="beef1-104">You can analyze one, several, or all databases, analyze trace files that were created by using [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)], and analyze SQL batch files.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="beef1-105">Einige Upgradeprobleme können nur erkannt werden, wenn Sie Ablaufverfolgungsdateien oder SQL-Batchdateien zur Analyse übermitteln.</span><span class="sxs-lookup"><span data-stu-id="beef1-105">Some upgrade issues can be detected only if you submit trace files or SQL batch files to be analyzed.</span></span>  
  
## <a name="options"></a><span data-ttu-id="beef1-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="beef1-106">Options</span></span>  
 <span data-ttu-id="beef1-107">**Zu analysierende Datenbank(en)**</span><span class="sxs-lookup"><span data-stu-id="beef1-107">**Database(s) to analyze**</span></span>  
 <span data-ttu-id="beef1-108">Um alle Datenbanken zu analysieren, aktivieren Sie das Kontrollkästchen **alle Datenbanken** .</span><span class="sxs-lookup"><span data-stu-id="beef1-108">To analyze all databases, select the **All databases** check box.</span></span> <span data-ttu-id="beef1-109">Um eine Auswahl von Datenbanken zu analysieren, aktivieren Sie die Kontrollkästchen neben den Datenbanken, die überprüft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="beef1-109">To analyze a selection of databases, select the check box next to each database to include in the scan.</span></span>  
  
 <span data-ttu-id="beef1-110">**Ablaufdateien analysieren**</span><span class="sxs-lookup"><span data-stu-id="beef1-110">**Analyze trace file(s)**</span></span>  
 <span data-ttu-id="beef1-111">Aktivieren Sie dieses Kontrollkästchen, um Ablaufverfolgungsdateien im Dateisystem zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="beef1-111">Select this check box to analyze trace files in the file system.</span></span>  
  
 <span data-ttu-id="beef1-112">**Pfad zu Ablaufdatei(en)**</span><span class="sxs-lookup"><span data-stu-id="beef1-112">**Path to trace file(s)**</span></span>  
 <span data-ttu-id="beef1-113">Sie können eine oder mehrere Dateien analysieren.</span><span class="sxs-lookup"><span data-stu-id="beef1-113">You can analyze one or more files.</span></span> <span data-ttu-id="beef1-114">Sie können zu einem Speicherort navigieren und mehrere Dateien auswählen, oder Sie können mehrere Dateinamen angeben.</span><span class="sxs-lookup"><span data-stu-id="beef1-114">You can browse to a location and select multiple files, or you can provide multiple file names.</span></span> <span data-ttu-id="beef1-115">Verwenden Sie den vollen Pfadnamen jeder Datei, geben Sie den Dateinamen an, und trennen Sie die Einträge durch einen senkrechten Strich (|).</span><span class="sxs-lookup"><span data-stu-id="beef1-115">Use the full path name to each file, include the file name, and separate entries by using the pipe character (|).</span></span>  
  
 <span data-ttu-id="beef1-116">Wenn Sie die Option Ablauf **Verfolgungs Datei (en) analysieren**aktivieren, wird **weiter** deaktiviert, bis Sie einen Pfadnamen und einen Dateinamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="beef1-116">If you enable **Analyze trace file(s)**, **Next** is disabled until you enter a path name and a file name.</span></span>  
  
 <span data-ttu-id="beef1-117">**[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Batchdatei (en) analysieren**</span><span class="sxs-lookup"><span data-stu-id="beef1-117">**Analyze [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] batch file(s)**</span></span>  
 <span data-ttu-id="beef1-118">Aktivieren Sie dieses Kontrollkästchen, um [!INCLUDE[tsql](../../includes/tsql-md.md)]-Batchdateien im Dateisystem zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="beef1-118">Select this check box to analyze [!INCLUDE[tsql](../../includes/tsql-md.md)] batch files in the file system.</span></span>  
  
 <span data-ttu-id="beef1-119">**Pfad zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Batchdatei (en)**</span><span class="sxs-lookup"><span data-stu-id="beef1-119">**Path to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] batch file(s)**</span></span>  
 <span data-ttu-id="beef1-120">Sie können eine oder mehrere Batchdateien analysieren.</span><span class="sxs-lookup"><span data-stu-id="beef1-120">You can analyze one or more batch files.</span></span> <span data-ttu-id="beef1-121">Sie können zu einem Speicherort navigieren und mehrere Dateien auswählen, oder Sie können mehrere Dateinamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="beef1-121">You can browse to a location and select multiple files, or you can type multiple file names.</span></span> <span data-ttu-id="beef1-122">Verwenden Sie den vollen Pfadnamen jeder Datei, geben Sie den Dateinamen an, und trennen Sie die Einträge durch einen senkrechten Strich (|).</span><span class="sxs-lookup"><span data-stu-id="beef1-122">Use the full path name to each file, include the file name, and separate entries by using the pipe character (|).</span></span>  
  
 <span data-ttu-id="beef1-123">Wenn Sie **SQL-Batchdatei (en) analysieren**aktivieren, wird die Schaltfläche **weiter** deaktiviert, bis Sie einen Pfadnamen und einen Dateinamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="beef1-123">If you enable **Analyze SQL batch file(s)**, the **Next** button is disabled until you enter a path name and a file name.</span></span>  
  
 <span data-ttu-id="beef1-124">**SQL-Batchtrennzeichen**</span><span class="sxs-lookup"><span data-stu-id="beef1-124">**SQL Batch Separator**</span></span>  
 <span data-ttu-id="beef1-125">Der Text, der zum Trennen von [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungsbatches verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="beef1-125">The text that is used to separate batches of [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="beef1-126">Der Standardwert ist " **go**".</span><span class="sxs-lookup"><span data-stu-id="beef1-126">The default value is **GO**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="beef1-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="beef1-127">See Also</span></span>  
 <span data-ttu-id="beef1-128">[Arbeiten mit Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="beef1-128">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="beef1-129">Benutzeroberflächenreferenz des Upgrade Advisors</span><span class="sxs-lookup"><span data-stu-id="beef1-129">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
