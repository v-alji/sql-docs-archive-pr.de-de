---
title: Verweisen auf andere Assemblys in Skriptlösungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- SSIS Script task, .NET Framework
- Script task [Integration Services], adding references
- referencing custom assemblies
- SSIS Script task, VisualBasic namespace
- assemblies [Integration Services]
- VisualBasic namespace
- Script task [Integration Services], VisualBasic namespace
- Microsoft.VisualBasic namespace
- Script task [Integration Services], .NET Framework
- .NET Framework [Integration Services]
- referencing Web services
ms.assetid: 9b655bcd-19f6-43d8-9f89-1b4d299c6380
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 685bbaa62da88e84cd848eb49dcf5bedb03d5390
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609962"
---
# <a name="referencing-other-assemblies-in-scripting-solutions"></a><span data-ttu-id="e7093-102">Verweisen auf andere Assemblys in Skriptlösungen</span><span class="sxs-lookup"><span data-stu-id="e7093-102">Referencing Other Assemblies in Scripting Solutions</span></span>
  <span data-ttu-id="e7093-103">Die [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Klassenbibliothek bietet Skriptentwicklern leistungsfähige Tools zur Implementierung von benutzerdefinierten Funktionen in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Paketen.</span><span class="sxs-lookup"><span data-stu-id="e7093-103">The [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] class library provides the script developer with a powerful set of tools for implementing custom functionality in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="e7093-104">In Skripttasks und Skriptkomponenten können ebenfalls benutzerdefinierte verwaltete Assemblys verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7093-104">The Script task and the Script component can also use custom managed assemblies.</span></span>

> [!NOTE]
>  <span data-ttu-id="e7093-105">Damit Ihre Pakete die Objekte und Methoden eines Webdienstes verwenden können, setzen Sie den Befehl **Webverweis hinzufügen** in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA) ein.</span><span class="sxs-lookup"><span data-stu-id="e7093-105">To enable your packages to use the objects and methods from a Web service, use the **Add Web Reference** command available in [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Tools for Applications (VSTA).</span></span> <span data-ttu-id="e7093-106">In früheren Versionen von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] mussten Sie eine Proxyklasse generieren, um einen Webdienst zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e7093-106">In earlier versions of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you had to generate a proxy class to use a Web service.</span></span>

