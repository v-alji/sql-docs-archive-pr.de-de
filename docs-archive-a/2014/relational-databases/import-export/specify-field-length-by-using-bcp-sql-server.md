---
title: Angeben der Feldlänge mithilfe von bcp (SQL Server) | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-movement
ms.topic: conceptual
helpviewer_keywords:
- native data format [SQL Server]
- default field lengths
- field length [SQL Server]
- data formats [SQL Server], field length
- bcp utility [SQL Server], field length
ms.assetid: 240f33ca-ef4a-413a-a4de-831885cb505b
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 13343b4f3778df1bbe7ef1c99b3d06338f18631c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696842"
---
# <a name="specify-field-length-by-using-bcp-sql-server"></a><span data-ttu-id="b2fea-102">Angeben der Feldlänge mithilfe von bcp (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="b2fea-102">Specify Field Length by Using bcp (SQL Server)</span></span>
  <span data-ttu-id="b2fea-103">Die Feldlänge weist auf die maximale Anzahl von Zeichen hin, die zum Darstellen der Daten im Zeichenformat benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="b2fea-103">The field length indicates the maximum number of characters that are required to represent data in character format.</span></span> <span data-ttu-id="b2fea-104">Die Feldlänge ist bereits bekannt, wenn die Daten im systemeigenen Format gespeichert werden (z. B. der `int`-Datentyp, der 4 Bytes benötigt).</span><span class="sxs-lookup"><span data-stu-id="b2fea-104">The field length is already known if the data is stored in the native format; for example, the `int` data type takes 4 bytes.</span></span> <span data-ttu-id="b2fea-105">Wenn Sie für die Präfix Länge 0 angegeben haben, werden Sie vom **bcp** -Befehl zur Eingabe der Feldlänge, der Standardfeld Längen und der Auswirkung der Feldlänge auf die Datenspeicherung in Datendateien aufgefordert, die `char` Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="b2fea-105">If you have indicated 0 for the prefix length, the **bcp** command prompts you for field length, the default field lengths, and the impact of field-length on data storage in data files that contain `char` data.</span></span>  
  
