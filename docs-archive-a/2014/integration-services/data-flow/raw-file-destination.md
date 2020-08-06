---
title: Rohdatendatei-Ziel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.rawfiledest.f1
helpviewer_keywords:
- append options [Integration Services]
- destinations [Integration Services], Raw File
- raw data [Integration Services]
- writing raw data
- Raw File destination
ms.assetid: d311b458-aefc-4b4d-b1a1-4c0ebbb34214
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fc5ce99be6e467ba323137ef885cbb13bfb328ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615463"
---
# <a name="raw-file-destination"></a><span data-ttu-id="222cb-102">Raw File Destination</span><span class="sxs-lookup"><span data-stu-id="222cb-102">Raw File Destination</span></span>
  <span data-ttu-id="222cb-103">Das Rohdatendatei-Ziel schreibt Rohdaten in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="222cb-103">The Raw File destination writes raw data to a file.</span></span> <span data-ttu-id="222cb-104">Die Daten liegen im systemeigenen Zielformat vor, sodass die Daten nicht übersetzt und kaum analysiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="222cb-104">Because the format of the data is native to the destination, the data requires no translation and little parsing.</span></span> <span data-ttu-id="222cb-105">Dies bedeutet, dass das Rohdatendatei-Ziel Daten schneller als andere Ziele, wie z. B. Flatfile- und OLE DB-Ziele, schreiben kann.</span><span class="sxs-lookup"><span data-stu-id="222cb-105">This means that the Raw File destination can write data more quickly than other destinations such as the Flat File and the OLE DB destinations.</span></span>  
  
 <span data-ttu-id="222cb-106">Zusätzlich zur Option, Rohdatendateien in eine Datei schreiben zu können, können Sie auch das Rohdatendatei-Ziel verwenden, um eine leere Rohdatendatei zu generieren, die nur die Spalten (Nur-Metadatendatei) enthält, ohne dass das Paket ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="222cb-106">In addition to writing raw data to a file, you can also use the Raw File destination to generate an empty raw file that contains only the columns (metadata-only file), without having to run the package.</span></span> <span data-ttu-id="222cb-107">Mithilfe der Rohdatendatei-Quelle werden Rohdaten abgerufen, die zuvor vom Ziel geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="222cb-107">You use the Raw File source to retrieve raw data that was previously written by the destination.</span></span> <span data-ttu-id="222cb-108">Sie können die Rohdatendatei-Quelle zudem auf die Nur-Metadaten-Datei verweisen.</span><span class="sxs-lookup"><span data-stu-id="222cb-108">You can also point the Raw File source to the metadata-only file.</span></span>  
  
 <span data-ttu-id="222cb-109">Das Format der Rohdatendatei enthält Sortierungsinformationen:</span><span class="sxs-lookup"><span data-stu-id="222cb-109">The raw file format contains sort information.</span></span> <span data-ttu-id="222cb-110">Das Rohdatendatei-Ziel speichert alle Sortierungsinformationen, einschließlich der Vergleichsflags für Zeichenfolgenspalten.</span><span class="sxs-lookup"><span data-stu-id="222cb-110">The Raw File Destination saves all the sort information including the comparison flags for string columns.</span></span> <span data-ttu-id="222cb-111">Die Rohdatendatei-Quelle liest und beachtet die Sortierungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="222cb-111">The Raw File source reads and honors the sort information.</span></span> <span data-ttu-id="222cb-112">Sie können die Rohdatendatei-Quelle dergestalt konfigurieren, dass die Sortierflags in der Datei mit dem erweiterten Editor ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="222cb-112">You do have the option of configuring the Raw File Source to ignore the sort flags in the file, using the Advanced Editor.</span></span> <span data-ttu-id="222cb-113">Weitere Informationen zu Vergleichsflags finden Sie unter [Comparing String Data](comparing-string-data.md).</span><span class="sxs-lookup"><span data-stu-id="222cb-113">For more information about comparison flags, see [Comparing String Data](comparing-string-data.md).</span></span>  
  
 <span data-ttu-id="222cb-114">Es gibt folgende Möglichkeiten, um das Rohdatendatei-Ziel zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="222cb-114">You can configure the Raw File destination in the following ways:</span></span>  
  