## <a name="using-a-managed-assembly"></a><span data-ttu-id="e7093-107">Verwenden einer verwalteten Assembly</span><span class="sxs-lookup"><span data-stu-id="e7093-107">Using a Managed Assembly</span></span>
 <span data-ttu-id="e7093-108">Damit [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] die verwaltete Assembly zur Entwurfszeit findet, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="e7093-108">For [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to find a managed assembly at design time, you must do the following steps:</span></span>

1.  <span data-ttu-id="e7093-109">Speichern Sie die verwaltete Assembly in einem beliebigen Ordner auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="e7093-109">Store the managed assembly in any folder on your computer.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="e7093-110">In früheren Versionen von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] konnten Sie nur einen Verweis auf eine verwaltete Assembly hinzufügen, die im Ordner %windir%\Microsoft.NET\Framework\vx.x.xxxxx oder unter %Programme%\Microsoft SQL Server\100\SDK\Assemblies gespeichert war.</span><span class="sxs-lookup"><span data-stu-id="e7093-110">In earlier versions of [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you could only add a reference to a managed assembly that was stored in the %windir%\Microsoft.NET\Framework\vx.x.xxxxx folder or the %ProgramFiles%\Microsoft SQL Server\100\SDK\Assemblies folder.</span></span>

2.  <span data-ttu-id="e7093-111">Fügen Sie einen Verweis auf die verwaltete Assembly hinzu.</span><span class="sxs-lookup"><span data-stu-id="e7093-111">Add a reference to the managed assembly.</span></span>

     <span data-ttu-id="e7093-112">Um den Verweis hinzuzufügen, klicken Sie in VSTA im Dialogfeld **Verweis hinzufügen** auf die Registerkarte **Durchsuchen**. Wenn Sie die verwaltete Assembly gefunden haben, fügen Sie sie hinzu.</span><span class="sxs-lookup"><span data-stu-id="e7093-112">To add the reference, in VSTA, in the **Add Reference** dialog box, on the **Browse** tab, locate and add the managed assembly.</span></span>

 <span data-ttu-id="e7093-113">Damit [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] die verwaltete Assembly zur Laufzeit findet, müssen Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="e7093-113">For [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] to find the managed assembly at run time, you must do the following steps:</span></span>

1.  <span data-ttu-id="e7093-114">Signieren Sie die verwaltete Assembly mit einem starken Namen.</span><span class="sxs-lookup"><span data-stu-id="e7093-114">Sign the managed assembly with a strong name.</span></span>

2.  <span data-ttu-id="e7093-115">Installieren Sie die Assembly im globalen Assemblycache auf dem Computer, auf dem das Paket ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e7093-115">Install the assembly in the global assembly cache on the computer on which the package is run.</span></span>

     <span data-ttu-id="e7093-116">Weitere Informationen finden Sie unter [Building, Deploying, and Debugging Custom Objects](../extending-packages-custom-objects/building-deploying-and-debugging-custom-objects.md) (Erstellen, Bereitstellen und Debuggen von benutzerdefinierten Objekten).</span><span class="sxs-lookup"><span data-stu-id="e7093-116">For more information, see [Building, Deploying, and Debugging Custom Objects](../extending-packages-custom-objects/building-deploying-and-debugging-custom-objects.md).</span></span>

## <a name="using-the-microsoft-net-framework-class-library"></a><span data-ttu-id="e7093-117">Verwenden der Microsoft .NET Framework-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="e7093-117">Using the Microsoft .NET Framework Class Library</span></span>
 <span data-ttu-id="e7093-118">Der Skripttask und die Skriptkomponente können alle anderen Objekte und Funktionen, die von der [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Klassenbibliothek bereitgestellt werden, nutzen.</span><span class="sxs-lookup"><span data-stu-id="e7093-118">The Script task and the Script component can take advantage of all the other objects and functionality exposed by the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] class library.</span></span> <span data-ttu-id="e7093-119">Durch Verwendung von [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] können Sie beispielsweise Informationen zu Ihrer Umgebung abrufen und mit dem Computer interagieren, der das Paket ausführt.</span><span class="sxs-lookup"><span data-stu-id="e7093-119">For example, by using the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], you can retrieve information about your environment and interact with the computer that is running the package.</span></span>

 <span data-ttu-id="e7093-120">In dieser Liste werden einige der häufig verwendeten [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Klassen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="e7093-120">This list describes several of the more frequently used [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes:</span></span>

-   <span data-ttu-id="e7093-121">`System.Data`Enthält die ADO.NET-Architektur.</span><span class="sxs-lookup"><span data-stu-id="e7093-121">`System.Data` Contains the ADO.NET architecture.</span></span>

-   <span data-ttu-id="e7093-122">`System.IO`Stellt eine Schnittstelle für das Dateisystem und Streams bereit.</span><span class="sxs-lookup"><span data-stu-id="e7093-122">`System.IO` Provides an interface to the file system and streams.</span></span>

-   <span data-ttu-id="e7093-123">`System.Windows.Forms`Stellt die Formular Erstellung bereit.</span><span class="sxs-lookup"><span data-stu-id="e7093-123">`System.Windows.Forms` Provides form creation.</span></span>

-   <span data-ttu-id="e7093-124">`System.Text.RegularExpressions`Stellt Klassen zum Arbeiten mit regulären Ausdrücken bereit.</span><span class="sxs-lookup"><span data-stu-id="e7093-124">`System.Text.RegularExpressions` Provides classes for working with regular expressions.</span></span>

-   <span data-ttu-id="e7093-125">`System.Environment`Gibt Informationen über den lokalen Computer, den aktuellen Benutzer sowie die Computer-und Benutzereinstellungen zurück.</span><span class="sxs-lookup"><span data-stu-id="e7093-125">`System.Environment` Returns information about the local computer, the current user, and computer and user settings.</span></span>

-   <span data-ttu-id="e7093-126">`System.Net`Ermöglicht die Netzwerkkommunikation.</span><span class="sxs-lookup"><span data-stu-id="e7093-126">`System.Net` Provides network communications.</span></span>

-   <span data-ttu-id="e7093-127">`System.DirectoryServices`Macht Active Directory verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e7093-127">`System.DirectoryServices` Exposes Active Directory.</span></span>

-   <span data-ttu-id="e7093-128">`System.Drawing`Stellt umfangreiche Bild Bearbeitungs Bibliotheken bereit.</span><span class="sxs-lookup"><span data-stu-id="e7093-128">`System.Drawing` Provides extensive image manipulation libraries.</span></span>

-   <span data-ttu-id="e7093-129">`System.Threading`Ermöglicht Multithreadprogrammierung.</span><span class="sxs-lookup"><span data-stu-id="e7093-129">`System.Threading` Enables multithreaded programming.</span></span>

 <span data-ttu-id="e7093-130">Weitere Informationen über [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] finden Sie in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="e7093-130">For more information about the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], see the MSDN Library.</span></span>

<span data-ttu-id="e7093-131">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="e7093-131">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="e7093-132">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="e7093-132">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="e7093-133">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="e7093-133">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="e7093-134">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e7093-134">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7093-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e7093-135">See Also</span></span>
 [<span data-ttu-id="e7093-136">Erweitern von Paketen mit Skripts</span><span class="sxs-lookup"><span data-stu-id="e7093-136">Extending Packages with Scripting</span></span>](extending-packages-with-scripting.md)


