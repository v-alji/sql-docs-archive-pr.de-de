---
title: Shortcutabfragedateien (MDS-Add-In für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: 1ba0219a-6c40-41fa-aff9-8c8f41ef3220
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fe1bdbdadabe0e6448ed3bdc65316104fb26ba43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698372"
---
# <a name="shortcut-query-files-mds-add-in-for-excel"></a><span data-ttu-id="5cf5e-102">Shortcutabfragedateien (MDS-Add-In für Excel)</span><span class="sxs-lookup"><span data-stu-id="5cf5e-102">Shortcut Query Files (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="5cf5e-103">Verwenden Sie in [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]Shortcutabfragedateien, um häufig verwendete Daten schnell zu verbinden und zu laden.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)], use shortcut query files to quickly connect and load frequently-used data.</span></span> <span data-ttu-id="5cf5e-104">Sie können sie auch verwenden, wenn Sie MDS-Daten für andere freigeben möchten.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-104">You can also use them when you want to share MDS data with others.</span></span> <span data-ttu-id="5cf5e-105">Statt das Arbeitsblatt zu speichern und es per E-Mail zu senden, sollten Sie eine Shortcutabfragedatei speichern und stattdessen diese per E-Mail senden.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-105">Instead of saving the worksheet and emailing it, you should save a shortcut query file and email that instead.</span></span> <span data-ttu-id="5cf5e-106">Dadurch wird sichergestellt, dass Sie beide eine Verbindung mit dem MDS-Repository herstellen, um die aktuellsten Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-106">This ensures that you are both connecting to the MDS repository to get the latest data.</span></span>  
  
 <span data-ttu-id="5cf5e-107">Shortcutabfragedateien sind XML-Dateien, die Informationen über Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="5cf5e-107">Shortcut query files are XML files that contain information about:</span></span>  
  
-   <span data-ttu-id="5cf5e-108">Die MDS-Repositoryverbindung.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-108">The MDS repository connection.</span></span>  
  
-   <span data-ttu-id="5cf5e-109">Das Modell, die Version und die Entität.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-109">The model, version, and entity.</span></span>  
  
-   <span data-ttu-id="5cf5e-110">Alle Filter, die angewendet wurden, als die Verknüpfung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-110">Any filters that were applied when the shortcut was created.</span></span>  
  
-   <span data-ttu-id="5cf5e-111">Die Reihenfolge der Spalten von links nach rechts, als die Verknüpfung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-111">The left-to-right order of the columns when the shortcut was created.</span></span>  
  
 <span data-ttu-id="5cf5e-112">Sie können diese Dateien in einer Liste speichern und eine Auswahl treffen, wenn Sie das Add-In öffnen.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-112">You can save these files in a list and choose from them when you open the Add-in.</span></span> <span data-ttu-id="5cf5e-113">Sie können sie auf den Computer oder einen freigegebenen Speicherort exportieren, oder Sie können sie an andere senden.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-113">You can export them to your computer or to a shared location, or you can send them to others.</span></span>  
  
## <a name="queryopener-application"></a><span data-ttu-id="5cf5e-114">QueryOpener-Anwendung</span><span class="sxs-lookup"><span data-stu-id="5cf5e-114">QueryOpener Application</span></span>  
 <span data-ttu-id="5cf5e-115">Für alle Benutzer, die den [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] installieren, ist eine Anwendung mit dem Namen QueryOpener installiert.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-115">All users who install the [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] have an application called QueryOpener installed.</span></span> <span data-ttu-id="5cf5e-116">Diese Anwendung wird verwendet, um Shortcutabfragedateien im [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)]zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-116">This application is used to open shortcut query files in the [!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)].</span></span> <span data-ttu-id="5cf5e-117">Wenn Sie auf eine Shortcutabfragedatei doppelklicken, wird diese Anwendung automatisch zum Öffnen der Datei im Add-In verwendet.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-117">If you double-click a shortcut query file, this application is automatically used to open the file in the Add-in.</span></span>  
  
 <span data-ttu-id="5cf5e-118">Wenn Sie eine Shortcutabfragedatei mit dieser Anwendung öffnen, werden Sie aufgefordert, die Verbindung mit einer „sicheren“ Verbindung herzustellen. Dies bedeutet, dass Sie Inhalt von diesem Speicherort vertrauen.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-118">When you open a shortcut query file with this application, you are prompted to make the connection a "safe" connection, which means you trust content from this location.</span></span> <span data-ttu-id="5cf5e-119">Jedes Mal, wenn Sie eine Verbindung als sicher markieren, wird sie einer Liste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-119">Each time you mark a connection as safe, it is added to a list.</span></span> <span data-ttu-id="5cf5e-120">Wenn Sie diese Liste löschen möchten, öffnen Sie das Dialogfeld **Einstellungen** und klicken im Abschnitt **Zur sicheren Liste hinzugefügte Server** auf **Auswahl aufheben**.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-120">If you want to clear this list, open the **Settings** dialog box and in the **Servers Added to Safe List** section, click **Clear All**.</span></span>  
  
 <span data-ttu-id="5cf5e-121">Der Standard Speicherort für die Anwendung ist *Laufwerk*: \Programme\Microsoft SQL server\120\master Data services\excel Add-In\Microsoft.MasterDataServices.QueryOpener.exe.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-121">The default location for the application is *drive*:\Program Files\Microsoft SQL Server\120\Master Data Services\Excel Add-In\Microsoft.MasterDataServices.QueryOpener.exe.</span></span>  
  
 <span data-ttu-id="5cf5e-122">Es gibt zwei Möglichkeiten, Shortcutabfragedateien zu öffnen: Sie können sie importieren, oder Sie können auf sie doppelklicken und sie werden automatisch geöffnet.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-122">There are two ways to open shortcut query files: you can import them or you can double-click them and they are opened automatically.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="5cf5e-123">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="5cf5e-123">Related Tasks</span></span>  
  
