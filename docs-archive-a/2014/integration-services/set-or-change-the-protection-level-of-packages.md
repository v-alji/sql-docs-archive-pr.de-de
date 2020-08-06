---
title: Festlegen oder Ändern der Schutz Ebene von Paketen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- passwords [Integration Services]
- packages [Integration Services],security
- security [Integration Services],protection levels
- protection level for packages [Integration Services]
ms.assetid: 904a5580-82ba-4a26-b0c5-d1c989975f61
author: chugugrace
ms.author: chugu
ms.openlocfilehash: da8e63028498097b4321e4ef1383fbc8aa5845b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724806"
---
# <a name="set-or-change-the-protection-level-of-packages"></a><span data-ttu-id="fc200-102">Festlegen oder Ändern der Schutzebene von Paketen</span><span class="sxs-lookup"><span data-stu-id="fc200-102">Set or Change the Protection Level of Packages</span></span>
  <span data-ttu-id="fc200-103">Wenn der Zugriff auf den Inhalt von Paketen und die darin enthaltenen vertraulichen Werte, z. B. Kennwörter, gesteuert werden soll, legen Sie den Wert der `ProtectionLevel`-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="fc200-103">To control access to the contents of packages and to the sensitive values that they contain, such as passwords, set the value of the `ProtectionLevel` property.</span></span> <span data-ttu-id="fc200-104">Zum Erstellen des Projekts müssen die in einem Projekt enthaltenen Pakete die gleiche Schutzebene wie das Projekt aufweisen.</span><span class="sxs-lookup"><span data-stu-id="fc200-104">The packages contained in a project need to have the same protection level as the project, to build the project.</span></span> <span data-ttu-id="fc200-105">Wenn Sie die `ProtectionLevel`-Eigenschafteneinstellung für das Projekt ändern, müssen Sie die Eigenschafteneinstellung für die Pakete manuell aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="fc200-105">If you change the `ProtectionLevel` property setting on the project, you need to manually update the property setting for the packages.</span></span>  
  
 <span data-ttu-id="fc200-106">Informationen dazu, wie Sie die Einstellungen ermitteln, die `ProtectionLevel` für Ihre Pakete in verschiedenen Phasen des Paket Lebenszyklus geeignet sind, finden Sie unter [Access Control für sensible Daten in Paketen](security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="fc200-106">For information about how to determine the `ProtectionLevel` settings that are appropriate for your packages at different stages in the package life cycle, see [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span></span> <span data-ttu-id="fc200-107">Eine Übersicht über die Sicherheitsfeatures in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] finden Sie unter [Sicherheitsübersicht &#40;Integration Services&#41;](security/security-overview-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="fc200-107">For an overview of security features in [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)], see [Security Overview &#40;Integration Services&#41;](security/security-overview-integration-services.md).</span></span>  
  
 <span data-ttu-id="fc200-108">In den Verfahren in diesem Thema wird die Verwendung des [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]-Befehlszeilen-Hilfsprogramms oder dtutil-Befehlszeilen-Hilfsprogramms zum Ändern der `ProtectionLevel`-Eigenschaft beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fc200-108">The procedures in this topic describe how to use either [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] or the dtutil command prompt utility to change the `ProtectionLevel` property.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fc200-109">Neben dem Verfahren in diesem Thema gibt es normalerweise die Möglichkeit, die `ProtectionLevel`-Eigenschaft eines Pakets festzulegen oder zu ändern, wenn Sie das Paket importieren oder exportieren.</span><span class="sxs-lookup"><span data-stu-id="fc200-109">In addition to the procedures in this topic, you can typically set or change the `ProtectionLevel` property of a package when you import or export the package.</span></span> <span data-ttu-id="fc200-110">Sie können die `ProtectionLevel`-Eigenschaft eines Pakets auch ändern, wenn Sie ein Paket mit dem [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Import/Export-Assistenten speichern.</span><span class="sxs-lookup"><span data-stu-id="fc200-110">You can also change the `ProtectionLevel` property of a package when you use the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard to save a package.</span></span>  
  
### <a name="to-set-or-change-the-protection-level-of-a-package-in-sql-server-data-tools"></a><span data-ttu-id="fc200-111">So legen Sie die Schutzebene eines Pakets in SQL Server-Datentools fest oder ändern sie</span><span class="sxs-lookup"><span data-stu-id="fc200-111">To set or change the protection level of a package in SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="fc200-112">Überprüfen Sie die verfügbaren Werte für die- `ProtectionLevel` Eigenschaft im Thema, legen Sie [die Schutz Ebene von Paketen fest](security/access-control-for-sensitive-data-in-packages.md), und bestimmen Sie den entsprechenden Wert für das Paket.</span><span class="sxs-lookup"><span data-stu-id="fc200-112">Review the available values for the `ProtectionLevel` property in the topic, [Setting the Protection Level of Packages](security/access-control-for-sensitive-data-in-packages.md), and determine the appropriate value for your package.</span></span>  
  
2.  <span data-ttu-id="fc200-113">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt mit dem Paket.</span><span class="sxs-lookup"><span data-stu-id="fc200-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package.</span></span>  
  
3.  <span data-ttu-id="fc200-114">Öffnen Sie das Paket im [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer.</span><span class="sxs-lookup"><span data-stu-id="fc200-114">Open the package in the [!INCLUDE[ssIS](../includes/ssis-md.md)] designer.</span></span>  
  
4.  <span data-ttu-id="fc200-115">Wenn die Eigenschaften des Pakets nicht im Eigenschaftenfenster angezeigt werden, klicken Sie auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="fc200-115">If the Properties window does not show the properties of the package, click the design surface.</span></span>  
  
5.  <span data-ttu-id="fc200-116">Wählen Sie im Eigenschaftenfenster in der Gruppe **Sicherheit** den entsprechenden Wert für die Eigenschaft aus `ProtectionLevel` .</span><span class="sxs-lookup"><span data-stu-id="fc200-116">In the Properties window, in the **Security** group, select the appropriate value for the `ProtectionLevel` property.</span></span>  
  
     <span data-ttu-id="fc200-117">Wenn Sie eine Schutzebene auswählen, für die ein Kennwort erforderlich ist, geben Sie das Kennwort als Wert der **PackagePassword** -Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="fc200-117">If you select a protection level that requires a password, enter the password as the value of the **PackagePassword** property.</span></span>  
  
6.  <span data-ttu-id="fc200-118">Wählen Sie im Menü **Datei** die Option **Ausgewählte Elemente speichern** aus, um das geänderte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="fc200-118">On the **File** menu, select **Save Selected Items** to save the modified package.</span></span>  
  
### <a name="to-set-or-change-the-protection-level-of-packages-at-the-command-prompt"></a><span data-ttu-id="fc200-119">So legen Sie die Schutzebene von Paketen an der Eingabeaufforderung fest oder ändern sie</span><span class="sxs-lookup"><span data-stu-id="fc200-119">To set or change the protection level of packages at the command prompt</span></span>  
  
1.  <span data-ttu-id="fc200-120">Überprüfen Sie die verfügbaren Werte für die- `ProtectionLevel` Eigenschaft im Thema, legen Sie [die Schutz Ebene von Paketen fest](security/access-control-for-sensitive-data-in-packages.md), und bestimmen Sie den entsprechenden Wert für das Paket.</span><span class="sxs-lookup"><span data-stu-id="fc200-120">Review the available values for the `ProtectionLevel` property in the topic, [Setting the Protection Level of Packages](security/access-control-for-sensitive-data-in-packages.md), and determine the appropriate value for your package.</span></span>  
  
2.  <span data-ttu-id="fc200-121">Überprüfen Sie die Zuordnungen für die `Encrypt` Option im Thema [dtutil Utility](dtutil-utility.md), und legen Sie die entsprechende Ganzzahl fest, die als Wert der ausgewählten Eigenschaft verwendet werden soll `ProtectionLevel` .</span><span class="sxs-lookup"><span data-stu-id="fc200-121">Review the mappings for the `Encrypt` option in the topic, [dtutil Utility](dtutil-utility.md), and determine the appropriate integer to use as the value of the selected `ProtectionLevel` property.</span></span>  
  
3.  <span data-ttu-id="fc200-122">Öffnen Sie ein Eingabeaufforderungsfenster.</span><span class="sxs-lookup"><span data-stu-id="fc200-122">Open a Command Prompt window.</span></span>  
  
4.  <span data-ttu-id="fc200-123">Navigieren Sie an der Eingabeaufforderung zu dem Ordner mit den Paketen, für die Sie die `ProtectionLevel`-Eigenschaft festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="fc200-123">At the command prompt, navigate to the folder that contains the package or packages for which you want to set the `ProtectionLevel` property.</span></span>  
  
     <span data-ttu-id="fc200-124">In den Syntaxbeispielen im folgenden Schritt wird davon ausgegangen, dass dieser Ordner der aktuelle Ordner ist.</span><span class="sxs-lookup"><span data-stu-id="fc200-124">The syntax examples shown in the following step assume that this folder is the current folder.</span></span>  
  
5.  <span data-ttu-id="fc200-125">Verwenden Sie zum Festlegen oder Ändern der Schutzebene für die Pakete einen Befehl wie in einem der folgenden Beispiele:</span><span class="sxs-lookup"><span data-stu-id="fc200-125">Set or change the protection level of the package or packages by using a command similar to the one of the following examples:</span></span>  
  
    -   <span data-ttu-id="fc200-126">Mit dem folgenden Befehl wird die `ProtectionLevel`-Eigenschaft eines einzelnen Pakets im Dateisystem auf Ebene 2 ("Sensible Daten mit einem Kennwort verschlüsseln") mit dem Kennwort "strongpassword" festgelegt:</span><span class="sxs-lookup"><span data-stu-id="fc200-126">The following command sets the `ProtectionLevel` property of an individual package in the file system to level 2, "Encrypt sensitive with password", with the password, "strongpassword":</span></span>  
  
         `dtutil.exe /file "C:\Package.dtsx" /encrypt file;"C:\Package.dtsx";2;strongpassword`  
  
    -   <span data-ttu-id="fc200-127">Mit dem folgenden Befehl wird die `ProtectionLevel`-Eigenschaft aller Pakete in einem bestimmten Ordner auf Ebene 2 ("Sensible Daten mit einem Kennwort verschlüsseln") mit dem Kennwort "strongpassword" festgelegt:</span><span class="sxs-lookup"><span data-stu-id="fc200-127">The following command sets the `ProtectionLevel` property of all packages in a particular folder in the file system to level 2, "Encrypt sensitive with password", with the password, "strongpassword":</span></span>  
  
         `for %f in (*.dtsx) do dtutil.exe /file %f /encrypt file;%f;2;strongpassword`  
  
         <span data-ttu-id="fc200-128">Wenn Sie einen ähnlichen Befehl in einer Batchdatei verwenden, geben Sie den Dateiplatzhalter "%f" in der Batchdatei als "%%f" ein.</span><span class="sxs-lookup"><span data-stu-id="fc200-128">If you use a similar command in a batch file, enter the file placeholder, "%f", as "%%f" in the batch file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc200-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc200-129">See Also</span></span>  
 [<span data-ttu-id="fc200-130">dtutil (Hilfsprogramm)</span><span class="sxs-lookup"><span data-stu-id="fc200-130">dtutil Utility</span></span>](dtutil-utility.md)  
  
  
