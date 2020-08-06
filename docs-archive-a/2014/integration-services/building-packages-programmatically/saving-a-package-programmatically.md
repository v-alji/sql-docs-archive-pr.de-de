---
title: Programmgesteuertes Speichern von Paketen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- programmatically saving a package
- saving a package programmatically
ms.assetid: 4204f817-d5df-475a-9338-d7f01305d566
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2879c4213b2c9c0bf395c103de0d1bc37e4daab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616141"
---
# <a name="saving-a-package-programmatically"></a><span data-ttu-id="5db29-102">Programmgesteuertes Speichern von Paketen</span><span class="sxs-lookup"><span data-stu-id="5db29-102">Saving a Package Programmatically</span></span>
  <span data-ttu-id="5db29-103">Nachdem Sie ein neues Paket programmgesteuert erstellt oder ein vorhandenes geändert haben, sollten Sie Ihre Änderungen speichern.</span><span class="sxs-lookup"><span data-stu-id="5db29-103">After building a new package programmatically, or modifying an existing one, you usually want to save your changes.</span></span>  
  
 <span data-ttu-id="5db29-104">Alle in diesem Thema erläuterten Methoden zum Speichern von Paketen erfordern einen Verweis auf die `Microsoft.SqlServer.ManagedDTS`-Assembly.</span><span class="sxs-lookup"><span data-stu-id="5db29-104">All of the methods used in this topic to save packages require a reference to the `Microsoft.SqlServer.ManagedDTS` assembly.</span></span> <span data-ttu-id="5db29-105">Nachdem Sie den Verweis in einem neuen Projekt hinzugefügt haben, importieren Sie den <xref:Microsoft.SqlServer.Dts.Runtime>-Namespace mit einer `using`- oder `Imports`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="5db29-105">After you add the reference in a new project, import the <xref:Microsoft.SqlServer.Dts.Runtime> namespace with a `using` or `Imports` statement.</span></span>  
  
## <a name="saving-a-package-programmatically"></a><span data-ttu-id="5db29-106">Programmgesteuertes Speichern von Paketen</span><span class="sxs-lookup"><span data-stu-id="5db29-106">Saving a Package Programmatically</span></span>  
 <span data-ttu-id="5db29-107">Rufen Sie eine der folgenden Methoden der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <xref:Microsoft.SqlServer.Dts.Runtime.Application>-Klasse auf, um ein Paket programmgesteuert zu speichern:</span><span class="sxs-lookup"><span data-stu-id="5db29-107">To save a package programmatically, call one of the following methods of the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <xref:Microsoft.SqlServer.Dts.Runtime.Application> class:</span></span>  
  
|<span data-ttu-id="5db29-108">Speicherort</span><span class="sxs-lookup"><span data-stu-id="5db29-108">Storage Location</span></span>|<span data-ttu-id="5db29-109">Aufzurufende Methode</span><span class="sxs-lookup"><span data-stu-id="5db29-109">Method to Call</span></span>|  
|----------------------|--------------------|  
|<span data-ttu-id="5db29-110">Datei</span><span class="sxs-lookup"><span data-stu-id="5db29-110">File</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToXml%2A>|  
|<span data-ttu-id="5db29-111">SSIS-Paketspeicher</span><span class="sxs-lookup"><span data-stu-id="5db29-111">SSIS Package Store</span></span>|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToDtsServer%2A>|  
|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|<xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToSqlServer%2A><br /><br /> <span data-ttu-id="5db29-112">oder</span><span class="sxs-lookup"><span data-stu-id="5db29-112">or</span></span><br /><br /> <xref:Microsoft.SqlServer.Dts.Runtime.Application.SaveToSqlServerAs%2A>|  
  
> [!IMPORTANT]  
>  <span data-ttu-id="5db29-113">Die Methoden der <xref:Microsoft.SqlServer.Dts.Runtime.Application>-Klasse zum Arbeiten mit dem SSIS-Paketspeicher unterstützen nur "." oder den Namen des lokalen Servers.</span><span class="sxs-lookup"><span data-stu-id="5db29-113">The methods of the <xref:Microsoft.SqlServer.Dts.Runtime.Application> class for working with the SSIS Package Store only support "." or the server name for the local server.</span></span> <span data-ttu-id="5db29-114">"(local)" oder "localhost" können nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5db29-114">You cannot use "(local)" or "localhost".</span></span>  
  
<span data-ttu-id="5db29-115">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="5db29-115">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="5db29-116">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="5db29-116">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="5db29-117">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="5db29-117">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="5db29-118">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5db29-118">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5db29-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5db29-119">See Also</span></span>  
 [<span data-ttu-id="5db29-120">Speichern von Paketen</span><span class="sxs-lookup"><span data-stu-id="5db29-120">Save Packages</span></span>](../save-packages.md)  
  
  