-   <span data-ttu-id="222cb-115">Geben Sie einen Zugriffsmodus an, wobei es sich entweder um den Namen der Datei oder eine Variable handelt, die den Namen der Datei enthält, in die das Rohdatendatei-Ziel schreibt.</span><span class="sxs-lookup"><span data-stu-id="222cb-115">Specify an access mode which is either the name of the file or a variable that contains the name of the file to which the Raw File destination writes.</span></span>  
  
-   <span data-ttu-id="222cb-116">Geben Sie an, ob das Rohdatendatei-Ziel Daten an eine vorhandene gleichnamige Datei anfügt oder eine neue Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="222cb-116">Indicate whether the Raw File destination appends data to an existing file that has the same name or creates a new file.</span></span>  
  
 <span data-ttu-id="222cb-117">Das Rohdatendatei-Ziel wird häufig zum Schreiben von Zwischenergebnissen teilweise verarbeiteter Daten zwischen Paketausführungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="222cb-117">The Raw File destination is frequently used to write intermediary results of partly processed data between package executions.</span></span> <span data-ttu-id="222cb-118">Das Speichern von Rohdatendateien bedeutet, dass die Daten schnell von einer Rohdatendatei-Quelle gelesen und dann weiter transformiert werden können, bevor sie in das endgültige Ziel geladen werden.</span><span class="sxs-lookup"><span data-stu-id="222cb-118">Storing raw data means that the data can be read quickly by a Raw File source and then further transformed before it is loaded into its final destination.</span></span> <span data-ttu-id="222cb-119">Beispielsweise kann ein Paket mehrmals ausgeführt werden, wobei jedes Mal Rohdaten in Dateien geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="222cb-119">For example, a package might run several times, and each time write raw data to files.</span></span> <span data-ttu-id="222cb-120">Später kann ein anderes Paket die Rohdatendatei-Quelle zum Lesen aus jeder Datei verwenden und mit einer Transformation für UNION ALL die Daten zu einem einzigen Dataset zusammenführen. Dann kann das Paket zusätzliche Transformationen anwenden, mit denen die Daten zusammengefasst werden, bevor sie in das endgültige Ziel, z. B. eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tabelle, geladen werden.</span><span class="sxs-lookup"><span data-stu-id="222cb-120">Later, a different package can use the Raw File source to read from each file, use a Union All transformation to merge the data into one data set, and then apply additional transformations that summarize the data before loading the data into its final destination such as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="222cb-121">Das Rohdatendatei-Ziel unterstützt NULL-Werte, aber keine BLOB-Daten (Binary Large Object).</span><span class="sxs-lookup"><span data-stu-id="222cb-121">The Raw File destination supports null data but not binary large object (BLOB) data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="222cb-122">Für das Rohdatendatei-Ziel wird kein Verbindungs-Manager verwendet.</span><span class="sxs-lookup"><span data-stu-id="222cb-122">The Raw File destination does not use a connection manager.</span></span>  
  
 <span data-ttu-id="222cb-123">Diese Quelle hat nur eine reguläre Eingabe.</span><span class="sxs-lookup"><span data-stu-id="222cb-123">This source has one regular input.</span></span> <span data-ttu-id="222cb-124">Eine Fehlerausgabe wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="222cb-124">It does not support an error output.</span></span>  
  
