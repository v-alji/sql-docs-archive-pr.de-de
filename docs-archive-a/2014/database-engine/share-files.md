---
title: Freigeben von Dateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- sharing files
- file sharing [SQL Server]
- version control services [SQL Server], file sharing
ms.assetid: 645f5c0a-e949-4e87-8988-85e4d6128464
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 79909fcdb09e349798edfe285475f8a898c3bf04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724901"
---
# <a name="share-files"></a><span data-ttu-id="f0de0-102">Freigeben von Dateien</span><span class="sxs-lookup"><span data-stu-id="f0de0-102">Share Files</span></span>
  <span data-ttu-id="f0de0-103">Mit [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] können Sie Elemente über mehrere Quellcodeverwaltungsprojekte freigeben.</span><span class="sxs-lookup"><span data-stu-id="f0de0-103">You can use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to share items across source control projects.</span></span> <span data-ttu-id="f0de0-104">Wenn Sie ein Element freigeben, werden Änderungen an dem Element in den einzelnen Projekten angezeigt, für die das Element freigegeben ist.</span><span class="sxs-lookup"><span data-stu-id="f0de0-104">When you share an item, any changes to the item are reflected in every project to which the item is shared.</span></span>  
  
 <span data-ttu-id="f0de0-105">Benutzern der Quellcodeverwaltung bietet das Freigeben von Elementen die folgenden Vorteile:</span><span class="sxs-lookup"><span data-stu-id="f0de0-105">Item sharing provides the following advantages to source control users:</span></span>  
  
-   <span data-ttu-id="f0de0-106">Das Speichern einzelner Kopien des Elements für die einzelnen Projekte, die freigegebene Elemente verwenden, entfällt. Dadurch wird Speicherplatz auf dem Client und dem Server der Quellcodeverwaltung gespart.</span><span class="sxs-lookup"><span data-stu-id="f0de0-106">Makes it unnecessary for each project that uses the shared item to store a separate copy of the item, conserving disk space on both the source control client and server.</span></span> <span data-ttu-id="f0de0-107">Der Quellcodeverwaltungsanbieter speichert das freigegebene Element an einem zentralen Speicherort, und jedes Projekt, für das die Freigabe erfolgt, speichert einen Zeiger zu diesem Speicherort.</span><span class="sxs-lookup"><span data-stu-id="f0de0-107">The source control provider stores the shared item in one central location, and every project to which it is shared stores a pointer to that location.</span></span>  
  
-   <span data-ttu-id="f0de0-108">Inkompatibilitäten der Versionen werden vermieden.</span><span class="sxs-lookup"><span data-stu-id="f0de0-108">Avoids version incompatibilities.</span></span> <span data-ttu-id="f0de0-109">Da jedes Projekt, für das das Element freigegeben wird, dieselbe Version des Elements verwendet, vermeiden Sie die Konflikte, die durch unabhängig voneinander geänderten Kopien eines Elements in den einzelnen Projekten entstehen können.</span><span class="sxs-lookup"><span data-stu-id="f0de0-109">Because every project to which the item is shared uses the same version of the item, you avoid the conflicts that arise when each copy of an item is changing independently within multiple projects.</span></span>  
  
### <a name="to-share-an-item"></a><span data-ttu-id="f0de0-110">So geben Sie ein Element frei</span><span class="sxs-lookup"><span data-stu-id="f0de0-110">To share an item</span></span>  
  
1.  <span data-ttu-id="f0de0-111">Wählen Sie im Projektmappen-Explorer den Ordner oder das Projekt aus, in dem die freigegebenen Dateien platziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f0de0-111">In Solution Explorer, select either the folder or project in which you want to place the shared files.</span></span>  
  
2.  <span data-ttu-id="f0de0-112">Zeigen Sie im Menü **Datei** auf **Quell**Code Verwaltung, und klicken Sie dann auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="f0de0-112">On the **File** menu, point to **Source Control**, and then click **Share**.</span></span>  
  
3.  <span data-ttu-id="f0de0-113">Navigieren Sie im Dialogfeld **Freigeben mit** in der Verzeichnisliste für das Element, das Sie freigeben möchten, und klicken Sie auf dieses Element.</span><span class="sxs-lookup"><span data-stu-id="f0de0-113">In the **Share with** dialog box, browse the directory list for the item you want to share, and click that item.</span></span>  
  
4.  <span data-ttu-id="f0de0-114">Klicken Sie auf **Share** (Freigeben).</span><span class="sxs-lookup"><span data-stu-id="f0de0-114">Click **Share**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0de0-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0de0-115">See Also</span></span>  
 [<span data-ttu-id="f0de0-116">Grundlagen zur Quellcodeverwaltung</span><span class="sxs-lookup"><span data-stu-id="f0de0-116">Source Control Basics</span></span>](../../2014/database-engine/source-control-basics.md)  
  
  
