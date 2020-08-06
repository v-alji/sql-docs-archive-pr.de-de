---
title: In Paket Bereitstellungs Modell konvertieren (Dialog Feld) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.bids.converttolegacydeployment.f1
ms.assetid: 9e60a34a-10f7-48d1-966f-b3ff236ab4b7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b52932ad26f8cebd2e67b0025f4b881241119f6e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618839"
---
# <a name="convert-to-package-deployment-model-dialog-box"></a><span data-ttu-id="b88f9-102">In Paketbereitstellungsmodell konvertieren (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="b88f9-102">Convert to Package Deployment Model Dialog Box</span></span>
  <span data-ttu-id="b88f9-103">Mit dem Befehl **In Paketbereitstellungsmodell konvertieren** können Sie ein Paket auf dem Paketbereitstellungsmodell konvertieren, nachdem das Projekt und jedes Paket im Projekt auf Kompatibilität mit dem Modell überprüft wurden.</span><span class="sxs-lookup"><span data-stu-id="b88f9-103">The **Convert to Package Deployment Model** command allows you to convert a package to the package deployment model after checking the project and each package in the project for compatibility with that model.</span></span> <span data-ttu-id="b88f9-104">Wenn ein Paket für ein Projektbereitstellungsmodell eindeutige Funktionen verwendet, z. B. Parameter, dann kann das Paket nicht konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="b88f9-104">If a package uses features unique to the project deployment model, such as parameters, then the package cannot be converted.</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="b88f9-105">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="b88f9-105">Task List</span></span>  
 <span data-ttu-id="b88f9-106">Für das Konvertieren eines Pakets auf ein Paketbereitstellungsmodell sind zwei Schritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b88f9-106">Converting a package to the package deployment model requires two steps.</span></span>  
  
1.  <span data-ttu-id="b88f9-107">Wenn Sie den Befehl **In Paketbereitstellungsmodell konvertieren** aus dem Menü **Projekt** auswählen, werden das Projekt und jedes Paket auf Kompatibilität mit diesem Modell überprüft.</span><span class="sxs-lookup"><span data-stu-id="b88f9-107">When you select the **Convert to Package Deployment Model** command from the **Project** menu, the project and each package are checked for compatibility with this model.</span></span> <span data-ttu-id="b88f9-108">Die Ergebnisse werden in der Tabelle **Ergebnisse** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b88f9-108">The results are displayed in the **Results** table.</span></span>  
  
     <span data-ttu-id="b88f9-109">Wenn das Projekt oder ein Paket den Kompatibilitätstest nicht besteht, klicken Sie in der Spalte **Ergebnis** auf **Fehler** , um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b88f9-109">If the project or a package fails the compatibility test, click **Failed** in the **Result** column for more information.</span></span> <span data-ttu-id="b88f9-110">Klicken Sie auf **Bericht speichern** , um eine Kopie dieser Informationen in einer Textdatei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b88f9-110">Click **Save Report** to save a copy of this information to a text file.</span></span>  
  
2.  <span data-ttu-id="b88f9-111">Wenn das Projekt und alle Pakete den Kompatibilitätstest bestehen, klicken Sie auf **OK** , um das Paket zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="b88f9-111">If the project and all packages pass the compatibility test, then click **OK** to convert the package.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b88f9-112">Verwenden Sie den **Assistenten für die Konvertierung von Integration Services-Projekten**, um ein Projekt ins Projektbereitstellungsmodell zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="b88f9-112">To convert a project to the project deployment model, use the **Integration Services Project Conversion Wizard**.</span></span> <span data-ttu-id="b88f9-113">Weitere Informationen finden Sie unter [Integration Services Project Conversion Wizard](../../2014/integration-services/integration-services-project-conversion-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="b88f9-113">For more information, see [Integration Services Project Conversion Wizard](../../2014/integration-services/integration-services-project-conversion-wizard.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b88f9-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b88f9-114">See Also</span></span>  
 <span data-ttu-id="b88f9-115">[Bereitstellung von Projekten und Paketen](packages/deploy-integration-services-ssis-projects-and-packages.md) </span><span class="sxs-lookup"><span data-stu-id="b88f9-115">[Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md) </span></span>  
 <span data-ttu-id="b88f9-116">[Paket Bereitstellung &#40;SSIS-&#41;](packages/legacy-package-deployment-ssis.md) </span><span class="sxs-lookup"><span data-stu-id="b88f9-116">[Package Deployment &#40;SSIS&#41;](packages/legacy-package-deployment-ssis.md) </span></span>  
 [<span data-ttu-id="b88f9-117">Assistent für die Konvertierung von Integration Services-Projekten</span><span class="sxs-lookup"><span data-stu-id="b88f9-117">Integration Services Project Conversion Wizard</span></span>](../../2014/integration-services/integration-services-project-conversion-wizard.md)  
  
  
