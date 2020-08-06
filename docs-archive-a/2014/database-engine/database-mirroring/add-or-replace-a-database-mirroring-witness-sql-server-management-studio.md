---
title: Hinzufügen oder Ersetzen eines Datenbank-Spiegelungszeugen (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- witness [SQL Server], establishing
- database mirroring [SQL Server], witness
ms.assetid: 4b5ecffd-f025-4ab7-b69d-8958c6477127
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5dd14ace23956ceef114f1f032b5d4db5febcec7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615586"
---
# <a name="add-or-replace-a-database-mirroring-witness-sql-server-management-studio"></a><span data-ttu-id="ed6c7-102">Hinzufügen oder Ersetzen eines Datenbank-Spiegelungszeugen (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="ed6c7-102">Add or Replace a Database Mirroring Witness (SQL Server Management Studio)</span></span>
  <span data-ttu-id="ed6c7-103">Wenn die Endpunkte für die Datenbankspiegelung die Windows-Authentifizierung verwenden, können Sie mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] einen Zeugen hinzufügen oder ersetzen.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-103">If the database mirroring endpoints use Windows Authentication,, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to add or replace a witness.</span></span> <span data-ttu-id="ed6c7-104">Beim Hinzufügen eines Zeugen in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] wird auch der Betriebsmodus in den Modus für hohe Sicherheit mit automatischem Failover geändert.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-104">Adding a witness in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)] also changes the operating mode to high-safety mode with automatic failover.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ed6c7-105">Sie sollten den Zeugen unbedingt auf einem von den Partnern separaten Computer platzieren.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-105">We strongly recommend that the witness reside on a separate computer from either of the partners.</span></span> <span data-ttu-id="ed6c7-106">Das vom Zeugen verwendete Dienstkonto muss sich in derselben Domäne wie die von der Prinzipalserver- und Spiegelserverinstanz verwendeten Dienstkonten befinden oder in einer vertrauenswürdigen Domäne.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-106">The service account used by the witness must be in the same domain as the service accounts used by the principal and mirror server instances, or it must be in a trusted domain.</span></span>  
  
### <a name="to-add-or-replace-a-witness"></a><span data-ttu-id="ed6c7-107">So fügen Sie einen Zeugen hinzu oder ersetzen ihn</span><span class="sxs-lookup"><span data-stu-id="ed6c7-107">To Add or Replace a Witness</span></span>  
  
1.  <span data-ttu-id="ed6c7-108">Nachdem Sie eine Verbindung mit der Prinzipalserverinstanz hergestellt haben, klicken Sie im Objekt-Explorer auf den Servernamen, um die Serverstruktur zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-108">After connecting to the principal server instance, in Object Explorer, click the server name to expand the server tree.</span></span>  
  
2.  <span data-ttu-id="ed6c7-109">Erweitern Sie **Datenbanken**, und wählen Sie die Prinzipaldatenbank der Sitzung aus, für die Sie einen Zeugen hinzufügen oder ersetzen.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-109">Expand **Databases**, and select the principal database of the session to which you are adding or replacing a witness.</span></span>  
  
3.  <span data-ttu-id="ed6c7-110">Klicken Sie mit der rechten Maustaste auf die Datenbank, wählen Sie **Tasks**aus, und klicken Sie dann auf **Spiegeln**.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-110">Right-click the database, select **Tasks**, and then click **Mirror**.</span></span> <span data-ttu-id="ed6c7-111">Dadurch wird die Seite **Spiegelung** im Dialogfeld **Datenbankeigenschaften** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-111">This opens the **Mirroring** page of the **Database Properties** dialog box.</span></span>  
  
4.  <span data-ttu-id="ed6c7-112">Klicken Sie auf **Sicherheit konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-112">Click **Configure Security**.</span></span>  
  
5.  <span data-ttu-id="ed6c7-113">Wenn die Willkommenseite des **Assistenten zum Konfigurieren der Sicherheit für die Datenbankspiegelung** angezeigt wird, klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-113">If the **Configure Database Mirroring Security Wizard** welcome screen appears, click **Next**.</span></span>  
  
6.  <span data-ttu-id="ed6c7-114">Klicken Sie im Dialogfeld **Zeugenserver einschließen** auf **Ja**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-114">In the **Include Witness Server** dialog box, click **Yes**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="ed6c7-115">Im Dialogfeld **Zu konfigurierende Server auswählen** ist das Kontrollkästchen **Zeugenserverinstanz** automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-115">In the **Choose Servers to Configure** dialog box, the **Witness server instance** check box is automatically checked.</span></span> <span data-ttu-id="ed6c7-116">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-116">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="ed6c7-117">Behalten Sie im Dialogfeld **Prinzipalserverinstanz** den vorhandenen Port und Endpunkt bei.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-117">On the **Principal Server Instance** dialog box, keep the existing port and endpoint.</span></span> <span data-ttu-id="ed6c7-118">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-118">Click **Next**.</span></span>  
  
9. <span data-ttu-id="ed6c7-119">Klicken Sie im Dialogfeld **Zeugenserverinstanz** auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-119">On the **Witness Server Instance** dialog box, click **Connect**.</span></span>  
  
