---
title: Debuggen von Übermittlungserweiterungscode | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], debugging
- debugging delivery extensions [Reporting Services]
- troubleshooting [Reporting Services], delivery extensions
ms.assetid: a7d959da-5005-4a50-aca7-2cef36aa9947
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fb80ac97f5c0e346b208784f1fa5b857ff93ef57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725242"
---
# <a name="debugging-delivery-extension-code"></a><span data-ttu-id="2f7d6-102">Debuggen von Übermittlungserweiterungscode</span><span class="sxs-lookup"><span data-stu-id="2f7d6-102">Debugging Delivery Extension Code</span></span>
  <span data-ttu-id="2f7d6-103">Das [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] stellt mehrere hilfreiche Tools zum Debuggen zur Verfügung, die Sie bei der Analyse des Codes für Übermittlungserweiterungen und bei der Fehlersuche darin unterstützen.</span><span class="sxs-lookup"><span data-stu-id="2f7d6-103">The [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] provides several debugging tools that can help you analyze your delivery extension code and locate errors in it.</span></span> <span data-ttu-id="2f7d6-104">Welches Tool dafür am besten geeignet ist, hängt von Ihrer Zielsetzung ab.</span><span class="sxs-lookup"><span data-stu-id="2f7d6-104">The tool that works best will depend on what you are trying to accomplish.</span></span> <span data-ttu-id="2f7d6-105">In diesem Beispiel wird [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] verwendet.</span><span class="sxs-lookup"><span data-stu-id="2f7d6-105">This example uses [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)].</span></span>  
  
#### <a name="to-debug-your-delivery-extension-code"></a><span data-ttu-id="2f7d6-106">So debuggen Sie Code für Übermittlungserweiterungen</span><span class="sxs-lookup"><span data-stu-id="2f7d6-106">To debug your delivery extension code</span></span>  
  
1.  <span data-ttu-id="2f7d6-107">Starten Sie [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)], und öffnen Sie das Projekt mit der Übermittlungserweiterung.</span><span class="sxs-lookup"><span data-stu-id="2f7d6-107">Launch [!INCLUDE[vsOrcas](../../../includes/vsorcas-md.md)] and open your delivery extension project.</span></span>  
  
2.  <span data-ttu-id="2f7d6-108">Erstellen Sie das Projekt, und stellen Sie die Assembly der Übermittlungserweiterung und die dazugehörige PDB-Datei im Berichtsserver und im Berichts-Manager bereit.</span><span class="sxs-lookup"><span data-stu-id="2f7d6-108">Build the project and deploy your delivery extension assembly and the accompanying .pdb file to the report server and Report Manager.</span></span> <span data-ttu-id="2f7d6-109">Weitere Informationen zur Bereitstellung finden Sie unter [Bereitstellen von Übermittlungserweiterungen](deploying-a-delivery-extension.md).</span><span class="sxs-lookup"><span data-stu-id="2f7d6-109">For more information about deployment, see [Deploying a Delivery Extension](deploying-a-delivery-extension.md).</span></span>  
  
3.  <span data-ttu-id="2f7d6-110">Wenn Sie eine Abonnementbenutzeroberfläche zur Erweiterung des Berichts-Managers geschrieben haben, öffnen Sie den Internet Explorer, und navigieren Sie zum Berichts-Manager, während Sie den Code der Übermittlungserweiterung in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] geöffnet lassen.</span><span class="sxs-lookup"><span data-stu-id="2f7d6-110">If you have written a subscription user interface to extend Report Manager, open Internet Explorer and navigate to Report Manager while leaving your delivery extension code open in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="2f7d6-111">Wenn Sie keine Abonnementbenutzeroberfläche auf dem Berichts-Manager eingesetzt haben, öffnen Sie einfach mithilfe der SOAP-API die Clientanwendung, von der Sie die Übermittlungserweiterung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="2f7d6-111">If you do not have a subscription user interface deployed for Report Manager, simply open the client application from which you call your delivery extension using the SOAP API.</span></span>  
  
4.  <span data-ttu-id="2f7d6-112">Wechseln Sie zu [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] und zum Projekt der Übermittlungserweiterung, und legen Sie einige Breakpoints im Code fest.</span><span class="sxs-lookup"><span data-stu-id="2f7d6-112">Navigate to [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] and your delivery extension project, and set some break points in your code.</span></span>  
  
5.  <span data-ttu-id="2f7d6-113">Während das Projekt mit der Übermittlungserweiterung noch immer im aktiven Fenster geöffnet ist, klicken Sie im Menü **Debuggen** auf **An den Prozess anhängen**.</span><span class="sxs-lookup"><span data-stu-id="2f7d6-113">With the delivery extension project still the active window, click **Attach to Process** on the **Debug** menu.</span></span>  
  
     <span data-ttu-id="2f7d6-114">Das Dialogfeld **An den Prozess anhängen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="2f7d6-114">The **Attach to Process** dialog opens.</span></span>  
  
6.  <span data-ttu-id="2f7d6-115">Wählen Sie aus der Liste der Prozesse „aspnet_wp.exe“ aus (oder „w3wp.exe“, wenn Ihre Anwendung unter IIS 6.0 läuft), und klicken Sie auf **Anfügen**.</span><span class="sxs-lookup"><span data-stu-id="2f7d6-115">From the list of processes, select the aspnet_wp.exe process (or w3wp.exe if your application is deployed on IIS 6.0), and click **Attach**.</span></span>  
  
7.  <span data-ttu-id="2f7d6-116">Definieren Sie mithilfe der Übermittlungserweiterung ein neues Abonnement.</span><span class="sxs-lookup"><span data-stu-id="2f7d6-116">Define a new subscription using your delivery extension.</span></span> <span data-ttu-id="2f7d6-117">Höchstwahrscheinlich verwenden Sie den Berichts-Manager oder die SOAP-API.</span><span class="sxs-lookup"><span data-stu-id="2f7d6-117">You will most likely use Report Manager or the SOAP API.</span></span> <span data-ttu-id="2f7d6-118">Dadurch sollte der Debugger aufgerufen und Code den Breakpoints gemäß ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2f7d6-118">This should invoke the debugger and execute code corresponding to your break points.</span></span>  
  
8.  <span data-ttu-id="2f7d6-119">Gehen Sie den Code schrittweise mit der Taste **F11** durch.</span><span class="sxs-lookup"><span data-stu-id="2f7d6-119">Step through your code using the **F11** key.</span></span> <span data-ttu-id="2f7d6-120">Weitere Informationen zum Debuggen mit [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] finden Sie in der Dokumentation zu [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f7d6-120">For more information about using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] for debugging, see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f7d6-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f7d6-121">See Also</span></span>  
 <span data-ttu-id="2f7d6-122">[Implementieren von Übermittlungserweiterungen](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="2f7d6-122">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="2f7d6-123">Reporting Services Extension Library (Reporting Services-Erweiterungsbibliothek)</span><span class="sxs-lookup"><span data-stu-id="2f7d6-123">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
