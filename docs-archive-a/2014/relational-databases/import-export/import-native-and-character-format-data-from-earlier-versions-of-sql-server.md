---
title: Importieren von Daten aus früheren SQL Server-Versionen im nativen Format oder im Zeichenformat | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- earlier versions [SQL Server], import and export data formats
- -V switch
- data formats [SQL Server], earlier versions
- previous versions [SQL Server], import and export data formats
ms.assetid: e644696f-9017-428e-a5b3-d445d1c630b3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 274c984d6ecec8af8f5bea27496450a45fc2f1df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620376"
---
# <a name="import-native-and-character-format-data-from-earlier-versions-of-sql-server"></a><span data-ttu-id="a41f9-102">Importieren von Daten aus früheren SQL Server-Versionen im systemeigenen Format oder im Zeichenformat</span><span class="sxs-lookup"><span data-stu-id="a41f9-102">Import Native and Character Format Data from Earlier Versions of SQL Server</span></span>
  <span data-ttu-id="a41f9-103">Sie können [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]bcp **in** verwenden, um Daten im nativen Format oder im Zeichenformat mithilfe des Schalters [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]-V [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]aus [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] , **oder** zu importieren.</span><span class="sxs-lookup"><span data-stu-id="a41f9-103">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], you can use **bcp** to import native and character format data from [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)], [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)], or [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] by using the **-V** switch.</span></span> <span data-ttu-id="a41f9-104">Der Schalter **-V** veranlasst [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] , Datentypen aus der angegebenen früheren Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zu verwenden. Zudem entspricht das Datendateiformat dem Format dieser früheren Version.</span><span class="sxs-lookup"><span data-stu-id="a41f9-104">The **-V** switch causes [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] to use data types from the specified earlier version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and the data file format are the same as the format in that earlier version.</span></span>  
  
 <span data-ttu-id="a41f9-105">Um eine frühere Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] für eine Datendatei anzugeben, verwenden Sie den Schalter **-V** mit einem der folgenden Qualifizierer:</span><span class="sxs-lookup"><span data-stu-id="a41f9-105">To specify an earlier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version for a data file, use the **-V** switch with one of the following qualifiers:</span></span>  
  
|<span data-ttu-id="a41f9-106">SQL Server-Version</span><span class="sxs-lookup"><span data-stu-id="a41f9-106">SQL Server version</span></span>|<span data-ttu-id="a41f9-107">Qualifizierer</span><span class="sxs-lookup"><span data-stu-id="a41f9-107">Qualifier</span></span>|  
|------------------------|---------------|  
|[!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]|<span data-ttu-id="a41f9-108">**-V80**</span><span class="sxs-lookup"><span data-stu-id="a41f9-108">**-V80**</span></span>|  
|[!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]|<span data-ttu-id="a41f9-109">**-V90**</span><span class="sxs-lookup"><span data-stu-id="a41f9-109">**-V90**</span></span>|  
|[!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)]|<span data-ttu-id="a41f9-110">**-V100**</span><span class="sxs-lookup"><span data-stu-id="a41f9-110">**-V100**</span></span>|  
|[!INCLUDE[ssSQL11](../../includes/sssql11-md.md)]|<span data-ttu-id="a41f9-111">**-V 110**</span><span class="sxs-lookup"><span data-stu-id="a41f9-111">**-V 110**</span></span>|  
  
## <a name="interpretation-of-data-types"></a><span data-ttu-id="a41f9-112">Interpretation von Datentypen</span><span class="sxs-lookup"><span data-stu-id="a41f9-112">Interpretation of Data Types</span></span>  
 [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] <span data-ttu-id="a41f9-113">und höhere Versionen bieten Unterstützung für einige neue Typen.</span><span class="sxs-lookup"><span data-stu-id="a41f9-113">and later versions have support for some new types.</span></span> <span data-ttu-id="a41f9-114">Beim Importieren eines neuen Datentyps aus einer früheren Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , muss der Dateityp in einem Format gespeichert sein, das von den älteren **bcp** -Clients gelesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="a41f9-114">When you want to import a new data type into an earlier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version, the data type must be stored in a format that readable by the older **bcp** clients.</span></span> <span data-ttu-id="a41f9-115">In der folgenden Tabelle finden Sie eine Übersicht, wie die neuen Datentypen konvertiert werden, damit sie mit den früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="a41f9-115">The following table summarizes how the new data types are converted for compatibility with the earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
