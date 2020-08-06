---
title: Importieren der Richtlinien in eine einzelne Instanz | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: bc5bcd87-663f-41d9-bb7b-b3e083cd63df
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 0464bc6f4dcd6326a4b8f222cb4b3128f21561ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724301"
---
# <a name="import-the-policies-to-a-single-instance"></a><span data-ttu-id="1e18d-102">Importieren der Richtlinien auf eine einzelne Instanz</span><span class="sxs-lookup"><span data-stu-id="1e18d-102">Import the Policies to a Single Instance</span></span>
  <span data-ttu-id="1e18d-103">In diesem Task importieren Sie die Best Practices-Richtlinien, die Sie in der richtlinienbasierten Verwaltung zeitgesteuert ausführen möchten, auf eine einzelne Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1e18d-103">In this task, you will import the best practices policies that you want to schedule into Policy-Based Management on a single instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1e18d-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1e18d-104">Prerequisites</span></span>  
 <span data-ttu-id="1e18d-105">Sie müssen diese Prozedur auf einem Server ausführen, auf dem [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] oder eine höhere Version ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1e18d-105">You must perform this procedure on a server that is running [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] or a later version.</span></span>  
  
### <a name="import-the-best-practices-policies-for-the-database-engine"></a><span data-ttu-id="1e18d-106">Importieren der Best Practices-Richtlinien für die Datenbank-Engine</span><span class="sxs-lookup"><span data-stu-id="1e18d-106">Import the best practices policies for the Database Engine</span></span>  
  
1.  <span data-ttu-id="1e18d-107">Starten Sie [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], und stellen Sie dann eine Verbindung mit dem [!INCLUDE[ssDE](../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="1e18d-107">Start [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], and then connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="1e18d-108">Erweitern Sie im Objekt-Explorer **Verwaltung**, und erweitern Sie dann **Richtlinienverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="1e18d-108">In Object Explorer, expand **Management**, and then expand **Policy Management**.</span></span>  
  
3.  <span data-ttu-id="1e18d-109">Klicken Sie mit der rechten Maustaste auf **Richtlinien**und dann auf **Richtlinie importieren**.</span><span class="sxs-lookup"><span data-stu-id="1e18d-109">Right-click **Policies**, and then click **Import Policy**.</span></span>  
  
4.  <span data-ttu-id="1e18d-110">Klicken Sie im Dialogfeld **importieren** neben dem Feld **zu importierende Dateien** auf die Schaltfläche mit den Auslassungs Punkten (**...**).</span><span class="sxs-lookup"><span data-stu-id="1e18d-110">In the **Import** dialog box, next to the **Files to import** box, click the ellipsis (**...**) button.</span></span>  
  
5.  <span data-ttu-id="1e18d-111">Wechseln Sie in der Liste **Suchen in** zum folgenden Ordner, in dem die Best Practices-Richtlinien enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="1e18d-111">In the **Look in** list, browse to the following folder, which contains the best practices policies:</span></span>  
  
     <span data-ttu-id="1e18d-112">**C:\Programme (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span><span class="sxs-lookup"><span data-stu-id="1e18d-112">**C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="1e18d-113">Abhängig davon, wo die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Programmdateien installiert sind, ob ein 32-Bit- oder 64-Bit-Betriebssystem ausgeführt bzw. ein Sprachbezeichner verwendet wird, kann sich der Dateipfad ändern.</span><span class="sxs-lookup"><span data-stu-id="1e18d-113">The file path may vary, depending on where you installed the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] program files, whether you are running a 32-bit or 64-bit operating system, and the language identifier.</span></span>  
  
6.  <span data-ttu-id="1e18d-114">Wählen Sie im Dialogfeld **Richtlinie auswählen** mindestens eine Richtliniendatei aus.</span><span class="sxs-lookup"><span data-stu-id="1e18d-114">In the **Select Policy** dialog box, select one or more policy files.</span></span>  
  
     <span data-ttu-id="1e18d-115">Um nicht aufeinander folgende Dateien auszuwählen, klicken Sie auf eine Datei, halten die STRG-Taste gedrückt und klicken dann jeweils auf die nächste Datei.</span><span class="sxs-lookup"><span data-stu-id="1e18d-115">To select nonadjacent files, click one file, hold down the CTRL key, and then click each additional file.</span></span> <span data-ttu-id="1e18d-116">Um aufeinander folgende Dateien auszuwählen, klicken Sie auf die erste Datei in der Abfolge, halten Sie die UMSCHALTTASTE gedrückt und klicken dann auf die letzte Datei.</span><span class="sxs-lookup"><span data-stu-id="1e18d-116">To select adjacent files, click the first file in the sequence, hold down the SHIFT key, and then click the last file.</span></span>  
  
7.  <span data-ttu-id="1e18d-117">Nachdem Sie alle Dateien ausgewählt haben, klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="1e18d-117">When you are finished selecting files, click **Open**.</span></span>  
  
8.  <span data-ttu-id="1e18d-118">Stellen Sie im Dialogfeld **importieren** sicher, dass die Liste **Richtlinien Status** für den **Richtlinien Status beim Import beibehalten** (Standardeinstellung) festgelegt ist, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e18d-118">In the **Import** dialog box, make sure that the **Policy state** list is set to **Preserve policy state on import** (the default), and then click **OK**.</span></span>  
  
     <span data-ttu-id="1e18d-119">Die Richtlinien werden dann unter der **Richtlinienverwaltung** in den Knoten **Richtlinien**importiert.</span><span class="sxs-lookup"><span data-stu-id="1e18d-119">The policies are imported into the **Policies** node under **Policy Management**.</span></span> <span data-ttu-id="1e18d-120">Standardmäßig wird für die importierten Richtlinien der Auswertungsmodus "Bedarfsgesteuert" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1e18d-120">By default, the imported policies are set to "On demand" evaluation mode.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1e18d-121">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1e18d-121">Next Steps</span></span>  
 [<span data-ttu-id="1e18d-122">Planen der Richtlinien</span><span class="sxs-lookup"><span data-stu-id="1e18d-122">Schedule the Policies</span></span>](../../2014/tutorials/schedule-the-policies.md)  
  
  
