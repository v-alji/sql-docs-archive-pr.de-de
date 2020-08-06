---
title: Eingecheckte Dateien bearbeiten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- modifying checked-in files
- checking in files
ms.assetid: 560cd19f-ab22-4273-b00c-149993a630e6
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: e2dbe1aad203dfdc83e438d5b7f4ed19c15038c1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701625"
---
# <a name="edit-checked-in-files"></a><span data-ttu-id="d32d8-102">Bearbeiten eingecheckter Dateien</span><span class="sxs-lookup"><span data-stu-id="d32d8-102">Edit Checked-In Files</span></span>
  <span data-ttu-id="d32d8-103">In der Regel müssen Sie quellcodeverwaltete Dateien zunächst auschecken, bevor Sie sie bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="d32d8-103">You typically must check out source-controlled files before you can edit them.</span></span> <span data-ttu-id="d32d8-104">Sie können jedoch so konfigurieren [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , dass Sie Dateien ändern können, die Sie nicht ausgecheckt haben. Wenn Sie dies tun, werden die Änderungen im Arbeitsspeicher gespeichert, bis Sie die Dateien speichern.</span><span class="sxs-lookup"><span data-stu-id="d32d8-104">However, you can configure [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] so that you can modify files you have not checked out. When doing so, your changes are held in memory until you save the files.</span></span> <span data-ttu-id="d32d8-105">Sie werden dann aufgefordert, die Datei aus der Quellcodeverwaltung auszuchecken.</span><span class="sxs-lookup"><span data-stu-id="d32d8-105">You will then be prompted to check out the file from source control.</span></span>  
  
 <span data-ttu-id="d32d8-106">Beim teambasierten Arbeiten ist es nicht empfehlenswert, eingecheckte Dateien zur Bearbeitung freizugeben, es sei denn, der Quellcodeverwaltungsanbieter unterstützt das Auschecken von lokalen Versionen und von Serverversionen.</span><span class="sxs-lookup"><span data-stu-id="d32d8-106">If you work on a team, allowing checked-in files to be edited is not recommended unless your source control provider supports both local version and server version checkouts.</span></span> <span data-ttu-id="d32d8-107">Die meisten Anbieter unterstützen kein Auschecken lokaler Versionen.</span><span class="sxs-lookup"><span data-stu-id="d32d8-107">Most providers do not support local version checkouts.</span></span> <span data-ttu-id="d32d8-108">Wenn Ihr Anbieter kein Auschecken lokaler Versionen unterstützt und Sie eine eingecheckte Datei bearbeiten, müssen Sie die Versionen im Arbeitsspeicher und auf dem Server manuell zusammenführen, bevor die Datei eingecheckt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d32d8-108">If your provider does not support local version checkouts and you edit a checked-in file, you have to merge the in-memory and server versions manually before the file can be checked in.</span></span> <span data-ttu-id="d32d8-109">In diesem Fall werden automatische und vom Anbieter unterstützte Zusammenführungen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d32d8-109">Automatic and provider-assisted merges are unsupported in this situation.</span></span>  
  
### <a name="to-edit-checked-in-files"></a><span data-ttu-id="d32d8-110">So bearbeiten Sie eingecheckte Dateien</span><span class="sxs-lookup"><span data-stu-id="d32d8-110">To edit checked-in files</span></span>  
  
1.  <span data-ttu-id="d32d8-111">Klicken Sie im Menü **Extras** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="d32d8-111">On the **Tools** menu, click **Options**.</span></span>  
  
2.  <span data-ttu-id="d32d8-112">Erweitern Sie im Dialogfeld **Optionen** den Ordner **Quell**Ordner, und klicken Sie dann auf **Umgebung**.</span><span class="sxs-lookup"><span data-stu-id="d32d8-112">In the **Options** dialog box, expand the **Source Contro**l folder, and then click **Environment**.</span></span>  
  
3.  <span data-ttu-id="d32d8-113">Klicken Sie auf **zu bearbeitende eingegebene Elemente zulassen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d32d8-113">Click **Allow checked-in items to be edited**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d32d8-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d32d8-114">See Also</span></span>  
 <span data-ttu-id="d32d8-115">[Check-Ins verwalten](../../2014/database-engine/manage-checkins.md) </span><span class="sxs-lookup"><span data-stu-id="d32d8-115">[Manage Checkins](../../2014/database-engine/manage-checkins.md) </span></span>  
 [<span data-ttu-id="d32d8-116">Verwalten von Auscheckvorgängen</span><span class="sxs-lookup"><span data-stu-id="d32d8-116">Manage Checkouts</span></span>](../../2014/database-engine/manage-checkouts.md)  
  
  
