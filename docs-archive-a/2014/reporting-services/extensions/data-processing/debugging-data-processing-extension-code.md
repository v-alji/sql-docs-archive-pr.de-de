---
title: Debuggen von Code für Datenverarbeitungserweiterungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- debugging data processing extensions [Reporting Services]
- troubleshooting [Reporting Services], data processing extensions
- data processing extensions [Reporting Services], debugging
ms.assetid: e963e205-9ae0-446d-97df-028a1d2727d9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3bf7490145f91ee8b3cfc2357c34010bed593ed9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616938"
---
# <a name="debugging-data-processing-extension-code"></a><span data-ttu-id="e4554-102">Debuggen von Code für Datenverarbeitungserweiterungen</span><span class="sxs-lookup"><span data-stu-id="e4554-102">Debugging Data Processing Extension Code</span></span>
  <span data-ttu-id="e4554-103">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] umfasst mehrere Debugtools, mit denen Sie den Code für Ihr Datenverarbeitungserweiterung analysieren und enthaltene Fehler ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="e4554-103">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides several debugging tools that can help you analyze your data processing extension code and locate errors in it.</span></span> <span data-ttu-id="e4554-104">Welches Tool dafür am besten geeignet ist, hängt von Ihrer Zielsetzung ab.</span><span class="sxs-lookup"><span data-stu-id="e4554-104">The tool that works best will depend on what you are trying to accomplish.</span></span> <span data-ttu-id="e4554-105">In diesem Beispiel wird [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] verwendet.</span><span class="sxs-lookup"><span data-stu-id="e4554-105">This example uses [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span></span>  
  
#### <a name="to-debug-your-data-processing-extension-code"></a><span data-ttu-id="e4554-106">So debuggen Sie Code für Datenverarbeitungserweiterungen</span><span class="sxs-lookup"><span data-stu-id="e4554-106">To debug your data processing extension code</span></span>  
  
1.  <span data-ttu-id="e4554-107">Starten Sie [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)], und öffnen Sie das Projekt für die Datenverarbeitungserweiterung.</span><span class="sxs-lookup"><span data-stu-id="e4554-107">Launch [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)], and open your data processing extension project.</span></span>  
  
2.  <span data-ttu-id="e4554-108">Erstellen Sie das Projekt, und stellen Sie die Assembly der Datenverarbeitungserweiterung und die dazugehörige PDB-Datei im Berichts-Designer bereit.</span><span class="sxs-lookup"><span data-stu-id="e4554-108">Build the project, and deploy your data processing extension assembly and the accompanying .pdb file to the Report Designer.</span></span> <span data-ttu-id="e4554-109">Weitere Informationen zur Bereitstellung finden Sie unter [Vorgehensweise: Bereitstellen einer Datenverarbeitungserweiterung für den Berichts-Designer](deploying-a-data-processing-extension-to-report-designer.md).</span><span class="sxs-lookup"><span data-stu-id="e4554-109">For more information about deployment, see [How to: Deploy a Data Processing Extension to Report Designer](deploying-a-data-processing-extension-to-report-designer.md).</span></span>  
  
3.  <span data-ttu-id="e4554-110">Öffnen Sie ein neues Berichtsprojekt in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], ohne vorher den Code für die Datenverarbeitungserweiterungen in einem anderen Fenster von [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] zu schließen.</span><span class="sxs-lookup"><span data-stu-id="e4554-110">Open a new Report Project in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] while leaving your data processing extension code open in a separate window of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span>  
  
4.  <span data-ttu-id="e4554-111">Wechseln Sie zu dem [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]-Fenster, das das Projekt für die Datenverarbeitungserweiterung enthält, und legen Sie einige Breakpoints im Code fest.</span><span class="sxs-lookup"><span data-stu-id="e4554-111">Navigate to the window of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] that contains your data processing extension project and set some break points in your code.</span></span>  
  
5.  <span data-ttu-id="e4554-112">Klicken Sie im Menü **Debuggen** auf **An den Prozess anhängen**, während das Fenster des Projekts für die Datenverarbeitungserweiterung noch aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="e4554-112">With the data processing extension project window still active, click **Attach to Process** on the **Debug** menu.</span></span>  
  
     <span data-ttu-id="e4554-113">Das Dialogfeld **An den Prozess anhängen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e4554-113">The **Attach to Process** dialog opens.</span></span>  
  
6.  <span data-ttu-id="e4554-114">Wählen Sie aus der Liste der Prozesse den Prozess „devenv.exe“ aus, der dem Berichtsprojekt entspricht, und klicken Sie auf **Anfügen**.</span><span class="sxs-lookup"><span data-stu-id="e4554-114">From the list of processes, select the devenv.exe process that corresponds to your Report Project and click **Attach**.</span></span>  
  
7.  <span data-ttu-id="e4554-115">Definieren Sie mithilfe der Registerkarte **Berichtsdaten** des Berichtsprojekts die Berichtsdatenquelle.</span><span class="sxs-lookup"><span data-stu-id="e4554-115">Define your report data source using the **Report Data** tab of the Report Project.</span></span> <span data-ttu-id="e4554-116">Sie verwenden wahrscheinlich den generischen Abfrage-Designer, um eine Abfrage für die benutzerdefinierte Datenquelle auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e4554-116">You will most likely use the generic Query Designer to execute a query against your custom data source.</span></span> <span data-ttu-id="e4554-117">Dadurch sollte der Debugger aufgerufen und Code den Breakpoints gemäß ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e4554-117">This should invoke the debugger and execute code corresponding to your break points.</span></span>  
  
8.  <span data-ttu-id="e4554-118">Gehen Sie den Code schrittweise mit der F11-Taste durch.</span><span class="sxs-lookup"><span data-stu-id="e4554-118">Step through your code using the F11 key.</span></span> <span data-ttu-id="e4554-119">Weitere Informationen zum Debuggen mit [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] finden Sie in der Dokumentation zu [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e4554-119">For more information about using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] for debugging, see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4554-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e4554-120">See Also</span></span>  
 <span data-ttu-id="e4554-121">[Bereitstellen von Datenverarbeitungserweiterungen](deploying-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="e4554-121">[Deploying a Data Processing Extension](deploying-a-data-processing-extension.md) </span></span>  
 <span data-ttu-id="e4554-122">[Erweiterungen für Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="e4554-122">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="e4554-123">[Implementieren von Datenverarbeitungserweiterungen](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="e4554-123">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="e4554-124">Reporting Services Extension Library (Reporting Services-Erweiterungsbibliothek)</span><span class="sxs-lookup"><span data-stu-id="e4554-124">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