## <a name="the-bcp-prompt-for-field-length"></a><span data-ttu-id="b2fea-106">Die bcp-Eingabeaufforderung für die Feldlänge</span><span class="sxs-lookup"><span data-stu-id="b2fea-106">The bcp Prompt for Field Length</span></span>  
 <span data-ttu-id="b2fea-107">Wenn ein interaktiver **bcp**-Befehl die Option **in** oder **out**, jedoch keinen Formatdateischalter ( **-f**) bzw. keinen Datenformatschalter ( **-n**, **-c**, **-w** oder **-N**) enthält, fordert der Befehl wie folgt zur Eingabe der Feldlänge für jedes Datenfeld auf:</span><span class="sxs-lookup"><span data-stu-id="b2fea-107">If an interactive **bcp** command contains the **in** or **out** option without either the format file switch (**-f**) or a data-format switch (**-n**, **-c**, **-w**, or **-N**), the command prompts for the field length of each data field, as follows:</span></span>  
  
 `Enter length of field <field_name> [<default>]:`  
  
 <span data-ttu-id="b2fea-108">Ein Beispiel, das die Verwendung der Aufforderung im Kontext veranschaulicht, finden Sie unter [ Angeben von Datenformaten für die Kompatibilität bei Verwendung von „bcp“ &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b2fea-108">For an example that shows this prompt in context, see [Specify Data Formats for Compatibility when Using bcp &#40;SQL Server&#41;](specify-data-formats-for-compatibility-when-using-bcp-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b2fea-109">Nachdem Sie interaktiv alle Felder in einem **bcp**-Befehl angegeben haben, werden Sie vom Befehl dazu aufgefordert, Ihre Antworten für die einzelnen Felder in einer Nicht-XML-Formatdatei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b2fea-109">After you interactively specify all of the fields in a **bcp** command, the command prompts you save your responses for each field in a non-XML format file.</span></span> <span data-ttu-id="b2fea-110">Weitere Informationen zu Nicht-XML-Formatdateien finden Sie unter [Nicht-XML-Formatdateien &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="b2fea-110">For more information on non-XML format files, see [Non-XML Format Files &#40;SQL Server&#41;](xml-format-files-sql-server.md).</span></span>  
  
 <span data-ttu-id="b2fea-111">Ob Sie vom **bcp** -Befehl zur Eingabe der Feldlänge aufgefordert werden, hängt von verschiedenen Faktoren ab, die im Folgenden aufgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="b2fea-111">Whether a **bcp** command prompts for field length depends on several factors, as follows:</span></span>  
  
-   <span data-ttu-id="b2fea-112">Wenn Sie Datentypen ohne feste Länge kopieren und eine Präfixlänge von 0 angeben, werden Sie von **bcp** zur Eingabe einer Feldlänge aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="b2fea-112">When you copy data types that are not of fixed length and you specify a prefix length of 0, **bcp** prompts for a field length.</span></span>  
  
-   <span data-ttu-id="b2fea-113">Wenn **bcp** Daten, die nicht auf Zeichen basieren, in Zeichen konvertiert, schlägt das Hilfsprogramm eine Standardfeldlänge vor, die groß genug zum Speichern der Daten ist.</span><span class="sxs-lookup"><span data-stu-id="b2fea-113">When converting noncharacter data to character data, **bcp** suggests a default field length large enough to store the data.</span></span>  
  
-   <span data-ttu-id="b2fea-114">Wenn der Dateispeichertyp Daten enthält, die nicht auf Zeichen basieren, fordert **bcp** nicht zur Eingabe einer Feldlänge auf.</span><span class="sxs-lookup"><span data-stu-id="b2fea-114">If the file storage type is noncharacter, the **bcp** command does not prompt for a field length.</span></span> <span data-ttu-id="b2fea-115">Die Daten werden in der nativen Datendarstellung (natives Format) in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b2fea-115">The data is stored in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data representation (native format).</span></span>  
  
## <a name="using-default-field-lengths"></a><span data-ttu-id="b2fea-116">Verwenden der Standardfeldlängen</span><span class="sxs-lookup"><span data-stu-id="b2fea-116">Using Default Field Lengths</span></span>  
 <span data-ttu-id="b2fea-117">Im Allgemeinen empfiehlt [!INCLUDE[msCoName](../../includes/msconame-md.md)] , dass Sie die von **bcp**für die Feldlänge vorgeschlagenen Standardwerte übernehmen.</span><span class="sxs-lookup"><span data-stu-id="b2fea-117">Generally, [!INCLUDE[msCoName](../../includes/msconame-md.md)] recommends that you accept the **bcp**-suggested default values for the field length.</span></span> <span data-ttu-id="b2fea-118">Wenn Sie beim Erstellen einer Datendatei im Zeichenmodus die Standardfeldlänge verwenden, können Sie sicherstellen, dass die Daten nicht abgeschnitten werden und auch keine numerischen Überlauffehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="b2fea-118">When a character mode data file is created, using the default field length ensures that data is not truncated and that numeric overflow errors do not occur.</span></span>  
  
 <span data-ttu-id="b2fea-119">Die Angabe falscher Feldlängen kann zu Problemen führen.</span><span class="sxs-lookup"><span data-stu-id="b2fea-119">If you specify a field length that is incorrect, problems can occur.</span></span> <span data-ttu-id="b2fea-120">Wenn Sie beispielsweise numerische Daten kopieren und eine Feldlänge angeben, die für die Daten nicht ausreicht, druckt das Hilfsprogramm **bcp** eine Überlaufmeldung und kopiert die Daten nicht.</span><span class="sxs-lookup"><span data-stu-id="b2fea-120">For instance, if you copy numeric data and you specify a field length that is too short for the data, the **bcp** utility prints an overflow message and does not copy the data.</span></span> <span data-ttu-id="b2fea-121">Wenn Sie `datetime` Daten exportieren und für die Zeichenfolge eine Feldlänge von weniger als 26 Bytes angeben, werden die Daten vom Hilfsprogramm **bcp** ohne Fehlermeldung abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="b2fea-121">Also, if you export `datetime` data and specify a field length of less than 26 bytes for the character string, the **bcp** utility truncates the data without an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b2fea-122">Bei Verwendung der Standardgrößenoption wird von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine vollständige Zeichenfolge erwartet.</span><span class="sxs-lookup"><span data-stu-id="b2fea-122">When the default size option is used, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] expects to read an entire string.</span></span> <span data-ttu-id="b2fea-123">In bestimmten Situationen kann die Verwendung der Standardfeldlänge zu einem Fehler des Typs "unerwartetes Dateiende" führen.</span><span class="sxs-lookup"><span data-stu-id="b2fea-123">In some situations, use of a default field length can lead to an "unexpected end of file" error.</span></span> <span data-ttu-id="b2fea-124">Dieser Fehler tritt in der Regel mit `money` den `datetime` Datentypen und auf, wenn nur ein Teil des erwarteten Felds in der Datendatei auftritt, z. b. Wenn ein `datetime` Wert von *mm* / *DD* / *yy* ohne die Zeitkomponente angegeben wird und daher kürzer ist als die erwartete 24-Zeichen-Länge eines `datetime` Werts im- `char` Format.</span><span class="sxs-lookup"><span data-stu-id="b2fea-124">Typically, this error occurs with the `money` and `datetime` data types when only part of the expected field occurs in the data file; for example, when a `datetime` value of *mm*/*dd*/*yy* is specified without the time component and is, therefore, shorter than the expected 24 character length of a `datetime` value in `char` format.</span></span> <span data-ttu-id="b2fea-125">Zur Vermeidung dieses Fehlertyps sollten Sie Feldabschlusszeichen oder Datenfelder mit fester Länge verwenden oder die Standardfeldlänge auf einen anderen Wert ändern.</span><span class="sxs-lookup"><span data-stu-id="b2fea-125">To avoid this type of error, use field terminators or fixed-length data fields, or change the default field length by specifying another value.</span></span>  
  
### <a name="default-field-lengths-for-character-file-storage"></a><span data-ttu-id="b2fea-126">Standardfeldlänge zum Speichern von Dateien im Zeichenformat</span><span class="sxs-lookup"><span data-stu-id="b2fea-126">Default Field Lengths for Character File Storage</span></span>  
 <span data-ttu-id="b2fea-127">In der folgenden Tabelle werden die Standardfeldlängen für Daten aufgeführt, die als Dateien im Zeichenformat gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="b2fea-127">The following table lists the default field lengths for data to be stored as a character-file storage type.</span></span> <span data-ttu-id="b2fea-128">Daten, die NULL zulassen, besitzen die gleiche Länge wie Daten ohne NULL-Werte.</span><span class="sxs-lookup"><span data-stu-id="b2fea-128">Nullable data is the same length as nonnull data.</span></span>  
  
|<span data-ttu-id="b2fea-129">Datentyp</span><span class="sxs-lookup"><span data-stu-id="b2fea-129">Data type</span></span>|<span data-ttu-id="b2fea-130">Standardlänge (Zeichen)</span><span class="sxs-lookup"><span data-stu-id="b2fea-130">Default length (characters)</span></span>|  
|---------------|-----------------------------------|  
|`char`|<span data-ttu-id="b2fea-131">Für die Spalte definierte Länge</span><span class="sxs-lookup"><span data-stu-id="b2fea-131">Length defined for the column</span></span>|  
|`varchar`|<span data-ttu-id="b2fea-132">Für die Spalte definierte Länge</span><span class="sxs-lookup"><span data-stu-id="b2fea-132">Length defined for the column</span></span>|  
|`nchar`|<span data-ttu-id="b2fea-133">Zweifaches der für die Spalte definierten Länge</span><span class="sxs-lookup"><span data-stu-id="b2fea-133">Twice the length defined for the column</span></span>|  
|`nvarchar`|<span data-ttu-id="b2fea-134">Zweifaches der für die Spalte definierten Länge</span><span class="sxs-lookup"><span data-stu-id="b2fea-134">Twice the length defined for the column</span></span>|  
|`Text`|<span data-ttu-id="b2fea-135">0</span><span class="sxs-lookup"><span data-stu-id="b2fea-135">0</span></span>|  
|`ntext`|<span data-ttu-id="b2fea-136">0</span><span class="sxs-lookup"><span data-stu-id="b2fea-136">0</span></span>|  
|`bit`|<span data-ttu-id="b2fea-137">1</span><span class="sxs-lookup"><span data-stu-id="b2fea-137">1</span></span>|  
|`binary`|<span data-ttu-id="b2fea-138">Das Doppelte der für die Spalte definierten Länge + 1</span><span class="sxs-lookup"><span data-stu-id="b2fea-138">Twice the length defined for the column + 1</span></span>|  
|`varbinary`|<span data-ttu-id="b2fea-139">Das Doppelte der für die Spalte definierten Länge + 1</span><span class="sxs-lookup"><span data-stu-id="b2fea-139">Twice the length defined for the column + 1</span></span>|  
|`image`|<span data-ttu-id="b2fea-140">0</span><span class="sxs-lookup"><span data-stu-id="b2fea-140">0</span></span>|  
|`datetime`|<span data-ttu-id="b2fea-141">24</span><span class="sxs-lookup"><span data-stu-id="b2fea-141">24</span></span>|  
|`smalldatetime`|<span data-ttu-id="b2fea-142">24</span><span class="sxs-lookup"><span data-stu-id="b2fea-142">24</span></span>|  
|`float`|<span data-ttu-id="b2fea-143">30</span><span class="sxs-lookup"><span data-stu-id="b2fea-143">30</span></span>|  
|`real`|<span data-ttu-id="b2fea-144">30</span><span class="sxs-lookup"><span data-stu-id="b2fea-144">30</span></span>|  
|`int`|<span data-ttu-id="b2fea-145">12</span><span class="sxs-lookup"><span data-stu-id="b2fea-145">12</span></span>|  
|`bigint`|<span data-ttu-id="b2fea-146">19</span><span class="sxs-lookup"><span data-stu-id="b2fea-146">19</span></span>|  
|`smallint`|<span data-ttu-id="b2fea-147">7</span><span class="sxs-lookup"><span data-stu-id="b2fea-147">7</span></span>|  
|`tinyint`|<span data-ttu-id="b2fea-148">5</span><span class="sxs-lookup"><span data-stu-id="b2fea-148">5</span></span>|  
|`money`|<span data-ttu-id="b2fea-149">30</span><span class="sxs-lookup"><span data-stu-id="b2fea-149">30</span></span>|  
|`smallmoney`|<span data-ttu-id="b2fea-150">30</span><span class="sxs-lookup"><span data-stu-id="b2fea-150">30</span></span>|  
|`decimal`|<span data-ttu-id="b2fea-151">41\*</span><span class="sxs-lookup"><span data-stu-id="b2fea-151">41\*</span></span>|  
|`numeric`|<span data-ttu-id="b2fea-152">41\*</span><span class="sxs-lookup"><span data-stu-id="b2fea-152">41\*</span></span>|  
|`uniqueidentifier`|<span data-ttu-id="b2fea-153">37</span><span class="sxs-lookup"><span data-stu-id="b2fea-153">37</span></span>|  
|`timestamp`|<span data-ttu-id="b2fea-154">17</span><span class="sxs-lookup"><span data-stu-id="b2fea-154">17</span></span>|  
|`varchar(max)`|<span data-ttu-id="b2fea-155">0</span><span class="sxs-lookup"><span data-stu-id="b2fea-155">0</span></span>|  
|`varbinary(max)`|<span data-ttu-id="b2fea-156">0</span><span class="sxs-lookup"><span data-stu-id="b2fea-156">0</span></span>|  
|`nvarchar(max)`|<span data-ttu-id="b2fea-157">0</span><span class="sxs-lookup"><span data-stu-id="b2fea-157">0</span></span>|  
|<span data-ttu-id="b2fea-158">UDT</span><span class="sxs-lookup"><span data-stu-id="b2fea-158">UDT</span></span>|<span data-ttu-id="b2fea-159">Länge der UDT-Spalte (User-defined Term)</span><span class="sxs-lookup"><span data-stu-id="b2fea-159">Length of the user-defined term (UDT) column</span></span>|  
|<span data-ttu-id="b2fea-160">XML</span><span class="sxs-lookup"><span data-stu-id="b2fea-160">XML</span></span>|<span data-ttu-id="b2fea-161">0</span><span class="sxs-lookup"><span data-stu-id="b2fea-161">0</span></span>|  
  
 <span data-ttu-id="b2fea-162">\*Weitere Informationen zu den `decimal` `numeric` Datentypen und finden Sie unter [Decimal und numeric &#40;Transact-SQL-&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b2fea-162">\*For more information about the `decimal` and `numeric` data types, see [decimal and numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b2fea-163">Eine Spalte des Typs `tinyint` kann Werte von 0 bis 255 aufweisen. Zum Darstellen einer beliebigen Zahl in diesem Bereich werden maximal drei Zeichen (bei den Werten von 100 bis 255) benötigt.</span><span class="sxs-lookup"><span data-stu-id="b2fea-163">A column of type `tinyint` can have values from 0 through 255; the maximum number of characters that are needed to represent any number in that range is three (representing values 100 through 255).</span></span>  
  
### <a name="default-field-lengths-for-native-file-storage"></a><span data-ttu-id="b2fea-164">Standardfeldlänge zum Speichern systemeigener Dateien</span><span class="sxs-lookup"><span data-stu-id="b2fea-164">Default Field Lengths for Native File Storage</span></span>  
 <span data-ttu-id="b2fea-165">In der folgenden Tabelle werden die Standardfeldlängen für Daten aufgeführt, die als Dateien im systemeigenen Format gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="b2fea-165">The following table lists the default field lengths for data to be stored as native file storage type.</span></span> <span data-ttu-id="b2fea-166">Daten, die NULL zulassen, weisen die gleiche Länge auf wie Daten ohne NULL-Werte. Zeichendaten werden immer im Zeichenformat gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b2fea-166">Nullable data is the same length as nonnull data, and character data is always stored in character format.</span></span>  
  
|<span data-ttu-id="b2fea-167">Datentyp</span><span class="sxs-lookup"><span data-stu-id="b2fea-167">Data type</span></span>|<span data-ttu-id="b2fea-168">Standardlänge (Zeichen)</span><span class="sxs-lookup"><span data-stu-id="b2fea-168">Default length (characters)</span></span>|  
|---------------|-----------------------------------|  
|`bit`|<span data-ttu-id="b2fea-169">1</span><span class="sxs-lookup"><span data-stu-id="b2fea-169">1</span></span>|  
|`binary`|<span data-ttu-id="b2fea-170">Für die Spalte definierte Länge</span><span class="sxs-lookup"><span data-stu-id="b2fea-170">Length defined for the column</span></span>|  
|`varbinary`|<span data-ttu-id="b2fea-171">Für die Spalte definierte Länge</span><span class="sxs-lookup"><span data-stu-id="b2fea-171">Length defined for the column</span></span>|  
|`image`|<span data-ttu-id="b2fea-172">0</span><span class="sxs-lookup"><span data-stu-id="b2fea-172">0</span></span>|  
|`datetime`|<span data-ttu-id="b2fea-173">8</span><span class="sxs-lookup"><span data-stu-id="b2fea-173">8</span></span>|  
|`smalldatetime`|<span data-ttu-id="b2fea-174">4</span><span class="sxs-lookup"><span data-stu-id="b2fea-174">4</span></span>|  
|`float`|<span data-ttu-id="b2fea-175">8</span><span class="sxs-lookup"><span data-stu-id="b2fea-175">8</span></span>|  
|`real`|<span data-ttu-id="b2fea-176">4</span><span class="sxs-lookup"><span data-stu-id="b2fea-176">4</span></span>|  
|`int`|<span data-ttu-id="b2fea-177">4</span><span class="sxs-lookup"><span data-stu-id="b2fea-177">4</span></span>|  
|`bigint`|<span data-ttu-id="b2fea-178">8</span><span class="sxs-lookup"><span data-stu-id="b2fea-178">8</span></span>|  
|`smallint`|<span data-ttu-id="b2fea-179">2</span><span class="sxs-lookup"><span data-stu-id="b2fea-179">2</span></span>|  
|`tinyint`|<span data-ttu-id="b2fea-180">1</span><span class="sxs-lookup"><span data-stu-id="b2fea-180">1</span></span>|  
|`money`|<span data-ttu-id="b2fea-181">8</span><span class="sxs-lookup"><span data-stu-id="b2fea-181">8</span></span>|  
|`smallmoney`|<span data-ttu-id="b2fea-182">4</span><span class="sxs-lookup"><span data-stu-id="b2fea-182">4</span></span>|  
|<span data-ttu-id="b2fea-183">`decimal` <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b2fea-183">`decimal` <sup>1</sup></span></span>|<sup>*</sup>|  
|<span data-ttu-id="b2fea-184">`numeric` <sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b2fea-184">`numeric` <sup>1</sup></span></span>|<sup>*</sup>|  
|`uniqueidentifier`|<span data-ttu-id="b2fea-185">16</span><span class="sxs-lookup"><span data-stu-id="b2fea-185">16</span></span>|  
|`timestamp`|<span data-ttu-id="b2fea-186">8</span><span class="sxs-lookup"><span data-stu-id="b2fea-186">8</span></span>|  
  
 <span data-ttu-id="b2fea-187"><sup>1</sup> Weitere Informationen zu den `decimal` `numeric` Datentypen und finden Sie unter [Decimal und numeric &#40;Transact-SQL-&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="b2fea-187"><sup>1</sup> For more information about the `decimal` and `numeric` data types, see [decimal and numeric &#40;Transact-SQL&#41;](/sql/t-sql/data-types/decimal-and-numeric-transact-sql).</span></span>  
  
 <span data-ttu-id="b2fea-188">Wenn Sie eine Datendatei erstellen, die später erneut in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] geladen werden soll, und dabei den Speicherplatz auf ein Minimum begrenzen möchten, sollten Sie ein Längenpräfix mit dem Standard-Dateispeichertyp und der Standardfeldlänge verwenden. Dies gilt für jeden der vorangegangenen Fälle.</span><span class="sxs-lookup"><span data-stu-id="b2fea-188">In all of the preceding cases, to create a data file for later reloading into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that keeps the storage space to a minimum, use a length prefix with the default file storage type and the default field length.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2fea-189">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2fea-189">See Also</span></span>  
 <span data-ttu-id="b2fea-190">[bcp (Hilfsprogramm)](../../tools/bcp-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b2fea-190">[bcp Utility](../../tools/bcp-utility.md) </span></span>  
 <span data-ttu-id="b2fea-191">[Datentypen &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="b2fea-191">[Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql) </span></span>  
 <span data-ttu-id="b2fea-192">[Angeben von Feld- und Zeilenabschlusszeichen &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b2fea-192">[Specify Field and Row Terminators &#40;SQL Server&#41;](specify-field-and-row-terminators-sql-server.md) </span></span>  
 <span data-ttu-id="b2fea-193">[Angeben der Präfixlänge in Datendateien mittels bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b2fea-193">[Specify Prefix Length in Data Files by Using bcp &#40;SQL Server&#41;](specify-prefix-length-in-data-files-by-using-bcp-sql-server.md) </span></span>  
 <span data-ttu-id="b2fea-194">[Angeben des Dateispeichertyps mithilfe von bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b2fea-194">[Specify File Storage Type by Using bcp &#40;SQL Server&#41;](specify-file-storage-type-by-using-bcp-sql-server.md) </span></span>  
 [<span data-ttu-id="b2fea-195">Beibehalten von NULL-Werten oder Verwenden von Standardwerten während des Massenimports &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b2fea-195">Keep Nulls or Use Default Values During Bulk Import &#40;SQL Server&#41;</span></span>](keep-nulls-or-use-default-values-during-bulk-import-sql-server.md)  
  
  