## <a name="append-and-new-file-options"></a><span data-ttu-id="222cb-125">Optionen zum Anfügen und zum Erstellen einer neuen Datei</span><span class="sxs-lookup"><span data-stu-id="222cb-125">Append and New File Options</span></span>  
 <span data-ttu-id="222cb-126">Die „WriteOption“-Eigenschaft schließt Optionen zum Anfügen von Daten an eine vorhandene Datei oder zum Erstellen einer neuen Datei ein.</span><span class="sxs-lookup"><span data-stu-id="222cb-126">The WriteOption property includes options to append data to an existing file or create a new file.</span></span>  
  
 <span data-ttu-id="222cb-127">In der folgenden Tabelle werden die verfügbaren Optionen für die „WriteOption“-Eigenschaft beschrieben.</span><span class="sxs-lookup"><span data-stu-id="222cb-127">The following table describes the available options for the WriteOption property.</span></span>  
  
|<span data-ttu-id="222cb-128">Option</span><span class="sxs-lookup"><span data-stu-id="222cb-128">Option</span></span>|<span data-ttu-id="222cb-129">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="222cb-129">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="222cb-130">Anfügen</span><span class="sxs-lookup"><span data-stu-id="222cb-130">Append</span></span>|<span data-ttu-id="222cb-131">Fügt Daten an eine vorhandene Datei an.</span><span class="sxs-lookup"><span data-stu-id="222cb-131">Appends data to an existing file.</span></span> <span data-ttu-id="222cb-132">Die Metadaten der angefügten Daten müssen mit dem Dateiformat übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="222cb-132">The metadata of the appended data must match the file format.</span></span>|  
|<span data-ttu-id="222cb-133">Immer erstellen</span><span class="sxs-lookup"><span data-stu-id="222cb-133">Create always</span></span>|<span data-ttu-id="222cb-134">Erstellt immer eine neue Datei.</span><span class="sxs-lookup"><span data-stu-id="222cb-134">Always creates a new file.</span></span>|  
|<span data-ttu-id="222cb-135">Einmal erstellen</span><span class="sxs-lookup"><span data-stu-id="222cb-135">Create once</span></span>|<span data-ttu-id="222cb-136">Erstellt eine neue Datei.</span><span class="sxs-lookup"><span data-stu-id="222cb-136">Creates a new file.</span></span> <span data-ttu-id="222cb-137">Wenn die Datei vorhanden ist, ist die Komponente fehlerhaft.</span><span class="sxs-lookup"><span data-stu-id="222cb-137">If the file exists, the component fails.</span></span>|  
|<span data-ttu-id="222cb-138">Abschneiden und anfügen</span><span class="sxs-lookup"><span data-stu-id="222cb-138">Truncate and append</span></span>|<span data-ttu-id="222cb-139">Schneidet eine vorhandene Datei ab und schreibt dann die Daten in die Datei.</span><span class="sxs-lookup"><span data-stu-id="222cb-139">Truncates an existing file and then writes the data to the file.</span></span> <span data-ttu-id="222cb-140">Die Metadaten der angefügten Daten müssen mit dem Dateiformat übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="222cb-140">The metadata of the appended data must match the file format.</span></span>|  
  
 <span data-ttu-id="222cb-141">Im Folgenden finden Sie wichtige Elemente über das Anfügen von Daten:</span><span class="sxs-lookup"><span data-stu-id="222cb-141">The following are important items about appending data:</span></span>  
  
-   <span data-ttu-id="222cb-142">Durch das Anfügen von Daten an eine vorhandene Rohdatendatei werden die Daten nicht erneut sortiert.</span><span class="sxs-lookup"><span data-stu-id="222cb-142">Appending data to an existing raw file does not re-sort the data.</span></span>  
  
     <span data-ttu-id="222cb-143">Sie müssen sicherstellen, dass die sortierten Schlüssel in der richtigen Reihenfolge bleiben.</span><span class="sxs-lookup"><span data-stu-id="222cb-143">You need to make certain that the sorted keys remain in the correct order.</span></span>  
  