10. <span data-ttu-id="ed6c7-120">Geben Sie im Dialogfeld **Verbindung mit Server herstellen** im Textfeld **Servername** die Zeugenserverinstanz an, und verwenden Sie die Windows-Authentifizierung (die Standardeinstellung).</span><span class="sxs-lookup"><span data-stu-id="ed6c7-120">In the **Connect to Server** dialog box, specify the witness server instance in the **Server name** field, and use Windows Authentication (the default).</span></span> <span data-ttu-id="ed6c7-121">Klicken Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-121">Click **Connect**.</span></span>  
  
11. <span data-ttu-id="ed6c7-122">Sobald eine Verbindung hergestellt ist, werden im Dialogfeld **Zeugenserverinstanz** der Überwachungsport und der Datenbank-Spiegelungsendpunkt der Zeugenserverinstanz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-122">Once a connection is established, the listener port and database mirroring endpoint of the witness server instance are displayed on the **Witness Server Instance** dialog box.</span></span> <span data-ttu-id="ed6c7-123">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-123">Click **Next**.</span></span>  
  
12. <span data-ttu-id="ed6c7-124">Das Dialogfeld **Dienstkonten** enthält Felder für die Domänendienstkonten der Prinzipal-, Spiegel- und Zeugenserverinstanzen.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-124">The **Service Accounts** dialog box contains fields for the domain service accounts of the principal, mirror, and witness server instances.</span></span>  
  
    -   <span data-ttu-id="ed6c7-125">Lassen Sie diese Felder leer, wenn alle Serverinstanzen dasselbe Dienstkonto verwenden.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-125">If the server instances all use the same service account, leave the fields blank.</span></span>  
  
    -   <span data-ttu-id="ed6c7-126">Wenn die Zeugenserverinstanz ein anderes Dienstkonto als einer der Partner verwendet, füllen Sie die Felder **Prinzipal**, **Spiegel**und **Zeuge** mit dem Kontonamen aus:</span><span class="sxs-lookup"><span data-stu-id="ed6c7-126">If the witness server instance uses a different service account from either of the partners, fill in the **Principal**, **Mirror**, and **Witness** fields with the account name:</span></span>  
  
         <span data-ttu-id="ed6c7-127">*DOMÄNENNAME* **\\** *Benutzername*</span><span class="sxs-lookup"><span data-stu-id="ed6c7-127">*DOMAINNAME* **\\** *username*</span></span>  
  
         <span data-ttu-id="ed6c7-128">Der Domänenname muss in Großbuchstaben eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-128">The domain name must be in upper case.</span></span>  
  
     <span data-ttu-id="ed6c7-129">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-129">Click **Next**.</span></span>  
  
13. <span data-ttu-id="ed6c7-130">Überprüfen Sie optional auf der Seite **Assistenten abschließen** die Zeugenkonfiguration, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-130">On the **Complete the Wizard** summary screen, optionally, verify the witness configuration, and then click **Finish**.</span></span>  
  
14. <span data-ttu-id="ed6c7-131">Nach Abschluss des Assistenten wird wieder das Dialogfeld **Datenbankeigenschaften** angezeigt, in dem nun im Feld **Zeuge** die Servernetzwerkadresse des Zeugen angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-131">On finishing, the wizard returns you to the **Database Properties** dialog box where the server network address of the witness now appears in **Witness** field.</span></span> <span data-ttu-id="ed6c7-132">Außerdem ist die für einen Zeugen erforderliche Option **Hohe Sicherheit mit automatischem Failover (synchron)** automatisch ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-132">Also, **High-safety mode with automatic failover (synchronous)**, which is required with a witness, is automatically selected.</span></span>  
  
     <span data-ttu-id="ed6c7-133">Klicken Sie auf **OK**, um den Zeugen zu aktivieren und die Sitzung in den Modus für hohe Sicherheit zu versetzen.</span><span class="sxs-lookup"><span data-stu-id="ed6c7-133">To enable the witness and change the session to high-safety mode with automatic failover, Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed6c7-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed6c7-134">See Also</span></span>  
 <span data-ttu-id="ed6c7-135">[Datenbank-Spiegelungszeuge](database-mirroring-witness.md) </span><span class="sxs-lookup"><span data-stu-id="ed6c7-135">[Database Mirroring Witness](database-mirroring-witness.md) </span></span>  
 <span data-ttu-id="ed6c7-136">[Datenbankspiegelung &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ed6c7-136">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="ed6c7-137">[Datenbankeigenschaften &#40;Seite Wird gespiegelt&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span><span class="sxs-lookup"><span data-stu-id="ed6c7-137">[Database Properties &#40;Mirroring Page&#41;](../../relational-databases/databases/database-properties-mirroring-page.md) </span></span>  
 <span data-ttu-id="ed6c7-138">[Einrichten einer Datenbank-Spiegelungssitzung mithilfe der Windows-Authentifizierung (SQL Server Management Studio)](establish-database-mirroring-session-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="ed6c7-138">[Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md) </span></span>  
 [<span data-ttu-id="ed6c7-139">Datenbank-Spiegelungszeuge</span><span class="sxs-lookup"><span data-stu-id="ed6c7-139">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
