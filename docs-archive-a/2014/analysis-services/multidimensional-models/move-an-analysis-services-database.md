---
title: Verschieben einer Analysis Services Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- moving databases [Anlysis Services]
- moving databases
- operations [Analysis Services - multidimensional data]
ms.assetid: fa644e5d-e276-445e-98d9-673afcfb83fe
author: minewiskan
ms.author: owend
ms.openlocfilehash: bd9b099ad6765d9caccb9b0af6622eb4aa77d38c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724262"
---
# <a name="move-an-analysis-services-database"></a><span data-ttu-id="e237d-102">Verschieben einer Analysis Services Datenbank</span><span class="sxs-lookup"><span data-stu-id="e237d-102">Move an Analysis Services Database</span></span>
  <span data-ttu-id="e237d-103">Es gibt oftmals Situationen, in denen ein [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbankadministrator (DBA) eine mehrdimensionale oder tabellarische Modelldatenbank an einen anderen Speicherort verschieben möchte.</span><span class="sxs-lookup"><span data-stu-id="e237d-103">There are often situations when an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database administrator (dba) wants to move a multidimensional or tabular model database to a different location.</span></span> <span data-ttu-id="e237d-104">Diese Situationen hängen in der Regel von Geschäftsforderungen ab, z. B. wenn die Datenbank zur Leistungssteigerung auf einen anderen Datenträger verschoben werden soll, wenn bei Datenbankzuwachs Platz geschaffen werden muss oder wenn ein Produkt aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e237d-104">These situations are often driven by business needs, such as moving the database to a different disk for better performance, gaining room for database growth, or to upgrade a product.</span></span>  
  
 <span data-ttu-id="e237d-105">Es stehen zahlreiche Möglichkeiten zum Verschieben einer Datenbank zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e237d-105">A database can be moved in many ways.</span></span> <span data-ttu-id="e237d-106">In diesem Dokument werden die folgenden gängigen Szenarien erläutert:</span><span class="sxs-lookup"><span data-stu-id="e237d-106">This document explains the following common scenarios:</span></span>  
  
-   <span data-ttu-id="e237d-107">Interaktiv mithilfe von SSMS</span><span class="sxs-lookup"><span data-stu-id="e237d-107">Interactively using SSMS</span></span>  
  
-   <span data-ttu-id="e237d-108">Programmgesteuert mithilfe von AMO</span><span class="sxs-lookup"><span data-stu-id="e237d-108">Programmatically using AMO</span></span>  
  
-   <span data-ttu-id="e237d-109">Mit einem Skript mithilfe von XMLA</span><span class="sxs-lookup"><span data-stu-id="e237d-109">By script using XMLA</span></span>  
  
 <span data-ttu-id="e237d-110">In allen Szenarien muss der Benutzer auf den Datenbankordner zugreifen und eine Methode zum Verschieben der Dateien an das gewünschte endgültige Ziel verwenden.</span><span class="sxs-lookup"><span data-stu-id="e237d-110">All scenarios require the user to access the database folder and to use a method for moving the files to the desired final destination.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e237d-111">Wenn Sie eine Datenbank trennen, ohne ihr ein Kennwort zuzuweisen, befindet sich die Datenbank in einem ungesicherten Zustand.</span><span class="sxs-lookup"><span data-stu-id="e237d-111">Detaching a database without assigning a password to it leaves the database in an unsecured state.</span></span> <span data-ttu-id="e237d-112">Es wird daher empfohlen, dass Sie der Datenbank ein Kennwort zuweisen, um vertrauliche Informationen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="e237d-112">We recommend assigning a password to the database to protect confidential information.</span></span> <span data-ttu-id="e237d-113">Zudem sollten Sie die entsprechende Zugriffssicherheit auf den Datenbankordner, die Unterordner und die Dateien anwenden, um den nicht autorisierten Zugriff darauf zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="e237d-113">Also, the corresponding access security should be applied to the database folder, sub-folders, and files to prevent unauthorized access to them.</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="e237d-114">Prozeduren</span><span class="sxs-lookup"><span data-stu-id="e237d-114">Procedures</span></span>  
  
#### <a name="moving-a-database-interactively-using-ssms"></a><span data-ttu-id="e237d-115">Interaktives Verschieben einer Datenbank mithilfe von SSMS</span><span class="sxs-lookup"><span data-stu-id="e237d-115">Moving a database interactively using SSMS</span></span>  
  
1.  <span data-ttu-id="e237d-116">Suchen Sie im linken oder rechten Bereich von SSMS nach der zu verschiebenden Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e237d-116">Locate the database to be moved in the left or right pane of SSMS.</span></span>  
  
2.  <span data-ttu-id="e237d-117">Klicken Sie mit der rechten Maustaste auf die Datenbank, und wählen Sie **trennen... aus.**</span><span class="sxs-lookup"><span data-stu-id="e237d-117">Right-click on the database and select **Detach...**</span></span>  
  
3.  <span data-ttu-id="e237d-118">Weisen Sie der Datenbank, die getrennt werden soll, ein Kennwort zu, und klicken Sie dann auf **OK** , um den Befehl zum Trennen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e237d-118">Assign a password to the database to be detached, then click **OK** to execute the detach command.</span></span>  
  
4.  <span data-ttu-id="e237d-119">Verwenden Sie einen Mechanismus des Betriebssystems oder eine Standardmethode zum Verschieben des Datenbankordners an einen neuen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="e237d-119">Use any operating system mechanism or your standard method for moving files to move the database folder to the new location.</span></span>  
  
5.  <span data-ttu-id="e237d-120">Suchen Sie im linken oder rechten Bereich von SSMS nach dem Ordner **Datenbanken** .</span><span class="sxs-lookup"><span data-stu-id="e237d-120">Locate the **Databases** folder in the left or right pane of SSMS.</span></span>  
  
6.  <span data-ttu-id="e237d-121">Klicken Sie mit der rechten Maustaste auf den Ordner **Datenbanken** , und wählen Sie **Anfügen aus.**</span><span class="sxs-lookup"><span data-stu-id="e237d-121">Right-click on the **Databases** folder and select **Attach...**</span></span>  
  
7.  <span data-ttu-id="e237d-122">Geben Sie im Textfeld **Ordner** den neuen Speicherort des Datenbankordners ein.</span><span class="sxs-lookup"><span data-stu-id="e237d-122">In the **folder** text box, type the new location of the database folder.</span></span> <span data-ttu-id="e237d-123">Alternativ können Sie mit der Schaltfläche zum Durchsuchen (**...**) nach dem Daten Bank Ordner suchen.</span><span class="sxs-lookup"><span data-stu-id="e237d-123">Alternatively, you can use the browse button (**...**) to locate the database folder.</span></span>  
  
8.  <span data-ttu-id="e237d-124">Wählen Sie den `ReadWrite` Modus für die Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="e237d-124">Select the `ReadWrite` mode for the database.</span></span>  
  
9. <span data-ttu-id="e237d-125">Geben Sie das in Schritt 3 verwendete Kennwort ein, und klicken Sie auf **OK** , um den Befehl zum Anfügen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e237d-125">Type the password used in step 3 and click **OK** to execute the attach command.</span></span>  
  
#### <a name="moving-a-database-programmatically-using-amo"></a><span data-ttu-id="e237d-126">Programmgesteuertes Verschieben einer Datenbank mithilfe von AMO</span><span class="sxs-lookup"><span data-stu-id="e237d-126">Moving a database programmatically using AMO</span></span>  
  
1.  <span data-ttu-id="e237d-127">Passen Sie in der C#-Anwendung den folgenden Beispielcode an, und führen Sie die angegebenen Aufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="e237d-127">In your C# application, adapt the following sample code and complete the indicated tasks.</span></span>  
  
 `private void MoveDb(Server server, string dbName,`  
  
 `string dbInitialLocation, string dbFinalLocation,`  
  
 `string dbPassword, ReadWriteMode dbReadWriteMode)`  
  
 `{`  
  
 `//Verify dbInitialLocation exists before continuing`  
  
 `if (server.Databases.ContainsName(dbName))`  
  
 `{`  
  
 `Database db;`  
  
 `//Save current cursor and change cursor to Cursors.WaitCursor`  
  
 `db = server.Databases[dbName];`  
  
 `db.Detach(dbPassword);`  
  
 `//Add your own code to copy the database files to the destination where you intend to attach the database`  
  
 `//Verify dbFinalLocation exists before continuing`  
  
 `server.Attach(dbFinalLocation, dbReadWriteMode, dbPassword);`  
  
 `//Restore cursor to its original`  
  
 `}`  
  
 `}`  
  
1.  <span data-ttu-id="e237d-128">Rufen Sie in der C#-Anwendung `MoveDb()` mit den erforderlichen Parametern auf.</span><span class="sxs-lookup"><span data-stu-id="e237d-128">In your C# application, invoke `MoveDb()` with the necessary parameters.</span></span>  
  
2.  <span data-ttu-id="e237d-129">Kompilieren Sie den Code, und führen Sie ihn zum Verschieben der Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="e237d-129">Compile and execute your code to move the database.</span></span>  
  
#### <a name="moving-a-database-by-script-using-xmla"></a><span data-ttu-id="e237d-130">Verschieben einer Datenbank mit einem Skript mithilfe von XMLA</span><span class="sxs-lookup"><span data-stu-id="e237d-130">Moving a database by script using XMLA</span></span>  
  
1.  <span data-ttu-id="e237d-131">Öffnen Sie in SSMS eine neue XMLA-Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="e237d-131">Open a new XMLA tab in SSMS.</span></span>  
  
2.  <span data-ttu-id="e237d-132">Kopieren Sie die folgende Skriptvorlage für XMLA:</span><span class="sxs-lookup"><span data-stu-id="e237d-132">Copy the following script template for XMLA</span></span>  
  
 `<Detach xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">`  
  
 `<Object>`  
  
 `<DatabaseID>%dbName%</DatabaseID>`  
  
 `<Password>%password%</Password>`  
  
 `</Object>`  
  
 `</Detach>`  
  
1.  <span data-ttu-id="e237d-133">Ersetzen Sie `%dbName%` durch den Namen der Datenbank und `%password%` durch das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="e237d-133">Replace `%dbName%` with the name of the database and `%password%` with the password.</span></span> <span data-ttu-id="e237d-134">Die %-Zeichen sind Teil der Vorlage und müssen entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="e237d-134">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="e237d-135">Führen Sie den XMLA-Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="e237d-135">Execute the XMLA command.</span></span>  
  
3.  <span data-ttu-id="e237d-136">Verwenden Sie einen Mechanismus des Betriebssystems oder eine Standardmethode zum Verschieben des Datenbankordners an einen neuen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="e237d-136">Use any operating system mechanism or your standard method for moving files to move the database folder to the new location.</span></span>  
  
4.  <span data-ttu-id="e237d-137">Kopieren Sie die folgende Skriptvorlage für XMLA in eine neue XMLA-Registerkarte:</span><span class="sxs-lookup"><span data-stu-id="e237d-137">Copy the following script template for XMLA in a new XMLA tab</span></span>  
  
 `<Attach xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">`  
  
 `<Folder>%dbFolder%</Folder>`  
  
 `<ReadWriteMode xmlns="https://schemas.microsoft.com/analysisservices/2008/engine/100">%ReadOnlyMode%</ReadWriteMode>`  
  
 `</Attach>`  
  
1.  <span data-ttu-id="e237d-138">Ersetzen Sie `%dbFolder%` durch den vollständigen UNC-Pfad des Datenbankordners, `%ReadOnlyMode%` durch den entsprechenden Wert `ReadOnly` oder `ReadWrite` und `%password%` durch das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="e237d-138">Replace `%dbFolder%` with the complete UNC path of the database folder, `%ReadOnlyMode%` with the corresponding value `ReadOnly` or `ReadWrite`, and `%password%` with the password.</span></span> <span data-ttu-id="e237d-139">Die %-Zeichen sind Teil der Vorlage und müssen entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="e237d-139">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="e237d-140">Führen Sie den XMLA-Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="e237d-140">Execute the XMLA command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e237d-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e237d-141">See Also</span></span>  
 <xref:Microsoft.AnalysisServices.Server.Attach%2A>   
 <span data-ttu-id="e237d-142">[Microsoft. AnalysisServices. Database. Detach \*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span><span class="sxs-lookup"><span data-stu-id="e237d-142">[Microsoft.AnalysisServices.Database.Detach\*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span></span>  
 <span data-ttu-id="e237d-143">[Anfügen und trennen von Analysis Services Datenbanken](attach-and-detach-analysis-services-databases.md) </span><span class="sxs-lookup"><span data-stu-id="e237d-143">[Attach and Detach Analysis Services Databases](attach-and-detach-analysis-services-databases.md) </span></span>  
 <span data-ttu-id="e237d-144">[Daten Bank Speicherort](database-storage-location.md) </span><span class="sxs-lookup"><span data-stu-id="e237d-144">[Database Storage Location](database-storage-location.md) </span></span>  
 <span data-ttu-id="e237d-145">[Datenbanklesemodusmodi](database-readwritemodes.md) </span><span class="sxs-lookup"><span data-stu-id="e237d-145">[Database ReadWriteModes](database-readwritemodes.md) </span></span>  
 <span data-ttu-id="e237d-146">[Attach-Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span><span class="sxs-lookup"><span data-stu-id="e237d-146">[Attach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span></span>  
 <span data-ttu-id="e237d-147">[Detach-Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span><span class="sxs-lookup"><span data-stu-id="e237d-147">[Detach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span></span>  
 <span data-ttu-id="e237d-148">["Read Write-Mode"-Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span><span class="sxs-lookup"><span data-stu-id="e237d-148">[ReadWriteMode Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span></span>  
 [<span data-ttu-id="e237d-149">DbStorageLocation-Element</span><span class="sxs-lookup"><span data-stu-id="e237d-149">DbStorageLocation Element</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/dbstoragelocation-element)  
  
  