|<span data-ttu-id="a41f9-116">Neue Datentypen in SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="a41f9-116">New data types in SQL Server 2005</span></span>|<span data-ttu-id="a41f9-117">Kompatible Datentypen in Version 6*x*</span><span class="sxs-lookup"><span data-stu-id="a41f9-117">Compatible data types in version 6*x*</span></span>|<span data-ttu-id="a41f9-118">Kompatible Datentypen in Version 70</span><span class="sxs-lookup"><span data-stu-id="a41f9-118">Compatible data types in version 70</span></span>|<span data-ttu-id="a41f9-119">Kompatible Datentypen in Version 80</span><span class="sxs-lookup"><span data-stu-id="a41f9-119">Compatible data types in version 80</span></span>|  
|---------------------------------------|-------------------------------------------|-----------------------------------------|-----------------------------------------|  
|`bigint`|`decimal`|`decimal`|*|  
|`sql_variant`|`text`|`nvarchar(4000)`|*|  
|`varchar(max)`|`text`|`text`|`text`|  
|`nvarchar(max)`|`ntext`|`ntext`|`ntext`|  
|`varbinary(max)`|`image`|`image`|`image`|  
|<span data-ttu-id="a41f9-120">XML</span><span class="sxs-lookup"><span data-stu-id="a41f9-120">XML</span></span>|`ntext`|`ntext`|`ntext`|  
|<span data-ttu-id="a41f9-121">UDT<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a41f9-121">UDT<sup>1</sup></span></span>|`image`|`image`|`image`|  
  
 <span data-ttu-id="a41f9-122">\*Dieser Typ wird nativ unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a41f9-122">\* This type is natively supported.</span></span>  
  
 <span data-ttu-id="a41f9-123"><sup>1</sup> UDT gibt einen benutzerdefinierten Typ an.</span><span class="sxs-lookup"><span data-stu-id="a41f9-123"><sup>1</sup> UDT indicates a user defined type.</span></span>  
  