-   <span data-ttu-id="222cb-144">Durch das Anfügen von Daten an eine vorhandene Rohdatendatei werden die Dateimetadaten (Sortierungsinformationen) nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="222cb-144">Appending data to an existing raw file does not change the file metadata (sort information).</span></span>  
  
 <span data-ttu-id="222cb-145">Beispielsweise liest ein Paket im ProductKey (PK) sortierte Daten.</span><span class="sxs-lookup"><span data-stu-id="222cb-145">For example, a package reads data sorted on the ProductKey (PK).</span></span> <span data-ttu-id="222cb-146">Der Paketdatenfluss fügt die Daten an eine vorhandene Rohdatendatei an.</span><span class="sxs-lookup"><span data-stu-id="222cb-146">The package data flow appends the data to an existing raw file.</span></span> <span data-ttu-id="222cb-147">Bei der ersten Ausführung des Pakets werden drei Zeilen (PK 1000, 1100, 1200) empfangen.</span><span class="sxs-lookup"><span data-stu-id="222cb-147">The first time the package runs, three rows are received (PK 1000, 1100, 1200).</span></span> <span data-ttu-id="222cb-148">Die Rohdatendatei enthält nun die folgenden Daten.</span><span class="sxs-lookup"><span data-stu-id="222cb-148">The raw file now contains the following data.</span></span>  
  
-   <span data-ttu-id="222cb-149">1000, productA</span><span class="sxs-lookup"><span data-stu-id="222cb-149">1000, productA</span></span>  
  
-   <span data-ttu-id="222cb-150">1100, productB</span><span class="sxs-lookup"><span data-stu-id="222cb-150">1100, productB</span></span>  
  
-   <span data-ttu-id="222cb-151">1200, productC</span><span class="sxs-lookup"><span data-stu-id="222cb-151">1200, productC</span></span>  
  
 <span data-ttu-id="222cb-152">Bei der zweiten Ausführung des Pakets werden zwei neue Zeilen (PK 1001, 1300) empfangen.</span><span class="sxs-lookup"><span data-stu-id="222cb-152">The second time the package runs, two new rows are received (PK 1001, 1300).</span></span> <span data-ttu-id="222cb-153">Die Rohdatendatei enthält nun die folgenden Daten.</span><span class="sxs-lookup"><span data-stu-id="222cb-153">The raw file now contains the following data.</span></span>  
  
-   <span data-ttu-id="222cb-154">1000, productA</span><span class="sxs-lookup"><span data-stu-id="222cb-154">1000, productA</span></span>  
  
-   <span data-ttu-id="222cb-155">1100, productB</span><span class="sxs-lookup"><span data-stu-id="222cb-155">1100, productB</span></span>  
  
-   <span data-ttu-id="222cb-156">1200, productC</span><span class="sxs-lookup"><span data-stu-id="222cb-156">1200, productC</span></span>  
  
-   <span data-ttu-id="222cb-157">1001, productD</span><span class="sxs-lookup"><span data-stu-id="222cb-157">1001, productD</span></span>  
  
-   <span data-ttu-id="222cb-158">1300, productE</span><span class="sxs-lookup"><span data-stu-id="222cb-158">1300, productE</span></span>  
  
 <span data-ttu-id="222cb-159">Die neuen Daten werden an das Ende der Rohdatendatei angefügt, und die sortierten Schlüssel (PK) werden nicht mehr verwendet.</span><span class="sxs-lookup"><span data-stu-id="222cb-159">The new data is appended to the end of the raw file, and the sorted keys (PK) are out of order.</span></span> <span data-ttu-id="222cb-160">Zusätzlich werden die Dateimetadaten (Sortierungsinformationen) nicht durch den Anfügevorgang verändert.</span><span class="sxs-lookup"><span data-stu-id="222cb-160">In addition, the append operation didn't change the file metadata (sort information).</span></span> <span data-ttu-id="222cb-161">Wenn Sie die Datei mit der Rohdatendatei-Quelle lesen, gibt die Komponente an, dass die Datei immer noch nach PK sortiert ist, obwohl die Daten in der Datei nicht mehr in der richtigen Reihenfolge sind.</span><span class="sxs-lookup"><span data-stu-id="222cb-161">If you read the file by using the Raw File source, the component indicates that the file is still sorted on PK even though the data in the file is no longer in the correct order.</span></span>  
  
 <span data-ttu-id="222cb-162">Um die sortierten Schlüssel in der richtigen Reihenfolge zu behalten, während Daten angefügt werden, können Sie den Paketdatenfluss wie folgt entwerfen:</span><span class="sxs-lookup"><span data-stu-id="222cb-162">To keep the sorted keys in the correct order while appending data, you can design the package data flow as follows:</span></span>  
  
