---
title: Datenformate für Massenimport oder Massenexport (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- data formats [SQL Server], choosing
- bulk importing [SQL Server], data formats
ms.assetid: 73fe6741-9437-4b26-b030-28b863e74399
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 1b92ac8c038362ff18a1459a8bf3c55b6b596a17
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607761"
---
# <a name="data-formats-for-bulk-import-or-bulk-export-sql-server"></a><span data-ttu-id="34509-102">Datenformate für Massenimport oder Massenexport (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="34509-102">Data Formats for Bulk Import or Bulk Export (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="34509-103">kann Daten in Zeichendatenformat oder systemeigenem binärem Datenformat akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="34509-103">can accept data in character data format or native binary data format.</span></span> <span data-ttu-id="34509-104">Verwenden Sie das Zeichenformat, wenn Sie Daten zwischen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und einer anderen Anwendung (z. B. [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel) bzw. einem anderen Datenbankserver (wie Oracle oder [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]) verschieben.</span><span class="sxs-lookup"><span data-stu-id="34509-104">Use character format when you move data between [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and another application (such as [!INCLUDE[msCoName](../../includes/msconame-md.md)] Excel) or another database server (such as Oracle or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]).</span></span> <span data-ttu-id="34509-105">Das systemeigene Format kann nur verwendet werden, wenn Sie Daten zwischen verschiedenen Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verschieben.</span><span class="sxs-lookup"><span data-stu-id="34509-105">You can use native format only when you transfer data between instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="34509-106">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="34509-106">**In this Topic:**</span></span>  
  
-   [<span data-ttu-id="34509-107">Datenformate für Massenimport oder -export</span><span class="sxs-lookup"><span data-stu-id="34509-107">Data Formats for Bulk Import or Export</span></span>](#ComponentsAndConcepts)  
  
-   [<span data-ttu-id="34509-108">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="34509-108">Related Tasks</span></span>](#RelatedTasks)  
  
##  <a name="data-formats-for-bulk-import-or-export"></a><a name="ComponentsAndConcepts"></a> <span data-ttu-id="34509-109">Datenformate für Massenimport oder -export</span><span class="sxs-lookup"><span data-stu-id="34509-109">Data Formats for Bulk Import or Export</span></span>  
 <span data-ttu-id="34509-110">In der folgenden Tabelle ist angegeben, welches Datenformat im Allgemeinen für die Verwendung geeignet ist. Die Wahl hängt von der Darstellung der Daten und von der Quelle bzw. dem Ziel des Vorgangs ab.</span><span class="sxs-lookup"><span data-stu-id="34509-110">The following table indicates what data format is generally appropriate to use depending on how the data is represented and the source or target of the operation.</span></span>  
  
|<span data-ttu-id="34509-111">Vorgang</span><span class="sxs-lookup"><span data-stu-id="34509-111">Operation</span></span>|<span data-ttu-id="34509-112">Systemeigenes Format</span><span class="sxs-lookup"><span data-stu-id="34509-112">Native</span></span>|<span data-ttu-id="34509-113">Systemeigenes Unicode-Format</span><span class="sxs-lookup"><span data-stu-id="34509-113">Unicode native</span></span>|<span data-ttu-id="34509-114">Zeichen</span><span class="sxs-lookup"><span data-stu-id="34509-114">Character</span></span>|<span data-ttu-id="34509-115">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="34509-115">Unicode character</span></span>|  
|---------------|------------|--------------------|---------------|-----------------------|  
|<span data-ttu-id="34509-116">Massenübertragung von Daten zwischen mehreren Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe einer Datendatei, die keine Sonderzeichen oder Zeichen aus Doppelbyte-Zeichensätzen (Double-Byte Character Set, DBCS) enthält.</span><span class="sxs-lookup"><span data-stu-id="34509-116">Bulk transfers of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that does not contain any extended or double-byte character set (DBCS) characters.</span></span> <span data-ttu-id="34509-117">Sofern keine Formatdatei verwendet wird, müssen diese Tabellen identisch definiert sein.</span><span class="sxs-lookup"><span data-stu-id="34509-117">Unless a format file is used, these tables must be identically defined.</span></span>|<span data-ttu-id="34509-118">Ja<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="34509-118">Yes<sup>1</sup></span></span>|-|-|-|  
|<span data-ttu-id="34509-119">Für `sql_variant`-Spalten eignet sich das systemeigene Datenformat am besten, da es im Gegensatz zu Zeichen- und Unicode-Formaten die Metadaten für die einzelnen `sql_variant`-Werte beibehält.</span><span class="sxs-lookup"><span data-stu-id="34509-119">For `sql_variant` columns, use of native data format is best, because native data format preserves the metadata for each `sql_variant` value, unlike character or Unicode formats.</span></span>|<span data-ttu-id="34509-120">Ja</span><span class="sxs-lookup"><span data-stu-id="34509-120">Yes</span></span>|-|-|-|  
|<span data-ttu-id="34509-121">Massenübertragung von Daten zwischen mehreren Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe einer Datendatei, die Sonderzeichen oder DBCS-Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="34509-121">Bulk transfers of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains extended or DBCS characters.</span></span>|-|<span data-ttu-id="34509-122">Ja</span><span class="sxs-lookup"><span data-stu-id="34509-122">Yes</span></span>|-|-|  
|<span data-ttu-id="34509-123">Massenimport von Daten aus einer Textdatei, die von einem anderen Programm generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="34509-123">Bulk import of data from a text file that is generated by another program.</span></span>|-|-|<span data-ttu-id="34509-124">Ja</span><span class="sxs-lookup"><span data-stu-id="34509-124">Yes</span></span>|-|  
|<span data-ttu-id="34509-125">Massenexport von Daten in eine Textdatei, die in einem anderen Programm verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="34509-125">Bulk export of data to a text file that is to be used in another program.</span></span>|-|-|<span data-ttu-id="34509-126">Ja</span><span class="sxs-lookup"><span data-stu-id="34509-126">Yes</span></span>|-|  
|<span data-ttu-id="34509-127">Massenübertragung von Daten zwischen mehreren Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe einer Datendatei, die Unicode-Daten, aber keine Sonderzeichen oder DBCS-Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="34509-127">Bulk transfers of data between multiple instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using a data file that contains Unicode data and does not contain any extended or DBCS characters.</span></span>|-|-|-|<span data-ttu-id="34509-128">Ja</span><span class="sxs-lookup"><span data-stu-id="34509-128">Yes</span></span>|  
  
 <span data-ttu-id="34509-129"><sup>1</sup> schnellste Methode für den Massen Export von Daten aus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] bei Verwendung von **bcp**.</span><span class="sxs-lookup"><span data-stu-id="34509-129"><sup>1</sup> Fastest method for the bulk export of data from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] when using **bcp**.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="34509-130">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="34509-130">Related Tasks</span></span>  
  
-   [<span data-ttu-id="34509-131">Verwenden des nativen Formats zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34509-131">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="34509-132">Verwenden des Zeichenformats zum Importieren und Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34509-132">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="34509-133">Verwenden des nativen Unicode-Formats zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34509-133">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="34509-134">Verwenden des Unicode-Zeichenformats zum Importieren und Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34509-134">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="34509-135">Importieren von Daten aus früheren SQL Server-Versionen im nativen Format oder im Zeichenformat</span><span class="sxs-lookup"><span data-stu-id="34509-135">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>](import-native-and-character-format-data-from-earlier-versions-of-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="34509-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="34509-136">See Also</span></span>  
 <span data-ttu-id="34509-137">[Datentypen &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="34509-137">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 [<span data-ttu-id="34509-138">Angeben von Datenformaten für die Kompatibilität bei Verwendung von bcp &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="34509-138">Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;</span></span>](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md)  
  
  
