---
title: Speichern einer Kopie eines Pakets | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- Integration Services packages, saving
- packages [Integration Services], saving
- saving packages
- SSIS packages, saving
- SQL Server Integration Services packages, saving
ms.assetid: 21482a20-e420-4452-b7eb-8f9fa1929f31
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 02ee2374fddb7dbb6b17adc2a4a10707179c882d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698438"
---
# <a name="save-a-copy-of-a-package"></a><span data-ttu-id="d6f44-102">Speichern einer Kopie eines Pakets</span><span class="sxs-lookup"><span data-stu-id="d6f44-102">Save a Copy of a Package</span></span>
  <span data-ttu-id="d6f44-103">In diesem Verfahren wird beschrieben, wie Sie eine Kopie eines Pakets im Dateisystem, im Paketspeicher oder in der **msdb** -Datenbank in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]speichern.</span><span class="sxs-lookup"><span data-stu-id="d6f44-103">This procedure describes how to save a copy of a package to the file system, to the package store, or to the **msdb** database in [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d6f44-104">Wenn Sie einen Speicherort zum Speichern der Paketkopie angeben, können Sie auch den Namen des Pakets aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="d6f44-104">When you specify a location to save the package copy, you can also update the name of the package.</span></span>  
  
 <span data-ttu-id="d6f44-105">Der Paketspeicher kann sowohl die **msdb** -Datenbank als auch die Ordner im Dateisystem, nur **msdb**oder nur Ordner im Dateisystem einschließen.</span><span class="sxs-lookup"><span data-stu-id="d6f44-105">The package store can include both the **msdb** database and the folders in the file system, only **msdb**, or only folders in the file system.</span></span> <span data-ttu-id="d6f44-106">In **msdb**werden Pakete in der **sysssispackages** -Tabelle gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d6f44-106">In **msdb**, packages are saved to the **sysssispackages** table.</span></span> <span data-ttu-id="d6f44-107">Diese Tabelle schließt eine **folderid** -Spalte ein, die den logischen Ordner identifiziert, zu dem das Paket gehört.</span><span class="sxs-lookup"><span data-stu-id="d6f44-107">This table includes a **folderid** column that identifies the logical folder to which the package belongs.</span></span> <span data-ttu-id="d6f44-108">Logische Ordner bieten eine gute Möglichkeit, gespeicherter Pakete in **msdb** auf die gleiche Weise zu gruppieren, in der Ordner im Dateisystem das Gruppieren von im Dateisystem gespeicherten Paketen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d6f44-108">The logical folders provide a useful way to group packages saved to **msdb** in the same way that folders in the file system provide a way to group packages saved to the file system.</span></span> <span data-ttu-id="d6f44-109">Zeilen in der **sysssispackagefolders** -Tabelle in **msdb** definieren die Ordner.</span><span class="sxs-lookup"><span data-stu-id="d6f44-109">Rows in the **sysssispackagefolders** table in **msdb** define the folders.</span></span>  
  
 <span data-ttu-id="d6f44-110">Wenn **msdb** nicht als Teil des Paketspeichers definiert ist, können Sie Pakete weiterhin vorhandenen logischen Ordnern zuordnen, wenn Sie SQL Server in der Option **Paketpfad** auswählen.</span><span class="sxs-lookup"><span data-stu-id="d6f44-110">If **msdb** is not defined as part of the package store, you can continue to associate packages with existing logical folders when you select SQL Server in the **Package Path** option.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d6f44-111">Das Paket muss im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer geöffnet sein, damit Sie eine Kopie des Pakets speichern können.</span><span class="sxs-lookup"><span data-stu-id="d6f44-111">The package must be opened in [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer before you can save a copy of the package.</span></span>  
  
### <a name="to-save-a-copy-of-a-package"></a><span data-ttu-id="d6f44-112">So speichern Sie eine Kopie eines Pakets</span><span class="sxs-lookup"><span data-stu-id="d6f44-112">To save a copy of a package</span></span>  
  
1.  <span data-ttu-id="d6f44-113">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, von dem Sie eine Kopie speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="d6f44-113">In Solution Explorer, double-click the package of which you want to save a copy.</span></span>  
  
2.  <span data-ttu-id="d6f44-114">Klicken Sie im Menü **Datei** auf **Kopie von „\<package file>“ speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="d6f44-114">On the **File** menu, click **Save Copy of \<package file> As**.</span></span>  
  
3.  <span data-ttu-id="d6f44-115">Wählen Sie im Dialogfeld **Kopie des Pakets speichern** in der Liste **Paketspeicherort** einen Paketspeicherort aus.</span><span class="sxs-lookup"><span data-stu-id="d6f44-115">In the **Save Copy of Package** dialog box, select a package location in the **Package location** list.</span></span>  
  
4.  <span data-ttu-id="d6f44-116">Falls der Speicherort **SQL Server** oder **SSIS-Paketspeicher**ist, stellen Sie einen Servernamen bereit.</span><span class="sxs-lookup"><span data-stu-id="d6f44-116">If the location is **SQL Server** or **SSIS Package Store**, provide a server name.</span></span>  
  
5.  <span data-ttu-id="d6f44-117">Wenn Sie in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]speichern, geben Sie den Authentifizierungstyp an und, falls Sie die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Authentifizierung verwenden, einen Benutzernamen und ein Kennwort.</span><span class="sxs-lookup"><span data-stu-id="d6f44-117">If saving to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], specify the authentication type and, if using [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, provide a user name and password.</span></span>  
  
6.  <span data-ttu-id="d6f44-118">Geben Sie zum Angeben des Paketpfads entweder den Pfad ein, oder klicken Sie auf die Schaltfläche zum Durchsuchen **(...)** , um den Speicherort des Pakets anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d6f44-118">To specify the package path, either type the path or click the browse button **(...)** to specify the location of the package.</span></span> <span data-ttu-id="d6f44-119">Der Standardname des Pakets lautet Paket.</span><span class="sxs-lookup"><span data-stu-id="d6f44-119">The default name of the package is Package.</span></span> <span data-ttu-id="d6f44-120">Optional können Sie den Paktnamen aktualisieren, sodass er Ihren Bedürfnissen entspricht.</span><span class="sxs-lookup"><span data-stu-id="d6f44-120">Optionally, update the package name to one that suits your needs.</span></span>  
  
     <span data-ttu-id="d6f44-121">Wenn Sie **SQL Server** in der Option **Paketpfad** auswählen, besteht der Paketpfad aus logischen Ordnern in **msdb** und dem Paketnamen.</span><span class="sxs-lookup"><span data-stu-id="d6f44-121">If you select **SQL Server** as the **Package Path** option, the package path consists of logical folders in **msdb** and the package name.</span></span> <span data-ttu-id="d6f44-122">Ist z.B. das Paket DownloadMonthlyData dem Ordner Finance im Ordner MSDB (der Standardname des logischen Stammordners in **msdb**) zugeordnet, lautet der Paketpfad MSDB/Finance/DownloadMonthlyData für das Paket DownloadMonthlyData.</span><span class="sxs-lookup"><span data-stu-id="d6f44-122">For example, if the package DownloadMonthlyData is associated with the Finance folder within the MSDB folder (the default name of the root logical folder in **msdb**), the package path for the package named DownloadMonthlyData is MSDB/Finance/DownloadMonthlyData</span></span>  
  
     <span data-ttu-id="d6f44-123">Wenn Sie **SSIS-Paketspeicher** in der Option **Paketpfad** auswählen, besteht der Paketpfad aus dem Ordner, der vom Integration Services-Dienst verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="d6f44-123">If you select **SSIS Package Store** as the **Package Path** option, the package path consists of the folder that the Integration Services service manages.</span></span> <span data-ttu-id="d6f44-124">Befindet sich z. B. das Paket UpdateDeductions im Ordner HumanResources im Dateisystemordner, der von dem Dienst verwaltet wird, lautet der Paketpfad /File System/HumanResources/UpdateDeductions. Ist das Paket PostResumes dem Ordner HumanResources im Ordner MSDB zugeordnet, lautet der Paketpfad MSDB/HumanResources/PostResumes.</span><span class="sxs-lookup"><span data-stu-id="d6f44-124">For example, if the package UpdateDeductions is located in the HumanResources folder within the file system folder that the service manages, the package path is /File System/HumanResources/UpdateDeductions; likewise, if the package PostResumes is associated with the HumanResources folder within the MSDB folder, the package path is MSDB/HumanResources/PostResumes.</span></span>  
  
     <span data-ttu-id="d6f44-125">Wenn Sie **Dateisystem** in der Option **Paketpfad** auswählen, setzt sich der Paketpfad aus dem Speicherort im Dateisystem und dem Dateinamen zusammen.</span><span class="sxs-lookup"><span data-stu-id="d6f44-125">If you select **File System** as the **Package Path** option, the package path is the location in the file system and the file name.</span></span> <span data-ttu-id="d6f44-126">Ist z. B. der Paketname UpdateDemographics, lautet der Paketpfad C:\HumanResources\Quarterly\UpdateDemographics.dtsx.</span><span class="sxs-lookup"><span data-stu-id="d6f44-126">For example, if the package name is UpdateDemographics the package path is C:\HumanResources\Quarterly\UpdateDemographics.dtsx.</span></span>  
  
7.  <span data-ttu-id="d6f44-127">Überprüfen Sie die Paketschutzebene.</span><span class="sxs-lookup"><span data-stu-id="d6f44-127">Review the package protection level.</span></span>  
  
8.  <span data-ttu-id="d6f44-128">Klicken Sie optional auf die Auslassungspunkte **(…)** neben dem Feld **Schutzebene**, um die Schutzebene zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d6f44-128">Optionally, click the browse button **(...)** by the **Protection level** box to change the protection level.</span></span>  
  
    -   <span data-ttu-id="d6f44-129">Wählen Sie im Dialogfeld **Paketschutzebene** eine andere Schutzebene aus.</span><span class="sxs-lookup"><span data-stu-id="d6f44-129">In the **Package Protection Level** dialog box, select a different protection level.</span></span>  
  
    -   <span data-ttu-id="d6f44-130">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d6f44-130">Click **OK**.</span></span>  
  
9. <span data-ttu-id="d6f44-131">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d6f44-131">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6f44-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6f44-132">See Also</span></span>  
 <span data-ttu-id="d6f44-133">[Integration Services &#40;SSIS-&#41; Paketen](../../2014/integration-services/integration-services-ssis-packages.md) </span><span class="sxs-lookup"><span data-stu-id="d6f44-133">[Integration Services &#40;SSIS&#41; Packages](../../2014/integration-services/integration-services-ssis-packages.md) </span></span>  
 [<span data-ttu-id="d6f44-134">Konfigurieren des Integration Services-Diensts &#40;SSIS-Dienst&#41;</span><span class="sxs-lookup"><span data-stu-id="d6f44-134">Configuring the Integration Services Service &#40;SSIS Service&#41;</span></span>](service/integration-services-service-ssis-service.md)  
  
  