1.  <span data-ttu-id="222cb-163">Rufen Sie neue Zeilen mit Quelle A ab.</span><span class="sxs-lookup"><span data-stu-id="222cb-163">Retrieve new rows by using Source A.</span></span>  
  
2.  <span data-ttu-id="222cb-164">Rufen Sie vorhandene Zeilen mit Quelle B aus RawFile1 ab.</span><span class="sxs-lookup"><span data-stu-id="222cb-164">Retrieve existing rows from RawFile1 using Source B.</span></span>  
  
3.  <span data-ttu-id="222cb-165">Kombinieren Sie die Eingaben von Quelle A und B mit der Transformation für UNION ALL.</span><span class="sxs-lookup"><span data-stu-id="222cb-165">Combine the inputs from Source A and Source B by using the Union All transformation.</span></span>  
  
4.  <span data-ttu-id="222cb-166">Sortierung nach PK.</span><span class="sxs-lookup"><span data-stu-id="222cb-166">Sort on PK.</span></span>  
  
5.  <span data-ttu-id="222cb-167">Schreiben Sie in RawFile2 mit dem Rohdatendatei-Ziel.</span><span class="sxs-lookup"><span data-stu-id="222cb-167">Write to RawFile2 by using the Raw File destination.</span></span>  
  
     <span data-ttu-id="222cb-168">RawFile1 wird gesperrt, da die Datei im Datenfluss gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="222cb-168">RawFile1 is locked because it's being read from, in the data flow.</span></span>  
  
6.  <span data-ttu-id="222cb-169">Ersetzen Sie RawFile1 durch RawFile2.</span><span class="sxs-lookup"><span data-stu-id="222cb-169">Replace RawFile1 with RawFile2.</span></span>  
  
### <a name="using-the-raw-file-destination-in-a-loop"></a><span data-ttu-id="222cb-170">Verwenden des Rohdatendatei-Ziels in einer Schleife</span><span class="sxs-lookup"><span data-stu-id="222cb-170">Using the Raw File Destination in a Loop</span></span>  
 <span data-ttu-id="222cb-171">Wenn sich der Datenfluss, der das Rohdatendatei-Ziel verwendet, in einer Schleife befindet, wird die Datei möglicherweise einmal erstellt, und Daten werden an die Datei angefügt, wenn die Schleife wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="222cb-171">If the data flow that uses the Raw File destination is in a loop, you may want to create the file once and then append data to the file when the loop repeats.</span></span> <span data-ttu-id="222cb-172">Wenn die Daten an eine Datei angefügt werden, muss die anzufügende Datei mit dem Format der vorhandenen Datei übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="222cb-172">To append data to the file, the data that is appended must match the format of the existing file.</span></span>  
  
 <span data-ttu-id="222cb-173">Um die Datei in der ersten Iteration einer Schleife zu erstellen, und dann die Zeilen in der nachfolgenden Iteration der Schleife anzufügen, müssen Sie Folgendes zur Entwurfszeit ausführen:</span><span class="sxs-lookup"><span data-stu-id="222cb-173">To create the file in the first iteration of the loop, and then append rows in the subsequent iterations of the loop, you need to do the following at design time:</span></span>  
  
