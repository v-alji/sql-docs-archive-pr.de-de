---
title: 'Lektion 2: Vorbereiten des Momentaufnahmeordners | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
ms.assetid: f286cde9-c0d0-43ef-b7ba-53c3cbb8906c
author: rothja
ms.author: jroth
ms.openlocfilehash: 5d98c7433d0bd50504f20f7f576fcf0b20154c81
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723702"
---
# <a name="lesson-2-preparing-the-snapshot-folder"></a><span data-ttu-id="4628c-102">Lektion 2: Vorbereiten des Momentaufnahmeordners</span><span class="sxs-lookup"><span data-stu-id="4628c-102">Lesson 2: Preparing the Snapshot Folder</span></span>
  <span data-ttu-id="4628c-103">In dieser Lektion erfahren Sie, wie Sie den Momentaufnahmeordner konfigurieren, in dem die Veröffentlichungsmomentaufnahme erstellt und gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="4628c-103">In this lesson, you will learn to configure the snapshot folder that is used to create and store the publication snapshot.</span></span>  
  
### <a name="to-create-a-share-for-the-snapshot-folder-and-assign-permissions"></a><span data-ttu-id="4628c-104">So erstellen Sie eine Freigabe für den Momentaufnahmeordner und weisen Berechtigungen zu</span><span class="sxs-lookup"><span data-stu-id="4628c-104">To create a share for the snapshot folder and assign permissions</span></span>  
  
1.  <span data-ttu-id="4628c-105">Navigieren Sie im Windows-Explorer zum [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenordner.</span><span class="sxs-lookup"><span data-stu-id="4628c-105">In Windows Explorer, navigate to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data folder.</span></span> <span data-ttu-id="4628c-106">Der Standardspeicherort lautet C:\Programme\Microsoft SQL Server\MSSQL.X\MSSQL\Data.</span><span class="sxs-lookup"><span data-stu-id="4628c-106">The default location is C:\Program Files\Microsoft SQL Server\MSSQL.X\MSSQL\Data.</span></span>  
  
2.  <span data-ttu-id="4628c-107">Erstellen Sie einen neuen Ordner mit dem Namen **repldata**.</span><span class="sxs-lookup"><span data-stu-id="4628c-107">Create a new folder named **repldata**.</span></span>  
  
3.  <span data-ttu-id="4628c-108">Klicken Sie mit der rechten Maustaste auf den Ordner, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="4628c-108">Right-click this folder and click **Properties**.</span></span>  
  
4.  <span data-ttu-id="4628c-109">Klicken Sie auf der Registerkarte **Freigabe** im Dialogfeld **Eigenschaften von repldata** auf **Freigeben**.</span><span class="sxs-lookup"><span data-stu-id="4628c-109">On the **Sharing** tab in the **repldata Properties** dialog box, click **Share**.</span></span>  
  
5.  <span data-ttu-id="4628c-110">Klicken Sie im Dialogfeld **Dateifreigabe** auf **Freigeben**und anschließend auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="4628c-110">In the **File Sharing** dialog box, click **Share**, and then click **Done**.</span></span>  
  
6.  <span data-ttu-id="4628c-111">Klicken Sie auf der Registerkarte **Sicherheit** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="4628c-111">On the **Security** tab, click **Edit**.</span></span>  
  
7.  <span data-ttu-id="4628c-112">Klicken Sie im Dialogfeld **Berechtigungen** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4628c-112">In the **Permissions** dialog box, click **Add.**</span></span> <span data-ttu-id="4628c-113">Geben Sie im Textfeld **Benutzer, Computer, Dienst Konto oder Gruppen auswählen** den Namen des in Lektion 1 erstellten Momentaufnahmen-Agent Kontos wie \<_Machine_Name> _**\ repl_snapshot**ein, wobei \<*Machine_Name> \* der Name des Verlegers ist.</span><span class="sxs-lookup"><span data-stu-id="4628c-113">In the **Select User, Computers, Service Account, or Groups** text box, type the name of the Snapshot Agent account created in Lesson 1, as \<_Machine_Name>_**\repl_snapshot**, where \<*Machine_Name>\* is the name of the Publisher.</span></span> <span data-ttu-id="4628c-114">Klicken Sie auf **Namen überprüfen**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4628c-114">Click **Check Names**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="4628c-115">Wiederholen Sie den vorherigen Schritt, um Berechtigungen für den Verteilungs-Agent, wie \<_Machine_Name> _ **\ repl_distribution**, und für die \<_Machine_Name> Merge-Agent als _ **\ repl_merge**hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4628c-115">Repeat the previous step to add permissions for the Distribution Agent, as \<_Machine_Name>_**\repl_distribution**, and for the Merge Agent as \<_Machine_Name>_**\repl_merge**.</span></span>  
  
9. <span data-ttu-id="4628c-116">Überprüfen Sie, ob die folgenden Berechtigungen gewährt wurden.</span><span class="sxs-lookup"><span data-stu-id="4628c-116">Verify the following permissions are allowed:</span></span>  
  
    -   <span data-ttu-id="4628c-117">repl_snapshot - Vollzugriff</span><span class="sxs-lookup"><span data-stu-id="4628c-117">repl_snapshot - Full Control</span></span>  
  
    -   <span data-ttu-id="4628c-118">repl_distribution - Lesezugriff</span><span class="sxs-lookup"><span data-stu-id="4628c-118">repl_distribution - Read</span></span>  
  
    -   <span data-ttu-id="4628c-119">repl_merge - Lesezugriff</span><span class="sxs-lookup"><span data-stu-id="4628c-119">repl_merge - Read</span></span>  
  
10. <span data-ttu-id="4628c-120">Klicken Sie auf **OK** , um das Dialogfeld **Eigenschaften von repldata** zu schließen und die repldata-Freigabe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4628c-120">Click **OK** to close the **repldata Properties** dialog box and create the repldata share.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4628c-121">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4628c-121">Next Steps</span></span>  
 <span data-ttu-id="4628c-122">Sie haben erfolgreich eine Freigabe für den Momentaufnahmeordner konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4628c-122">You have successfully configured the share for the snapshot folder.</span></span> <span data-ttu-id="4628c-123">Im nächsten Arbeitsschritt konfigurieren Sie die Verteilung.</span><span class="sxs-lookup"><span data-stu-id="4628c-123">Next, you will configure distribution.</span></span> <span data-ttu-id="4628c-124">Weitere Informationen finden Sie unter [Lektion 3: Konfigurieren der Verteilung](lesson-3-configuring-distribution.md).</span><span class="sxs-lookup"><span data-stu-id="4628c-124">See [Lesson 3: Configuring Distribution](lesson-3-configuring-distribution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4628c-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4628c-125">See Also</span></span>  
 [<span data-ttu-id="4628c-126">Sichern des Momentaufnahmeordners</span><span class="sxs-lookup"><span data-stu-id="4628c-126">Secure the Snapshot Folder</span></span>](security/secure-the-snapshot-folder.md)  
  
  
