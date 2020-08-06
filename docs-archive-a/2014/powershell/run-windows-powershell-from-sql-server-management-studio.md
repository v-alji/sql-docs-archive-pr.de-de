---
title: Ausführen von Windows PowerShell über SQL Server Management Studio | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: 1f841825-da1f-4062-9a81-3cdbab03845b
author: stevestein
ms.author: sstein
ms.openlocfilehash: e0330e833aaa3344416a31aa700a2b1f6bb4a6e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617150"
---
# <a name="run-windows-powershell-from-sql-server-management-studio"></a><span data-ttu-id="0bb7b-102">Ausführen von Windows PowerShell über SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="0bb7b-102">Run Windows PowerShell from SQL Server Management Studio</span></span>
  <span data-ttu-id="0bb7b-103">Sie können Windows PowerShell-Sitzungen aus dem **Objekt-Explorer** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]starten.</span><span class="sxs-lookup"><span data-stu-id="0bb7b-103">You can start Windows PowerShell sessions from **Object Explorer** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]<span data-ttu-id="0bb7b-104">gestartet Windows PowerShell, lädt das `sqlps` -Modul und legt den Pfad Kontext auf den zugeordneten Knoten in der **Objekt-Explorer** Struktur fest.</span><span class="sxs-lookup"><span data-stu-id="0bb7b-104">launches Windows PowerShell, loads the `sqlps` module, and sets the path context to the associated node in the **Object Explorer** tree.</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="0bb7b-105">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="0bb7b-105">Before You Begin</span></span>  
 <span data-ttu-id="0bb7b-106">Wenn Sie die Ausführung von PowerShell für ein Objekt in **Objekt-Explorer**angeben, wird von [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] eine Windows PowerShell-Sitzung gestartet, in der die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell-Snap-Ins geladen und registriert wurden.</span><span class="sxs-lookup"><span data-stu-id="0bb7b-106">When you specify running PowerShell for an object in **Object Explorer**, [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] starts a Windows PowerShell session in which the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] PowerShell snap-ins have been loaded and registered.</span></span> <span data-ttu-id="0bb7b-107">Der Pfad für die Sitzung ist auf den Speicherort des Objekts, auf das Sie mit der rechten Maustaste geklickt haben, voreingestellt.</span><span class="sxs-lookup"><span data-stu-id="0bb7b-107">The path for the session is preset to the location of the object you right clicked in Object Explorer.</span></span> <span data-ttu-id="0bb7b-108">Wenn Sie beispielsweise im Objekt-Explorer mit der rechten Maustaste auf das Datenbankobjekt [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] klicken und dann **PowerShell starten**auswählen, wird der Windows PowerShell-Pfad folgendermaßen festgelegt:</span><span class="sxs-lookup"><span data-stu-id="0bb7b-108">For example, if you right-click the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database object in Object Explorer and select **Start PowerShell**, the Windows PowerShell path is set to the following:</span></span>  
  
```
SQLSERVER:\SQL\MyComputer\MyInstance\Databases\AdventureWorks2012>  
```  
  
## <a name="to-run-powershell-from-sql-server-management-studio"></a><span data-ttu-id="0bb7b-109">So führen Sie PowerShell in SQL Server Management Studio aus</span><span class="sxs-lookup"><span data-stu-id="0bb7b-109">To run PowerShell from SQL Server Management Studio</span></span> 
  
1.  <span data-ttu-id="0bb7b-110">Öffnen Sie **Objekt-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="0bb7b-110">Open **Object Explorer**.</span></span>  
  
2.  <span data-ttu-id="0bb7b-111">Navigieren Sie zum Knoten für das zu verarbeitende Objekt.</span><span class="sxs-lookup"><span data-stu-id="0bb7b-111">Navigate to the node for the object to be worked on.</span></span>  
  
3.  <span data-ttu-id="0bb7b-112">Klicken Sie mit der rechten Maustaste auf das Objekt, und wählen Sie **PowerShell starten**aus.</span><span class="sxs-lookup"><span data-stu-id="0bb7b-112">Right-click the object and select **Start PowerShell**.</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="0bb7b-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0bb7b-113">Permissions</span></span>  
 <span data-ttu-id="0bb7b-114">Wenn PowerShell in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)]geöffnet wurde, wird das Programm nicht mit Administratorrechten ausgeführt, wodurch einige Aktivitäten möglicherweise verhindert werden, z. B. Aufrufe der WMI.</span><span class="sxs-lookup"><span data-stu-id="0bb7b-114">When opened from [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], PowerShell does not run with Administrator privileges which may prevent some activities such as calls to WMI.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bb7b-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0bb7b-115">See Also</span></span>  
 [<span data-ttu-id="0bb7b-116">SQL Server-PowerShell</span><span class="sxs-lookup"><span data-stu-id="0bb7b-116">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