1.  <span data-ttu-id="222cb-174">Legen Sie die „WriteOption“-Eigenschaft auf **CreateOnce** oder **CreateAlways**fest, und führen Sie dann eine Iteration der Schleife aus.</span><span class="sxs-lookup"><span data-stu-id="222cb-174">Set the WriteOption property to **CreateOnce** or **CreateAlways**and run one iteration of the loop.</span></span> <span data-ttu-id="222cb-175">Die Datei ist erstellt.</span><span class="sxs-lookup"><span data-stu-id="222cb-175">The file is created.</span></span> <span data-ttu-id="222cb-176">Dadurch wird sichergestellt, dass die Metadaten der angefügten Daten mit der Datei übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="222cb-176">This ensures that the metadata of appended data and the file matches.</span></span>  
  
2.  <span data-ttu-id="222cb-177">Setzen Sie die Eigenschaft "Write Option" auf " **Append** " zurück, und legen Sie die Eigenschaft ValidateExternalMetadata auf fest `False` .</span><span class="sxs-lookup"><span data-stu-id="222cb-177">Reset the WriteOption property to **Append** and set the ValidateExternalMetadata property to `False`.</span></span>  
  
 <span data-ttu-id="222cb-178">Wenn Sie die Option **TruncateAppend** statt der Option **Append** verwenden, werden die Zeilen abgeschnitten, die in einer vorherigen Iteration hinzugefügt wurden, und dann neue Zeilen angefügt.</span><span class="sxs-lookup"><span data-stu-id="222cb-178">If you use the **TruncateAppend** option instead of the **Append** option, it will truncate rows that were added in any previous iteration, and then append new rows.</span></span> <span data-ttu-id="222cb-179">Das Verwenden der Option **TruncateAppend** erfordert auch, dass die Daten im Dateiformat übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="222cb-179">Using the **TruncateAppend** option also requires that the data matches the file format.</span></span>  
  
## <a name="configuration-of-the-raw-file-destination"></a><span data-ttu-id="222cb-180">Konfiguration des Rohdatendatei-Ziels</span><span class="sxs-lookup"><span data-stu-id="222cb-180">Configuration of the Raw File Destination</span></span>  
 <span data-ttu-id="222cb-181">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="222cb-181">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="222cb-182">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="222cb-182">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="222cb-183">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="222cb-183">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="222cb-184">Common Properties</span><span class="sxs-lookup"><span data-stu-id="222cb-184">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="222cb-185">Benutzerdefinierte Eigenschaften der Rohdatendatei</span><span class="sxs-lookup"><span data-stu-id="222cb-185">Raw File Custom Properties</span></span>](raw-file-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="222cb-186">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="222cb-186">Related Tasks</span></span>  
 <span data-ttu-id="222cb-187">Informationen zum Festlegen der Eigenschaften der Komponente finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="222cb-187">For information about how to set properties of the component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="222cb-188">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="222cb-188">Related Content</span></span>  
 <span data-ttu-id="222cb-189">Blogeintrag, [Raw Files Are Awesome](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131), auf sqlservercentral.com</span><span class="sxs-lookup"><span data-stu-id="222cb-189">Blog entry, [Raw Files Are Awesome](https://www.sqlservercentral.com/blogs/31-days-of-ssis-%e2%80%93-raw-files-are-awesome-131), on sqlservercentral.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="222cb-190">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="222cb-190">See Also</span></span>  
 <span data-ttu-id="222cb-191">[Rohdatendatei-Quelle](raw-file-source.md) </span><span class="sxs-lookup"><span data-stu-id="222cb-191">[Raw File Source](raw-file-source.md) </span></span>  
 [<span data-ttu-id="222cb-192">Datenfluss</span><span class="sxs-lookup"><span data-stu-id="222cb-192">Data Flow</span></span>](data-flow.md)  
  
  
