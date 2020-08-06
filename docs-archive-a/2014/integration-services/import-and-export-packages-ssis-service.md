---
title: Importieren und Exportieren von Paketen (SSIS-Dienst) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- packages [Integration Services], importing
- packages [Integration Services], exporting
- importing packages
- exporting packages
ms.assetid: ef18ec11-b536-47d9-abd1-794099f43486
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b69f9d23431ed86f6b84be6857b7104cd8ba3dcc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619953"
---
# <a name="import-and-export-packages-ssis-service"></a><span data-ttu-id="77959-102">Import und Export von Paketen (SSIS-Dienst)</span><span class="sxs-lookup"><span data-stu-id="77959-102">Import and Export Packages (SSIS Service)</span></span>
    
> [!IMPORTANT]  
>  <span data-ttu-id="77959-103">In diesem Thema wird der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst beschrieben, ein Windows-Dienst zur Verwaltung von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paketen.</span><span class="sxs-lookup"><span data-stu-id="77959-103">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service, a Windows service for managing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="77959-104">unterstützt den Dienst für die Abwärtskompatibilität mit früheren Versionen von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77959-104">supports the service for backward compatibility with earlier releases of [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="77959-105">Ab [!INCLUDE[ssSQL11](../includes/sssql11-md.md)]können Sie Objekte, z. B. Pakete, auf dem Integration Services-Server verwalten.</span><span class="sxs-lookup"><span data-stu-id="77959-105">Starting in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], you can manage objects such as packages on the Integration Services server.</span></span>  
  
 <span data-ttu-id="77959-106">Pakete können in der sysssispackages-Tabelle in der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -msdb-Datenbank oder im Dateisystem gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="77959-106">Packages can be saved either in the sysssispackages table in the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database or in the file system.</span></span>  
  
 <span data-ttu-id="77959-107">Der Paketspeicher, bei dem es sich um den logischen Speicherort handelt, der vom [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst überwacht und verwaltet wird, kann sowohl die msdb-Datenbank als auch die in der Konfigurationsdatei für den [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst angegebenen Dateisystemordner einschließen.</span><span class="sxs-lookup"><span data-stu-id="77959-107">The package store, which is the logical storage that [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service monitors and manages, can include both the msdb database and the file system folders specified in the configuration file for the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service.</span></span>  
  
 <span data-ttu-id="77959-108">Sie können Pakete zwischen den folgenden Speichertypen importieren und exportieren:</span><span class="sxs-lookup"><span data-stu-id="77959-108">You can import and export packages between the following storage types:</span></span>  
  
-   <span data-ttu-id="77959-109">Dateisystemordner überall im Dateisystem.</span><span class="sxs-lookup"><span data-stu-id="77959-109">File system folders anywhere in the file system.</span></span>  
  
-   <span data-ttu-id="77959-110">Ordner im SSIS-Paketspeicher.</span><span class="sxs-lookup"><span data-stu-id="77959-110">Folders in the SSIS Package Store.</span></span> <span data-ttu-id="77959-111">Die beiden Standardordner heißen File System und MSDM.</span><span class="sxs-lookup"><span data-stu-id="77959-111">The two default folders are named File System and MSDB.</span></span>  
  
-   <span data-ttu-id="77959-112">Die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -msdb-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="77959-112">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] msdb database.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="77959-113">ermöglicht Ihnen das Importieren und Exportieren von Paketen. Damit können Sie das Speicherformat und den Speicherort der Pakete ändern.</span><span class="sxs-lookup"><span data-stu-id="77959-113">gives you the ability to import and export packages, and by doing this change the storage format and location of packages.</span></span> <span data-ttu-id="77959-114">Mit den Import- und Export-Features können Sie Pakete zum Dateisystem, zum Paketspeicher oder zur msdb-Datenbank hinzufügen und Pakete aus einem Speicherformat in ein anderes Format kopieren.</span><span class="sxs-lookup"><span data-stu-id="77959-114">Using the import and export features, you can add packages to the file system, package store, or msdb database, and copy packages from one storage format to another.</span></span> <span data-ttu-id="77959-115">So können z.B. in msdb gespeicherte Pakete in das Dateisystem kopiert werden und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="77959-115">For example, packages saved in msdb can be copied to the file system and vice versa.</span></span>  
  
 <span data-ttu-id="77959-116">Zum Kopieren eines Pakets in ein anderes Format können Sie auch das Eingabeaufforderungs-Hilfsprogramm **dtutil** („dtutil.exe“) verwenden.</span><span class="sxs-lookup"><span data-stu-id="77959-116">You can also copy a package to a different format using the **dtutil** command prompt utility (dtutil.exe).</span></span> <span data-ttu-id="77959-117">Weitere Informationen finden Sie unter [dtutil Utility](dtutil-utility.md).</span><span class="sxs-lookup"><span data-stu-id="77959-117">For more information, see [dtutil Utility](dtutil-utility.md).</span></span>  
  
## <a name="to-import-or-export-a-package"></a><span data-ttu-id="77959-118">So importieren oder exportieren Sie ein Paket</span><span class="sxs-lookup"><span data-stu-id="77959-118">To import or export a package</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="77959-119">In diesem Thema wird der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst erläutert, der Teil von [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)]ist.</span><span class="sxs-lookup"><span data-stu-id="77959-119">This topic discusses the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service that is part of [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span> [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] <span data-ttu-id="77959-120">unterstützt den [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Dienst aus Gründen der Abwärtskompatibilität mit [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77959-120">supports the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] service for backward compatibility with [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span> <span data-ttu-id="77959-121">Informationen zum Verwalten von Paketen in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)] finden Sie unter [Integration Services-Server &#40;SSIS&#41;](catalog/integration-services-ssis-server-and-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="77959-121">For information about managing packages in [!INCLUDE[ssSQL11](../includes/sssql11-md.md)], see [Integration Services &#40;SSIS&#41; Server](catalog/integration-services-ssis-server-and-catalog.md).</span></span>  
  
 <span data-ttu-id="77959-122">Sie können ein [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket aus folgenden Speicherorten importieren bzw. in folgende Speicherorte exportieren:</span><span class="sxs-lookup"><span data-stu-id="77959-122">You can import or export an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package from or to the following locations:</span></span>  
  
-   <span data-ttu-id="77959-123">Sie können ein Paket importieren, das in einer [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Instanz, im Dateisystem oder im [!INCLUDE[ssIS](../includes/ssis-md.md)]-Paketspeicher gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="77959-123">You can import a package that is stored in an instance of [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], in the file system, or in the [!INCLUDE[ssIS](../includes/ssis-md.md)] package store.</span></span> <span data-ttu-id="77959-124">Das importierte Pakete wird in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] oder in einem Ordner im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Paketspeicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="77959-124">The imported package is saved to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or to a folder in the [!INCLUDE[ssIS](../includes/ssis-md.md)] package store.</span></span>  
  
-   <span data-ttu-id="77959-125">Sie können ein Paket exportieren, das in einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], im Dateisystem oder im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Paketspeicher in einem anderen Speicherformat und an einem anderen Speicherort gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="77959-125">You can export a package that is stored in an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], the file system, or the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store to a different storage format and location.</span></span>  
  
 <span data-ttu-id="77959-126">Es gibt jedoch einige Einschränkungen im Hinblick auf das Importieren und Exportieren eines Pakets zwischen verschiedenen Versionen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="77959-126">However, there are some restrictions on importing and exporting a package between different versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]:</span></span>  
  