## <a name="exporting-using--v-80"></a><span data-ttu-id="a41f9-124">Exportieren mit -V 80</span><span class="sxs-lookup"><span data-stu-id="a41f9-124">Exporting using -V 80</span></span>  
 <span data-ttu-id="a41f9-125">Wenn Sie einen Massen Export von Daten mithilfe des **-V80-** Schalters durch `nvarchar(max)` laufen, werden,,, `varchar(max)` `varbinary(max)` XML und UDT-Daten im einheitlichen Modus mit einem 4-Byte-Präfix wie `text` `image` die Daten, und und `ntext` nicht mit einem 8-Byte-Präfix gespeichert. Dies ist der Standardwert für [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und spätere Versionen.</span><span class="sxs-lookup"><span data-stu-id="a41f9-125">When you bulk export data by using the **-V80** switch, `nvarchar(max)`, `varchar(max)`, `varbinary(max)`, XML, and UDT data in native mode are stored with a 4-byte prefix, like `text`, `image`, and `ntext` data, rather than with an 8-byte prefix, which is the default for [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions.</span></span>  
  
## <a name="copying-date-values"></a><span data-ttu-id="a41f9-126">Kopieren von Datumswerten</span><span class="sxs-lookup"><span data-stu-id="a41f9-126">Copying Date Values</span></span>  
 <span data-ttu-id="a41f9-127">Von**bcp** wird die ODBC-API für das Massenkopieren verwendet.</span><span class="sxs-lookup"><span data-stu-id="a41f9-127">**bcp** uses the ODBC bulk copy API.</span></span> <span data-ttu-id="a41f9-128">Deshalb verwendet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]bcp **zum Importieren von Datumswerten in** das ODBC-Datumsformat (*jjjj-mm-tt hh:mm:ss*[ *.f...* ]).</span><span class="sxs-lookup"><span data-stu-id="a41f9-128">Therefore, to import date values into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], **bcp** uses the ODBC date format (*yyyy-mm-dd hh:mm:ss*[*.f...*]).</span></span>  
  
 <span data-ttu-id="a41f9-129">Der Befehl **bcp** exportiert Datendateien im Zeichenformat unter Verwendung des ODBC-Standard Formats für `datetime` -und- `smalldatetime` Werte.</span><span class="sxs-lookup"><span data-stu-id="a41f9-129">The **bcp** command exports character format data files using the ODBC default format for `datetime` and `smalldatetime` values.</span></span> <span data-ttu-id="a41f9-130">So wird beispielsweise eine `datetime`-Spalte mit dem Datum `12 Aug 1998` beim Massenkopieren in eine Datendatei als die Zeichenfolge `1998-08-12 00:00:00.000` übertragen.</span><span class="sxs-lookup"><span data-stu-id="a41f9-130">For example, a `datetime` column containing the date `12 Aug 1998` is bulk copied to a data file as the character string `1998-08-12 00:00:00.000`.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a41f9-131">Wenn Sie Daten `smalldatetime` mithilfe von **bcp**in ein Feld importieren, achten Sie darauf, dass der Wert für Sekunden 00,000 ist; andernfalls schlägt der Vorgang fehl.</span><span class="sxs-lookup"><span data-stu-id="a41f9-131">When importing data into a `smalldatetime` field using **bcp**, be sure the value for seconds is 00.000; otherwise the operation will fail.</span></span> <span data-ttu-id="a41f9-132">Der `smalldatetime`-Datentyp kann nur Werte beinhalten, die auf die volle Minute gerundet sind.</span><span class="sxs-lookup"><span data-stu-id="a41f9-132">The `smalldatetime` data type only holds values to the nearest minute.</span></span> <span data-ttu-id="a41f9-133">BULK INSERT und INSERT ... SELECT \* FROM OPENROWSET(BULK...) schlagen in diesem Fall nicht fehl, schneiden jedoch den Sekundenwert ab.</span><span class="sxs-lookup"><span data-stu-id="a41f9-133">BULK INSERT and INSERT ... SELECT \* FROM OPENROWSET(BULK...) will not fail in this instance but will truncate the seconds value.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="a41f9-134">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="a41f9-134">Related Tasks</span></span>  
 <span data-ttu-id="a41f9-135">**So verwenden Sie Datenformate für Massenimport oder Massenexport**</span><span class="sxs-lookup"><span data-stu-id="a41f9-135">**To use data formats for bulk import or bulk export**</span></span>  
  
-   [<span data-ttu-id="a41f9-136">Verwenden des Zeichenformats zum Importieren und Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a41f9-136">Use Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="a41f9-137">Verwenden des nativen Formats zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a41f9-137">Use Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-native-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="a41f9-138">Verwenden des Unicode-Zeichenformats zum Importieren und Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a41f9-138">Use Unicode Character Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-character-format-to-import-or-export-data-sql-server.md)  
  
-   [<span data-ttu-id="a41f9-139">Verwenden des nativen Unicode-Formats zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="a41f9-139">Use Unicode Native Format to Import or Export Data &#40;SQL Server&#41;</span></span>](use-unicode-native-format-to-import-or-export-data-sql-server.md)  
  
 
  
## <a name="see-also"></a><span data-ttu-id="a41f9-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a41f9-140">See Also</span></span>  
 <span data-ttu-id="a41f9-141">[bcp (Hilfsprogramm)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="a41f9-141">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="a41f9-142">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a41f9-142">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 <span data-ttu-id="a41f9-143">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a41f9-143">[OPENROWSET &#40;Transact-SQL&#41;](/sql/t-sql/functions/openrowset-transact-sql) </span></span>  
 <span data-ttu-id="a41f9-144">[Datentypen &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a41f9-144">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="a41f9-145">[Abwärtskompatibilität der SQL Server-Datenbank-Engine](../../database-engine/sql-server-database-engine-backward-compatibility.md) </span><span class="sxs-lookup"><span data-stu-id="a41f9-145">[SQL Server Database Engine Backward Compatibility](../../database-engine/sql-server-database-engine-backward-compatibility.md) </span></span>  
 [<span data-ttu-id="a41f9-146">CAST und CONVERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a41f9-146">CAST and CONVERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/cast-and-convert-transact-sql)  
  
  
