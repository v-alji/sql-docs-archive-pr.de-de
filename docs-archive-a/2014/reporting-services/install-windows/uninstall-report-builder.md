---
title: Deinstallieren Sie die eigenständige Version von Berichts-Generator (Berichts-Generator) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 009538c6-4941-4393-b14b-9144cffdbdaf
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cda13248d1aa14ee3d57a951872d3ad8ded17da9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620742"
---
# <a name="uninstall-the-stand-alone-version-of-report-builder-report-builder"></a><span data-ttu-id="42d7d-102">Deinstallieren der eigenständigen Version des Berichts-Generators (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="42d7d-102">Uninstall the Stand-Alone Version of Report Builder (Report Builder)</span></span>
  <span data-ttu-id="42d7d-103">Sie können die eigenständige Version des Berichts-Generators über die Systemsteuerung oder die Befehlszeile deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="42d7d-103">You can uninstall the stand-alone version of Report Builder from the control panel or the command line.</span></span> <span data-ttu-id="42d7d-104">Für die Deinstallation der [!INCLUDE[ndptecclick](../../includes/ndptecclick-md.md)]-Version des Berichts-Generators muss auch [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)] deinstalliert werden.</span><span class="sxs-lookup"><span data-stu-id="42d7d-104">You cannot uninstall the [!INCLUDE[ndptecclick](../../includes/ndptecclick-md.md)] version of Report Builder without uninstalling [!INCLUDE[ssRSCurrent](../../includes/ssrscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="42d7d-105">Zum Deinstallieren des Berichts-Generators über die Befehlszeile wird die gleiche Syntax verwendet wie zum Installieren des Berichts-Generators. Sie geben lediglich die /x-Option anstelle der /i-Option an.</span><span class="sxs-lookup"><span data-stu-id="42d7d-105">Uninstalling Report Builder from the command line uses syntax that is identical to the syntax you use to install Report Builder, except you use the /x option instead of the /i option.</span></span> <span data-ttu-id="42d7d-106">In den Befehlszeilen zur Deinstallation können auch die /quiet-Option und andere Standardoptionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="42d7d-106">Command lines for uninstalling can also include the /quiet option and other standard options.</span></span> <span data-ttu-id="42d7d-107">Wenn das Windows Installer Package für den Berichts-Generator (ReportBuilder3_x86.msi) entfernt wurde, ist das Entfernen des Berichts-Generators über die Befehlszeile nicht ohne Weiteres möglich.</span><span class="sxs-lookup"><span data-stu-id="42d7d-107">If the Report Builder Windows Installer Package (ReportBuilder3_x86.msi) has been removed, you cannot use the command line easily to uninstall Report Builder.</span></span> <span data-ttu-id="42d7d-108">In der Dokumentation für das msiexec-Programm in der MSDN Library wird beschrieben, wie Sie den Berichts-Generator möglicherweise dennoch mit der GUID entfernen können.</span><span class="sxs-lookup"><span data-stu-id="42d7d-108">To learn more about how you might be able to remove Report Builder by using its GUID, see the documentation for the msiexec program in the msdn library.</span></span>  
  
 <span data-ttu-id="42d7d-109">Enthalten vom Berichts-Generator verwendete Ordner benutzerdefinierte Dateien, werden die Ordner und Dateien beim Entfernen des Berichts-Generators beibehalten.</span><span class="sxs-lookup"><span data-stu-id="42d7d-109">If folders used by Report Builder include custom files, the folders and the files are preserved when Report Builder is removed.</span></span> <span data-ttu-id="42d7d-110">Nur die Berichts-Generator-Dateien werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="42d7d-110">Only the Report Builder files are removed.</span></span>  
  
### <a name="to-uninstall-report-builder-from-the-control-panel"></a><span data-ttu-id="42d7d-111">So deinstallieren Sie den Berichts-Generator über die Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="42d7d-111">To uninstall Report Builder from the control panel</span></span>  
  
1.  <span data-ttu-id="42d7d-112">Klicken Sie im Menü **Start** auf **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="42d7d-112">On the **Start** menu, click **Control Panel**.</span></span>  
  
2.  <span data-ttu-id="42d7d-113">Klicken Sie in der Systemsteuerung auf **Programme und Funktionen**.</span><span class="sxs-lookup"><span data-stu-id="42d7d-113">In the Control Panel, click **Programs and Features**.</span></span>  
  
3.  <span data-ttu-id="42d7d-114">Suchen Sie [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] -Berichts-Generator in der Liste **Name** , und klicken Sie darauf.</span><span class="sxs-lookup"><span data-stu-id="42d7d-114">Locate [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] Report Builder in the **Name** list and click it.</span></span>  
  
4.  <span data-ttu-id="42d7d-115">Klicken Sie auf **Deinstallieren**.</span><span class="sxs-lookup"><span data-stu-id="42d7d-115">Click **Uninstall**.</span></span>  
  
5.  <span data-ttu-id="42d7d-116">Klicken Sie auf **Ja**, wenn Sie aufgefordert werden, das Deinstallieren des Berichts-Generators zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="42d7d-116">If prompted to confirm the uninstall of Report Builder, click **Yes**.</span></span>  
  
### <a name="to-uninstall-report-builder-from-the-command-line"></a><span data-ttu-id="42d7d-117">So deinstallieren Sie den Berichts-Generator über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="42d7d-117">To uninstall Report Builder from the command line</span></span>  
  
1.  <span data-ttu-id="42d7d-118">Klicken Sie im Menü **Start** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="42d7d-118">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="42d7d-119">Geben Sie im Textfeld **Öffnen** den Text`cmd.`</span><span class="sxs-lookup"><span data-stu-id="42d7d-119">In the **Open** text box, type `cmd.`</span></span>  
  
3.  <span data-ttu-id="42d7d-120">Navigieren Sie im Eingabeaufforderungsfenster zum Ordner mit der Datei "ReportBuilder3_x86.msi".</span><span class="sxs-lookup"><span data-stu-id="42d7d-120">In the command prompt window, navigate to the folder with ReportBuilder3_x86.msi.</span></span>  
  
4.  <span data-ttu-id="42d7d-121">Geben Sie eine Standardbefehlszeile wie im folgenden Beispiel ein:</span><span class="sxs-lookup"><span data-stu-id="42d7d-121">Type a basic command line such as the following:</span></span>  
  
 `msiexec /x ReportBuilder3_x86.msi /quiet /l*v install.log`  
  
 <span data-ttu-id="42d7d-122">Wenn Sie die Protokollierung einschließen möchten, verwenden Sie z. B. folgende Befehlszeile:</span><span class="sxs-lookup"><span data-stu-id="42d7d-122">If you can to include logging, use a command line such as the following:</span></span>  
  
 `msiexec /x ReportBuilder3_x86.msi /quiet /l*v c:\junk\install.log`  
  
1.  <span data-ttu-id="42d7d-123">Drücken Sie die **EINGABETASTE**.</span><span class="sxs-lookup"><span data-stu-id="42d7d-123">Press **Enter**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42d7d-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="42d7d-124">See Also</span></span>  
 <span data-ttu-id="42d7d-125">[Unterstützung für Installation, Deinstallation und Berichts-Generator](../install-uninstall-and-report-builder-support.md) </span><span class="sxs-lookup"><span data-stu-id="42d7d-125">[Install, Uninstall, and Report Builder Support](../install-uninstall-and-report-builder-support.md) </span></span>  
 [<span data-ttu-id="42d7d-126">Installieren Sie die eigenständige Version von Berichts-Generator &#40;Berichts-Generator&#41;</span><span class="sxs-lookup"><span data-stu-id="42d7d-126">Install the Stand-Alone Version of Report Builder &#40;Report Builder&#41;</span></span>](install-report-builder.md)  
  
  
