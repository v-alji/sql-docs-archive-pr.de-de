---
title: Protokollieren in der Skriptkomponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], logging
ms.assetid: 17c19787-379e-43fe-9107-e36e17ecda53
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4c29dfffee6cacb39272aef07caa5539555cdd4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619207"
---
# <a name="logging-in-the-script-component"></a><span data-ttu-id="3fe1d-102">Protokollieren in der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="3fe1d-102">Logging in the Script Component</span></span>
  <span data-ttu-id="3fe1d-103">Durch die Protokollierung in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)]-Paketen können Sie detaillierte Informationen zum Fortschritt sowie über die Ergebnisse und Probleme der Ausführung speichern, indem Sie vordefinierte Ereignisse bzw. benutzerdefinierte Meldungen für die spätere Analyse erfassen.</span><span class="sxs-lookup"><span data-stu-id="3fe1d-103">Logging in [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] packages lets you save detailed information about execution progress, results, and problems by recording predefined events or user-defined messages for later analysis.</span></span> <span data-ttu-id="3fe1d-104">Die Skriptkomponente kann die <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A>-Methode der `ScriptMain`-Klasse verwenden, um benutzerdefinierte Daten zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="3fe1d-104">The Script component can use the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method of the `ScriptMain` class to log user-defined data.</span></span> <span data-ttu-id="3fe1d-105">Wenn die Protokollierung aktiviert ist und in der Registerkarte **Details** des Dialogfelds **SSIS-Protokolle konfigurieren** das Ereignis **ScriptComponentLogEntry** für die Protokollierung ausgewählt ist, dann speichert ein einzelner Aufruf der <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A>-Methode die Ereignisinformationen in allen Protokollanbietern, die für den Datenflusstask konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="3fe1d-105">If logging is enabled, and the **ScriptComponentLogEntry** event is selected for logging on the **Details** tab of the **Configure SSIS Logs** dialog box, a single call to the <xref:Microsoft.SqlServer.Dts.Pipeline.ScriptComponent.Log%2A> method stores the event information in all the log providers that have been configured for the data flow task.</span></span>  
  
 <span data-ttu-id="3fe1d-106">Im Folgenden ein einfaches Beispiel für die Protokollierung:</span><span class="sxs-lookup"><span data-stu-id="3fe1d-106">Here is a simple example of logging:</span></span>  
  
 `Dim bt(0) As Byte`  
  
 `Me.Log("Test Log Event", _`  
  
 `0, _`  
  
 `bt)`  
  
> [!NOTE]  
>  <span data-ttu-id="3fe1d-107">Obwohl Sie Protokollierungen direkt von der Skriptkomponente ausführen können, ist ggf. eine Implementierung von Ereignissen einer Protokollierung vorzuziehen.</span><span class="sxs-lookup"><span data-stu-id="3fe1d-107">Although you can perform logging directly from your Script component, you may want to consider implementing events rather than logging.</span></span> <span data-ttu-id="3fe1d-108">Bei der Verwendung von Ereignissen können Sie nicht nur die Protokollierung von Ereignismeldungen aktivieren, sondern auch auf das Ereignis mit standardmäßigen oder benutzerdefinierten Ereignishandlern reagieren.</span><span class="sxs-lookup"><span data-stu-id="3fe1d-108">When using events, not only can you enable the logging of event messages, but you can respond to the event with default or user-defined event handlers.</span></span>  
  
 <span data-ttu-id="3fe1d-109">Weitere Informationen zur Protokollierung finden Sie unter [Integration Services-Protokollierung &#40;SSIS&#41;](../../performance/integration-services-ssis-logging.md).</span><span class="sxs-lookup"><span data-stu-id="3fe1d-109">For more information about logging, see [Integration Services &#40;SSIS&#41; Logging](../../performance/integration-services-ssis-logging.md).</span></span>  
  
<span data-ttu-id="3fe1d-110">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="3fe1d-110">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="3fe1d-111">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="3fe1d-111">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="3fe1d-112">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="3fe1d-112">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="3fe1d-113">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3fe1d-113">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fe1d-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3fe1d-114">See Also</span></span>  
 [<span data-ttu-id="3fe1d-115">Integration Services-Protokollierung &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="3fe1d-115">Integration Services &#40;SSIS&#41; Logging</span></span>](../../performance/integration-services-ssis-logging.md)  
  
  
