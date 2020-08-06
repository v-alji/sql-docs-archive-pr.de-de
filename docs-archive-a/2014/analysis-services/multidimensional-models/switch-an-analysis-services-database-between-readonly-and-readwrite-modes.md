---
title: Wechseln einer Analysis Services-Datenbank zwischen Schreib geschütztem Modus und Lese-/Schreibmodus | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- ReadOnly property
- ReadWriteMode command
- operations [Analysis Services - multidimensional data]
ms.assetid: 4eff8181-08dd-4fad-b091-d400fc21a020
author: minewiskan
ms.author: owend
ms.openlocfilehash: 757aedd985d969f932deacf5599716078021a1af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87694750"
---
# <a name="switch-an-analysis-services-database-between-readonly-and-readwrite-modes"></a><span data-ttu-id="63405-102">Umschalten einer Analysis Services-Datenbank zwischen schreibgeschütztem Modus und Lese-/Schreibmodus</span><span class="sxs-lookup"><span data-stu-id="63405-102">Switch an Analysis Services database between ReadOnly and ReadWrite modes</span></span>
  <span data-ttu-id="63405-103">In vielen Situationen muss vom [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Datenbankadministrator (DBA) der Lese-/Schreibmodus einer tabellarischen oder mehrdimensionalen Datenbank geändert werden.</span><span class="sxs-lookup"><span data-stu-id="63405-103">There are often situations when a [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database administrator (dba) wants to change the read/write mode of a tabular or multidimensional database.</span></span> <span data-ttu-id="63405-104">Diese Situationen hängen in der Regel von Geschäftsforderungen ab, z. B. der Freigabe der Datenbank für einen Pool von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Servern zur Vereinfachung der Nutzung.</span><span class="sxs-lookup"><span data-stu-id="63405-104">These situations are often driven by business needs, such as sharing the database among a pool of [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] servers for a better user experience.</span></span>  
  
 <span data-ttu-id="63405-105">Es stehen zahlreiche Möglichkeiten zum Umschalten des Datenbankmodus zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="63405-105">A database mode can be switched in many ways.</span></span> <span data-ttu-id="63405-106">In diesem Dokument werden die folgenden gängigen Szenarien erläutert:</span><span class="sxs-lookup"><span data-stu-id="63405-106">This document explains the following common scenarios:</span></span>  
  
-   <span data-ttu-id="63405-107">Interaktiv mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63405-107">Interactively using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]</span></span>  
  
-   <span data-ttu-id="63405-108">Programmgesteuert mithilfe von AMO</span><span class="sxs-lookup"><span data-stu-id="63405-108">Programmatically using AMO</span></span>  
  
-   <span data-ttu-id="63405-109">Mit einem Skript mithilfe von XMLA</span><span class="sxs-lookup"><span data-stu-id="63405-109">By script using XMLA</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="63405-110">Prozeduren</span><span class="sxs-lookup"><span data-stu-id="63405-110">Procedures</span></span>  
  
#### <a name="to-switch-the-readwrite-mode-of-a-database-interactively-using-management-studio"></a><span data-ttu-id="63405-111">So schalten Sie den Lese-/Schreibmodus einer Datenbank interaktiv mithilfe von Management Studio um</span><span class="sxs-lookup"><span data-stu-id="63405-111">To switch the read/write mode of a database interactively using Management Studio</span></span>  
  
1.  <span data-ttu-id="63405-112">Suchen Sie im linken oder rechten Bereich von [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] nach der umzuschaltenden Datenbank.</span><span class="sxs-lookup"><span data-stu-id="63405-112">Locate the database to be switched in the left or right pane of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="63405-113">Klicken Sie mit der rechten Maustaste auf die Datenbank, und wählen Sie **Eigenschaften**</span><span class="sxs-lookup"><span data-stu-id="63405-113">Right-click the database and select **Properties**.</span></span> <span data-ttu-id="63405-114">Suchen Sie den Datenbankordner, und notieren Sie sich den Speicherort.</span><span class="sxs-lookup"><span data-stu-id="63405-114">Find the database folder and note the location.</span></span> <span data-ttu-id="63405-115">Ein leerer Datenbankspeicherort weist darauf hin, dass sich der Datenbankordner im Datenordner des Servers befindet.</span><span class="sxs-lookup"><span data-stu-id="63405-115">An empty database storage location indicates that the database folder is located in the server data folder.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="63405-116">Sobald die Datenbank getrennt ist, kann [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Ihnen nicht mehr dabei helfen, den Datenbankspeicherort abzurufen.</span><span class="sxs-lookup"><span data-stu-id="63405-116">As soon as the database is detached, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] can no longer help you obtain the database location.</span></span>  
  
3.  <span data-ttu-id="63405-117">Klicken Sie mit der rechten Maustaste auf die Datenbank, und wählen Sie **trennen...**</span><span class="sxs-lookup"><span data-stu-id="63405-117">Right-click the database and select **Detach...**</span></span>  
  
4.  <span data-ttu-id="63405-118">Weisen Sie der Datenbank, die getrennt werden soll, ein Kennwort zu, und klicken Sie anschließend auf **OK** , um den Befehl zum Trennen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="63405-118">Assign a password to the database to be detached, and then click **OK** to execute the detach command.</span></span>  
  
5.  <span data-ttu-id="63405-119">Suchen Sie im linken oder rechten Bereich von nach dem Ordner **Datenbanken** [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="63405-119">Locate the **Databases** folder in the left or right pane of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
6.  <span data-ttu-id="63405-120">Klicken Sie mit der rechten Maustaste auf den Ordner **Datenbanken** , und wählen Sie **anhängen aus.**</span><span class="sxs-lookup"><span data-stu-id="63405-120">Right-click the **Databases** folder and select **Attach...**</span></span>  
  
7.  <span data-ttu-id="63405-121">Geben Sie im Textfeld **Ordner** den ursprünglichen Speicherort des Datenbankordners ein.</span><span class="sxs-lookup"><span data-stu-id="63405-121">In the **folder** text box, type the original location of the database folder.</span></span> <span data-ttu-id="63405-122">Alternativ können Sie mit der Schaltfläche zum Durchsuchen (**...**) nach dem Daten Bank Ordner suchen.</span><span class="sxs-lookup"><span data-stu-id="63405-122">Alternatively, you can use the browse button (**...**) to locate the database folder.</span></span>  
  
8.  <span data-ttu-id="63405-123">Wählen Sie den Lese-/Schreibmodus für die Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="63405-123">Select the read/write mode for the database.</span></span>  
  
9. <span data-ttu-id="63405-124">Geben Sie das in Schritt 3 verwendete Kennwort ein, und klicken Sie auf **OK** , um den Befehl Anfügen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="63405-124">Type the password that was used in step 3 and click **OK** to execute the attach command.</span></span>  
  
#### <a name="to-switch-the-readwrite-mode-to-a-database-programmatically-using-amo"></a><span data-ttu-id="63405-125">So schalten Sie den Lese-/Schreibmodus einer Datenbank programmgesteuert mithilfe von AMO um</span><span class="sxs-lookup"><span data-stu-id="63405-125">To switch the read/write mode to a database programmatically using AMO</span></span>  
  
1.  <span data-ttu-id="63405-126">Passen Sie in der C#-Anwendung den folgenden Beispielcode an, und führen Sie die angegebenen Aufgaben aus.</span><span class="sxs-lookup"><span data-stu-id="63405-126">In your C# application, adapt the following sample code and complete the indicated tasks.</span></span>  
  
 `private void SwitchReadWrite(Server server, string dbName,`  
  
 `ReadWriteMode dbReadWriteMode)`  
  
 `{`  
  
 `if (server.Databases.ContainsName(dbName))`  
  
 `{`  
  
 `Database db;`  
  
 `string databaseLocation;`  
  
 `db = server.Databases[dbName];`  
  
 `databaseLocation = db.DbStorageLocation;`  
  
 `if (databaseLocation == null)`  
  
 `{`  
  
 `string dataDir = server.ServerProperties["DataDir"].Value;`  
  
 `String[] possibleFolders = Directory.GetDirectories(dataDir, string.Concat(dbName,"*"), SearchOption.TopDirectoryOnly);`  
  
 `if (possibleFolders.Length > 1)`  
  
 `{`  
  
 `List<String> sortedFolders = new List<string>(possibleFolders.Length);`  
  
 `sortedFolders.AddRange(possibleFolders);`  
  
 `sortedFolders.Sort();`  
  
 `databaseLocation = sortedFolders[sortedFolders.Count - 1];`  
  
 `}`  
  
 `else`  
  
 `{`  
  
 `databaseLocation = possibleFolders[0];`  
  
 `}`  
  
 `}`  
  
 `db.Detach();`  
  
 `server.Attach(databaseLocation, dbReadWriteMode);`  
  
 `}`  
  
 `}`  
  
1.  <span data-ttu-id="63405-127">Rufen Sie in der C#-Anwendung `SwitchReadWrite()` mit den erforderlichen Parametern auf.</span><span class="sxs-lookup"><span data-stu-id="63405-127">In your C# application, invoke `SwitchReadWrite()` with the necessary parameters.</span></span>  
  
2.  <span data-ttu-id="63405-128">Kompilieren Sie den Code, und führen Sie ihn zum Verschieben der Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="63405-128">Compile and execute your code to move the database.</span></span>  
  
#### <a name="to-switch-the-readwrite-mode-to-a-database-by-script-using-xmla"></a><span data-ttu-id="63405-129">So schalten Sie den Lese-/Schreibmodus einer Datenbank mit einem Skript mithilfe von XMLA um</span><span class="sxs-lookup"><span data-stu-id="63405-129">To switch the read/write mode to a database by script using XMLA</span></span>  
  
1.  <span data-ttu-id="63405-130">Suchen Sie im linken oder rechten Bereich von [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] nach der umzuschaltenden Datenbank.</span><span class="sxs-lookup"><span data-stu-id="63405-130">Locate the database to be switched in the left or right pane of [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
2.  <span data-ttu-id="63405-131">Klicken Sie mit der rechten Maustaste auf die Datenbank, und wählen Sie **Eigenschaften**</span><span class="sxs-lookup"><span data-stu-id="63405-131">Right-click the database and select **Properties**.</span></span> <span data-ttu-id="63405-132">Suchen Sie den Datenbankordner, und notieren Sie sich den Speicherort.</span><span class="sxs-lookup"><span data-stu-id="63405-132">Find the database folder and note the location.</span></span> <span data-ttu-id="63405-133">Ein leerer Datenbankspeicherort weist darauf hin, dass sich der Datenbankordner im Datenordner des Servers befindet.</span><span class="sxs-lookup"><span data-stu-id="63405-133">An empty database storage location indicates that the database folder is located in the server data folder.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="63405-134">Sobald die Datenbank getrennt ist, kann [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] Ihnen nicht mehr dabei helfen, den Datenbankspeicherort abzurufen.</span><span class="sxs-lookup"><span data-stu-id="63405-134">As soon as the database is detached, [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] can no longer help you obtain the database location.</span></span>  
  
3.  <span data-ttu-id="63405-135">Öffnen Sie in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]eine neue XMLA-Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="63405-135">Open a new XMLA tab in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
4.  <span data-ttu-id="63405-136">Kopieren Sie die folgende Skriptvorlage für XMLA:</span><span class="sxs-lookup"><span data-stu-id="63405-136">Copy the following script template for XMLA:</span></span>  
  
 `<Detach xmlns="https://schemas.microsoft.com/analysisservices/2003/engine">`  
  
 `<Object>`  
  
 `<DatabaseID>%dbName%</DatabaseID>`  
  
 `<Password>%password%</Password>`  
  
 `</Object>`  
  
 `</Detach>`  
  
1.  <span data-ttu-id="63405-137">Ersetzen Sie `%dbName%` durch den Namen der Datenbank und `%password%` durch das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="63405-137">Replace `%dbName%` with the name of the database and `%password%` with the password.</span></span> <span data-ttu-id="63405-138">Die %-Zeichen sind Teil der Vorlage und müssen entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="63405-138">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="63405-139">Führen Sie den XMLA-Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="63405-139">Execute the XMLA command.</span></span>  
  
3.  <span data-ttu-id="63405-140">Kopieren Sie die folgende Skriptvorlage für XMLA in eine neue XMLA-Registerkarte:</span><span class="sxs-lookup"><span data-stu-id="63405-140">Copy the following script template for XMLA in a new XMLA tab</span></span>  
  
 <span data-ttu-id="63405-141">`<Attach xmlns="https://schemas.microsoft.com/analysisservices/2003` `/engine` `">`</span><span class="sxs-lookup"><span data-stu-id="63405-141">`<Attach xmlns="https://schemas.microsoft.com/analysisservices/2003` `/engine` `">`</span></span>  
  
 `<Folder>%dbFolder%</Folder>`  
  
 `<ReadWriteMode xmlns="https://schemas.microsoft.com/analysisservices/2008/engine/100">%ReadOnlyMode%</ReadWriteMode>`  
  
 `</Attach>`  
  
1.  <span data-ttu-id="63405-142">Ersetzen Sie `%dbFolder%` durch den vollständigen UNC-Pfad des Datenbankordners, `%ReadOnlyMode%` durch den entsprechenden Wert `ReadOnly` oder `ReadWrite` und `%password%` durch das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="63405-142">Replace `%dbFolder%` with the complete UNC path of the database folder, `%ReadOnlyMode%` with the corresponding value `ReadOnly` or `ReadWrite`, and `%password%` with the password.</span></span> <span data-ttu-id="63405-143">Die %-Zeichen sind Teil der Vorlage und müssen entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="63405-143">The % characters are part of the template and must be removed.</span></span>  
  
2.  <span data-ttu-id="63405-144">Führen Sie den XMLA-Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="63405-144">Execute the XMLA command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63405-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="63405-145">See Also</span></span>  
 <xref:Microsoft.AnalysisServices.Server.Attach%2A>   
 <span data-ttu-id="63405-146">[Microsoft. AnalysisServices. Database. Detach \*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span><span class="sxs-lookup"><span data-stu-id="63405-146">[Microsoft.AnalysisServices.Database.Detach\*](/dotnet/api/microsoft.analysisservices.core.database.detach) </span></span>  
 <span data-ttu-id="63405-147">[Anfügen und trennen von Analysis Services Datenbanken](attach-and-detach-analysis-services-databases.md) </span><span class="sxs-lookup"><span data-stu-id="63405-147">[Attach and Detach Analysis Services Databases](attach-and-detach-analysis-services-databases.md) </span></span>  
 <span data-ttu-id="63405-148">[Daten Bank Speicherort](database-storage-location.md) </span><span class="sxs-lookup"><span data-stu-id="63405-148">[Database Storage Location](database-storage-location.md) </span></span>  
 <span data-ttu-id="63405-149">[Datenbanklesemodusmodi](database-readwritemodes.md) </span><span class="sxs-lookup"><span data-stu-id="63405-149">[Database ReadWriteModes](database-readwritemodes.md) </span></span>  
 <span data-ttu-id="63405-150">[Attach-Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span><span class="sxs-lookup"><span data-stu-id="63405-150">[Attach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/attach-element) </span></span>  
 <span data-ttu-id="63405-151">[Detach-Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span><span class="sxs-lookup"><span data-stu-id="63405-151">[Detach Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/detach-element) </span></span>  
 <span data-ttu-id="63405-152">["Read Write-Mode"-Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span><span class="sxs-lookup"><span data-stu-id="63405-152">[ReadWriteMode Element](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/readwritemode-element) </span></span>  
 [<span data-ttu-id="63405-153">DbStorageLocation-Element</span><span class="sxs-lookup"><span data-stu-id="63405-153">DbStorageLocation Element</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/dbstoragelocation-element)  
  
  