-   <span data-ttu-id="77959-127">In einer Instanz von [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)]können Sie Pakete von einer [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]-Instanz importieren, Sie können jedoch keine Pakete in eine [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]-Instanz exportieren.</span><span class="sxs-lookup"><span data-stu-id="77959-127">On an instance of [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)], you can import packages from an instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], but you cannot export packages to an instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)].</span></span>  
  
-   <span data-ttu-id="77959-128">In einer Instanz von [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)]können Sie keine Pakete von einer [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)]-Instanz importieren bzw. dorthin exportieren.</span><span class="sxs-lookup"><span data-stu-id="77959-128">On an instance of [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], you cannot import packages from, or export packages to, an instance of [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="77959-129">Die folgenden Schritte beschreiben, wie [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] verwendet wird, um ein Paket zu importieren oder zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="77959-129">The following procedures describe how to use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to import or export a package.</span></span>  
  
#### <a name="to-import-a-package-by-using-sql-server-management-studio"></a><span data-ttu-id="77959-130">So importieren Sie ein Paket mit SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="77959-130">To import a package by Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="77959-131">Klicken Sie auf **Start**, zeigen Sie auf **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], und klicken Sie dann auf **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="77959-131">Click **Start**, point to **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="77959-132">Legen Sie im Dialogfeld **Verbindung mit Server herstellen** die folgenden Optionen fest:</span><span class="sxs-lookup"><span data-stu-id="77959-132">In the **Connect to Server** dialog box set the following options:</span></span>  
  
    -   <span data-ttu-id="77959-133">Wählen Sie im Feld **Servertyp** die Option **Integration Services**aus.</span><span class="sxs-lookup"><span data-stu-id="77959-133">In the **Server type** box, select **Integration Services**.</span></span>  
  
    -   <span data-ttu-id="77959-134">Geben Sie im Feld **Servername** einen Servernamen an, oder klicken Sie auf **\<Browse for more...>** , um nach dem zu verwendenden Server zu suchen.</span><span class="sxs-lookup"><span data-stu-id="77959-134">In the **Server name** box, provide a server name or click **\<Browse for more...>** and locate the server to use.</span></span>  
  
3.  <span data-ttu-id="77959-135">Wenn der Objekt-Explorer nicht geöffnet ist, klicken Sie im Menü **Ansicht** auf **Objekt-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="77959-135">If Object Explorer is not open, on the **View** menu, click **Object Explorer**.</span></span>  
  
4.  <span data-ttu-id="77959-136">Erweitern Sie im Objekt-Explorer den Ordner **Gespeicherte Pakete** .</span><span class="sxs-lookup"><span data-stu-id="77959-136">In Object Explorer, expand the **Stored Packages** folder.</span></span>  
  
5.  <span data-ttu-id="77959-137">Erweitern Sie die Unterordner, um den Ordner zu suchen, in den Sie ein Paket importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="77959-137">Expand the subfolders to locate the folder into which you want to import a package.</span></span>  
  
6.  <span data-ttu-id="77959-138">Klicken Sie mit der rechten Maustaste auf den Ordner, und wählen Sie **Paket importieren**aus.</span><span class="sxs-lookup"><span data-stu-id="77959-138">Right-click the folder, click **Import Package**.</span></span> <span data-ttu-id="77959-139">Führen Sie dann eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="77959-139">and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="77959-140">Zum Importieren aus einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]wählen Sie die Option **SQL Server** aus, geben Sie den Server an, und wählen Sie den Authentifizierungsmodus aus.</span><span class="sxs-lookup"><span data-stu-id="77959-140">To import from an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], select the **SQL Server** option, and then specify the server and select the authentication mode.</span></span> <span data-ttu-id="77959-141">Wenn Sie die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung auswählen, geben Sie einen Benutzernamen und ein Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="77959-141">If you select [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name and a password.</span></span>  
  
         <span data-ttu-id="77959-142">Klicken Sie auf die Schaltfläche mit den drei Punkten **(…)** , wählen Sie das zu importierende Paket aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="77959-142">Click the browse button **(...)**, select the package to import, and then click **OK.**</span></span>  
  
    -   <span data-ttu-id="77959-143">Zum Importieren aus dem Dateisystem wählen Sie die Option **Dateisystem** aus.</span><span class="sxs-lookup"><span data-stu-id="77959-143">To import from the file system, select the **File system** option.</span></span>  
  
         <span data-ttu-id="77959-144">Klicken Sie auf die Schaltfläche mit den drei Punkten **(…)** , wählen Sie das zu importierende Paket aus, und klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="77959-144">Click the browse button **(...)**, select the package to import, and then click **Open.**</span></span>  
  
    -   <span data-ttu-id="77959-145">Zum Importieren aus dem [!INCLUDE[ssIS](../includes/ssis-md.md)] -Paketspeicher wählen Sie die Option **SSIS-Paketspeicher** aus, und geben Sie den Server an.</span><span class="sxs-lookup"><span data-stu-id="77959-145">To import from the [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Store, select the **SSIS Package Store** option and specify the server.</span></span>  
  
         <span data-ttu-id="77959-146">Klicken Sie auf die Schaltfläche mit den drei Punkten **(…)** , wählen Sie das zu importierende Paket aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="77959-146">Click the browse button **(...)**, select the package to import, and then click **OK.**</span></span>  
  
7.  <span data-ttu-id="77959-147">Aktualisieren Sie optional den Paketnamen.</span><span class="sxs-lookup"><span data-stu-id="77959-147">Optionally, update the package name.</span></span>  
  
8.  <span data-ttu-id="77959-148">Zum Aktualisieren der Schutzebene des Pakets klicken Sie auf die Schaltfläche mit den drei Punkten **(…)** , und wählen Sie im Dialogfeld **Paketschutzebene** eine andere Schutzebene aus.</span><span class="sxs-lookup"><span data-stu-id="77959-148">To update the protection level of the package, click the browse button **(...)** and choose a different protection level by using the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="77959-149">Falls die Option **Sensible Daten mit einem Kennwort verschlüsseln** oder **Alle Daten mit einem Kennwort verschlüsseln** ausgewählt ist, geben Sie ein Kennwort ein, und bestätigen Sie es.</span><span class="sxs-lookup"><span data-stu-id="77959-149">If the **Encrypt sensitive data with password** or the **Encrypt all data with password** option is selected, type and confirm a password.</span></span>  
  
9. <span data-ttu-id="77959-150">Klicken Sie auf **OK** , um den Import abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="77959-150">Click **OK** to complete the import.</span></span>  
  
#### <a name="to-export-a-package-by-using-sql-server-management-studio"></a><span data-ttu-id="77959-151">So exportieren Sie ein Paket mit SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="77959-151">To export a package by Using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="77959-152">Klicken Sie auf **Start**, zeigen Sie auf **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], und klicken Sie dann auf **SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="77959-152">Click **Start**, point to **Microsoft** [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="77959-153">Legen Sie im Dialogfeld **Verbindung mit Server herstellen** die folgenden Optionen fest:</span><span class="sxs-lookup"><span data-stu-id="77959-153">In the **Connect to Server** dialog box, set the following options:</span></span>  
  
    -   <span data-ttu-id="77959-154">Wählen Sie im Feld **Servertyp** die Option **Integration Services**aus.</span><span class="sxs-lookup"><span data-stu-id="77959-154">In the **Server type** box, select **Integration Services**.</span></span>  
  
    -   <span data-ttu-id="77959-155">Geben Sie im Feld **Servername** einen Servernamen an, oder klicken Sie auf **\<Browse for more...>** , um nach dem zu verwendenden Server zu suchen.</span><span class="sxs-lookup"><span data-stu-id="77959-155">In the **Server name** box, provide a server name or click **\<Browse for more...>** and locate the server to use.</span></span>  
  
3.  <span data-ttu-id="77959-156">Wenn der Objekt-Explorer nicht geöffnet ist, klicken Sie im Menü **Ansicht** auf **Objekt-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="77959-156">If Object Explorer is not open, on the **View** menu, click **Object Explorer**.</span></span>  
  
4.  <span data-ttu-id="77959-157">Erweitern Sie im Objekt-Explorer den Ordner **Gespeicherte Pakete** .</span><span class="sxs-lookup"><span data-stu-id="77959-157">In Object Explorer, expand the **Stored Packages** folder.</span></span>  
  
5.  <span data-ttu-id="77959-158">Erweitern Sie die Unterordner, um das Paket zu suchen, das Sie exportieren möchten.</span><span class="sxs-lookup"><span data-stu-id="77959-158">Expand the subfolders to locate the package you want to export.</span></span>  
  
6.  <span data-ttu-id="77959-159">Klicken Sie mit der rechten Maustaste auf das Paket, klicken Sie auf **Exportieren**, und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="77959-159">Right-click the package, click **Export**, and then do one of the following:</span></span>  
  
    -   <span data-ttu-id="77959-160">Zum Exportieren einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]wählen Sie die Option **SQL Server** aus, geben Sie den Server an, und wählen Sie den Authentifizierungsmodus aus.</span><span class="sxs-lookup"><span data-stu-id="77959-160">To export to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], select the **SQL Server** option, and then specify the server and select the authentication mode.</span></span> <span data-ttu-id="77959-161">Wenn Sie die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung auswählen, geben Sie einen Benutzernamen und ein Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="77959-161">If you select [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name and a password.</span></span>  
  
         <span data-ttu-id="77959-162">Klicken Sie auf die Schaltfläche mit den drei Punkten **(…)** , und erweitern Sie den Ordner **SSIS-Pakete**, um den Ordner zu suchen, in dem Sie das Paket speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="77959-162">Click the browse button **(...)**, and expand the **SSIS Packages** folder to locate the folder to which you want to save the package.</span></span> <span data-ttu-id="77959-163">Aktualisieren Sie optional den Standardnamen des Pakets, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="77959-163">Optionally, update the default name of the package, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="77959-164">Zum Exportieren in das Dateisystem wählen Sie die Option **Dateisystem** aus.</span><span class="sxs-lookup"><span data-stu-id="77959-164">To export to the file system, select the **File System** option.</span></span>  
  
         <span data-ttu-id="77959-165">Klicken Sie auf die Schaltfläche mit den drei Punkten **(…)** , um den Ordner zu suchen, in den Sie das Paket exportieren möchten, geben Sie den Namen der Paketdatei ein, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="77959-165">Click the browse button **(...)** to locate the folder to which you want to export the package, type the name of the package file, and then click **Save.**</span></span>  
  
    -   <span data-ttu-id="77959-166">Zum Exportieren in den [!INCLUDE[ssIS](../includes/ssis-md.md)] -Paketspeicher wählen Sie die Option **SSIS-Paketspeicher** aus, und geben Sie den Server an.</span><span class="sxs-lookup"><span data-stu-id="77959-166">To export to the [!INCLUDE[ssIS](../includes/ssis-md.md)] package store, select the **SSIS Package Store** option, and specify the server.</span></span>  
  
         <span data-ttu-id="77959-167">Klicken Sie auf die Schaltfläche mit den drei Punkten **(…)** , erweitern Sie den Ordner **SSIS-Pakete**, und wählen Sie den Ordner aus, in dem Sie das Paket speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="77959-167">Click the browse button **(...)**, expand the **SSIS Packages** folder, and select the folder to which you want to save the package.</span></span> <span data-ttu-id="77959-168">Geben Sie optional in das Textfeld **Paketname** einen neuen Namen für das Paket ein.</span><span class="sxs-lookup"><span data-stu-id="77959-168">Optionally, enter a new name for the package in the **Package Name** text box.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="77959-169">Zum Aktualisieren der Schutzebene des Pakets klicken Sie auf die Schaltfläche mit den drei Punkten **(…)** , und wählen Sie im Dialogfeld **Paketschutzebene** eine andere Schutzebene aus.</span><span class="sxs-lookup"><span data-stu-id="77959-169">To update the protection level of the package, click the browse button **(...)** and choose a different protection level by using the **Package Protection Level** dialog box.</span></span> <span data-ttu-id="77959-170">Falls die Option **Sensible Daten mit einem Kennwort verschlüsseln** oder **Alle Daten mit einem Kennwort verschlüsseln** ausgewählt ist, geben Sie ein Kennwort ein, und bestätigen Sie es.</span><span class="sxs-lookup"><span data-stu-id="77959-170">If the **Encrypt sensitive data with password** or the **Encrypt all data with password** option is selected, type and confirm a password.</span></span>  
  
8.  <span data-ttu-id="77959-171">Klicken Sie auf **OK** , um den Export abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="77959-171">Click **OK** to complete the export.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77959-172">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="77959-172">See Also</span></span>  
 [<span data-ttu-id="77959-173">Paketverwaltung &#40;SSIS-Dienst&#41;</span><span class="sxs-lookup"><span data-stu-id="77959-173">Package Management &#40;SSIS Service&#41;</span></span>](service/package-management-ssis-service.md)  
  
  