|<span data-ttu-id="5cf5e-124">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="5cf5e-124">Task Description</span></span>|<span data-ttu-id="5cf5e-125">Thema</span><span class="sxs-lookup"><span data-stu-id="5cf5e-125">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="5cf5e-126">Speichern des Inhalts des aktiven Arbeitsblatts als Shortcutabfragedatei.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-126">Save the contents of the active worksheet as a shortcut query file.</span></span>|[<span data-ttu-id="5cf5e-127">Speichern einer Shortcutabfragedatei &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="5cf5e-127">Save a Shortcut Query File &#40;MDS Add-in for Excel&#41;</span></span>](save-a-shortcut-query-file-mds-add-in-for-excel.md)|  
|<span data-ttu-id="5cf5e-128">Senden Sie eine Shortcutabfragedatei, die den Inhalt des aktiven Arbeitsblatts darstellt.</span><span class="sxs-lookup"><span data-stu-id="5cf5e-128">Email a shortcut query file that represents the contents of the active worksheet.</span></span>|[<span data-ttu-id="5cf5e-129">Senden einer Shortcutabfragedatei &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="5cf5e-129">Email a Shortcut Query File &#40;MDS Add-in for Excel&#41;</span></span>](email-a-shortcut-query-file-mds-add-in-for-excel.md)|  
  
## <a name="related-content"></a><span data-ttu-id="5cf5e-130">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="5cf5e-130">Related Content</span></span>  
  
-   [<span data-ttu-id="5cf5e-131">Verbindungen &#40;MDS-Add-In für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="5cf5e-131">Connections &#40;MDS Add-in for Excel&#41;</span></span>](connections-mds-add-in-for-excel.md)  
  
-   [<span data-ttu-id="5cf5e-132">Master Data Services-Add-In für Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="5cf5e-132">Master Data Services Add-in for Microsoft Excel</span></span>](master-data-services-add-in-for-microsoft-excel.md)  
  
-   [<span data-ttu-id="5cf5e-133">Sicherheit &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5cf5e-133">Security &#40;Master Data Services&#41;</span></span>](../security-master-data-services.md)  
  
  
