---
title: Erstellen einer BI-Semantik Modell Verbindung mit einer Power Pivot-Arbeitsmappe | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b2e3f97f-18a8-42b6-9030-b4f818afc3b9
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7ea4ddcc38328acc6ff8cfb5387b13056b689a24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620578"
---
# <a name="create-a-bi-semantic-model-connection-to-a-powerpivot-workbook"></a><span data-ttu-id="bbafa-102">Herstellen einer BI-Semantikmodellverbindung mit einer PowerPivot-Arbeitsmappe</span><span class="sxs-lookup"><span data-stu-id="bbafa-102">Create a BI Semantic Model Connection to a PowerPivot Workbook</span></span>
  <span data-ttu-id="bbafa-103">Verwenden Sie die Informationen in diesem Thema, um eine BI-Semantikmodellverbindung einzurichten, die zu einer PowerPivot-Arbeitsmappe in der gleichen Farm umleitet.</span><span class="sxs-lookup"><span data-stu-id="bbafa-103">Use the information in this topic to set up a BI semantic model connection that redirects to a PowerPivot workbook in the same farm.</span></span>  
  
 <span data-ttu-id="bbafa-104">Nachdem Sie eine BI-Semantikmodellverbindung erstellt und SharePoint-Berechtigungen konfiguriert haben, können Sie sie als Datenquelle für Excel- oder [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] -Berichte verwenden.</span><span class="sxs-lookup"><span data-stu-id="bbafa-104">After you create a BI semantic model connection and configure SharePoint permissions, you can use it as a data source for Excel or [!INCLUDE[ssCrescent](../../includes/sscrescent-md.md)] reports.</span></span>  
  
 <span data-ttu-id="bbafa-105">Das Thema enthält folgende Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="bbafa-105">This topic includes the following sections.</span></span> <span data-ttu-id="bbafa-106">Führen Sie jede Aufgabe in der angegebenen Reihenfolge aus.</span><span class="sxs-lookup"><span data-stu-id="bbafa-106">Perform each task in the order given.</span></span>  
  
 [<span data-ttu-id="bbafa-107">Überprüfen der Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="bbafa-107">Review Prerequisites</span></span>](#bkmk_prereq)  
  
 [<span data-ttu-id="bbafa-108">Erstellen einer Verbindung</span><span class="sxs-lookup"><span data-stu-id="bbafa-108">Create a Connection</span></span>](#bkmk_create)  
  
 [<span data-ttu-id="bbafa-109">Konfigurieren von SharePoint-Berechtigungen für die BI-Semantik Modell Verbindung</span><span class="sxs-lookup"><span data-stu-id="bbafa-109">Configure SharePoint Permissions on the BI Semantic Model Connection</span></span>](#bkmk_permissions)  
  
 [<span data-ttu-id="bbafa-110">Konfigurieren von SharePoint-Berechtigungen für die Arbeitsmappe</span><span class="sxs-lookup"><span data-stu-id="bbafa-110">Configure SharePoint Permissions on the Workbook</span></span>](#bkmk_userdb)  
  
 [<span data-ttu-id="bbafa-111">Next Steps</span><span class="sxs-lookup"><span data-stu-id="bbafa-111">Next Steps</span></span>](#bkmk_next)  
  
##  <a name="review-prerequisites"></a><a name="bkmk_prereq"></a><span data-ttu-id="bbafa-112">Voraussetzungen prüfen</span><span class="sxs-lookup"><span data-stu-id="bbafa-112">Review Prerequisites</span></span>  
 <span data-ttu-id="bbafa-113">Sie benötigen Teilnahmeberechtigungen oder weiterreichende Berechtigungen, um eine BI Semantikmodell-Verbindungsdatei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bbafa-113">You must have Contribute permissions or above to create a BI semantic model connection file.</span></span>  
  
 <span data-ttu-id="bbafa-114">Sie benötigen eine Bibliothek, die den Inhaltstyp der BI Semantikmodellverbindung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bbafa-114">You must have a library that supports the BI semantic model connection content type.</span></span> <span data-ttu-id="bbafa-115">Weitere Informationen finden [Sie unter Hinzufügen eines BI-Semantik Modell-Verbindungs-Inhaltstyps zu einer Bibliothek &#40;PowerPivot für SharePoint&#41;](add-bi-semantic-model-connection-content-type-to-library.md).</span><span class="sxs-lookup"><span data-stu-id="bbafa-115">For more information, see [Add a BI Semantic Model Connection Content Type to a Library &#40;PowerPivot for SharePoint&#41;](add-bi-semantic-model-connection-content-type-to-library.md).</span></span>  
  
 <span data-ttu-id="bbafa-116">Sie müssen die URL der Power Pivot-Arbeitsmappe kennen, für die Sie eine BI-Semantik Modell Verbindung einrichten (z http://adventure-works/shared . b. Dokumente/myworkbook.xlsx).</span><span class="sxs-lookup"><span data-stu-id="bbafa-116">You must know the URL of the PowerPivot workbook for which you are setting up a BI semantic model connection (for example, http://adventure-works/shared documents/myworkbook.xlsx).</span></span> <span data-ttu-id="bbafa-117">Die Arbeitsmappe muss in der gleichen Farm sein.</span><span class="sxs-lookup"><span data-stu-id="bbafa-117">The workbook must be in the same farm.</span></span>  
  
 <span data-ttu-id="bbafa-118">Alle Computer und Benutzer, die Teil der Verbindungssequenz sind, müssen in der gleichen Domäne bzw. vertrauenswürdigen Domäne (bidirektionale Vertrauensstellung) enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="bbafa-118">All computers and users that participate in the connection sequence must be in the same domain or trusted domain (two-way trust).</span></span>  
  
##  <a name="create-a-connection"></a><a name="bkmk_create"></a><span data-ttu-id="bbafa-119">Erstellen einer Verbindung</span><span class="sxs-lookup"><span data-stu-id="bbafa-119">Create a Connection</span></span>  
  
1.  <span data-ttu-id="bbafa-120">Klicken Sie in der Bibliothek, die die BI-Semantikmodellverbindung enthalten soll, auf **Dokumente** im SharePoint-Menüband.</span><span class="sxs-lookup"><span data-stu-id="bbafa-120">In the library that will contain the BI semantic model connection, click **Documents** on the SharePoint ribbon.</span></span> <span data-ttu-id="bbafa-121">Klicken Sie in „Neues Dokument“ auf den Pfeil nach unten, und wählen Sie **BISM-Verbindungsdatei** aus, um die Seite „Neue BI-Semantikmodellverbindung“ zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bbafa-121">Click the down arrow on New Document, and select **BISM Connection File** to open the New BI Semantic Model Connection page.</span></span>  
  
     <span data-ttu-id="bbafa-122">![Untermenü "Neues Dokument" in einer SharePoint-Bibliothek](../media/ssas-bismconnection-new.gif "Untermenü "Neues Dokument" in einer SharePoint-Bibliothek")</span><span class="sxs-lookup"><span data-stu-id="bbafa-122">![New Document submenu in a SharePoint library](../media/ssas-bismconnection-new.gif "New Document submenu in a SharePoint library")</span></span>  
  
2.  <span data-ttu-id="bbafa-123">Legen Sie die **Server** -Eigenschaft auf die SharePoint-URL der Power Pivot-Arbeitsmappe (z. b. \*\* http://mysharepoint/shared Dokumente/myWorkbook.xlsx\*\*fest.</span><span class="sxs-lookup"><span data-stu-id="bbafa-123">Set the **Server** property to the SharePoint URL of the PowerPivot workbook (for example, **http://mysharepoint/shared documents/myWorkbook.xlsx**.</span></span> <span data-ttu-id="bbafa-124">In einer Bereitstellung von PowerPivot für SharePoint können Daten auf jeden Server in der Farm geladen werden.</span><span class="sxs-lookup"><span data-stu-id="bbafa-124">In a PowerPivot for SharePoint deployment, data can be loaded on any server in the farm.</span></span> <span data-ttu-id="bbafa-125">Aus diesem Grund geben Datenquellenverbindungen mit PowerPivot-Daten nur den Pfad zur Arbeitsmappe an.</span><span class="sxs-lookup"><span data-stu-id="bbafa-125">For this reason, data source connections to PowerPivot data specify just the path to the workbook.</span></span> <span data-ttu-id="bbafa-126">Der PowerPivot-Systemdienst bestimmt, welcher Server die Daten lädt.</span><span class="sxs-lookup"><span data-stu-id="bbafa-126">The PowerPivot System Service determines which server loads the data.</span></span>  
  
     <span data-ttu-id="bbafa-127">Verwenden Sie die **Database** -Eigenschaft nicht. Er wird nicht verwendet, wenn der Speicherort einer Power Pivot-Arbeitsmappe angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bbafa-127">Do not use the **Database** property; it is not used when specifying the location of a PowerPivot workbook.</span></span>  
  
     <span data-ttu-id="bbafa-128">Die Seite sollte ähnlich der folgenden Abbildung aussehen.</span><span class="sxs-lookup"><span data-stu-id="bbafa-128">Your page should look similar to the following illustration.</span></span>  
  
     <span data-ttu-id="bbafa-129">![BISM-Verbindungsseite mit URL der Arbeitsmappe](../media/ssas-bismconnection-ppvtds.gif "BISM-Verbindungsseite mit URL der Arbeitsmappe")</span><span class="sxs-lookup"><span data-stu-id="bbafa-129">![BISM connection page showing URL to workbook](../media/ssas-bismconnection-ppvtds.gif "BISM connection page showing URL to workbook")</span></span>  
  
     <span data-ttu-id="bbafa-130">Wenn Sie über SharePoint-Berechtigungen an der Arbeitsmappe verfügen, wird optional ein zusätzlicher Überprüfungsschritt ausgeführt, der sicherstellt, dass der Speicherort gültig ist.</span><span class="sxs-lookup"><span data-stu-id="bbafa-130">Optionally, if you have SharePoint permissions to the workbook, an extra validation step is performed, ensuring that the location is valid.</span></span> <span data-ttu-id="bbafa-131">Wenn Sie nicht über die Berechtigung verfügen, auf die Daten zuzugreifen, wird Ihnen die Option gegeben, die BI-Semantikmodellverbindung ohne die Überprüfungsantwort zu speichern.</span><span class="sxs-lookup"><span data-stu-id="bbafa-131">If you do not have permission to access the data, you are given the option of saving the BI semantic model connection without the validation response.</span></span>  
  
##  <a name="configure-sharepoint-permissions-on-the-bi-semantic-model-connection"></a><a name="bkmk_permissions"></a> <span data-ttu-id="bbafa-132">Konfigurieren von SharePoint-Berechtigungen für die BI-Semantikmodellverbindung</span><span class="sxs-lookup"><span data-stu-id="bbafa-132">Configure SharePoint Permissions on the BI Semantic Model Connection</span></span>  
 <span data-ttu-id="bbafa-133">Damit eine BI-Semantikmodellverbindung als Datenquelle für eine Excel-Arbeitsmappe oder einen Reporting Services-Bericht verwendet werden kann, muss das BI-Semantikmodell-Verbindungselement über **Leseberechtigungen** in einer SharePoint-Bibliothek verfügen.</span><span class="sxs-lookup"><span data-stu-id="bbafa-133">Ability to use a BI semantic model connection as a data source for an Excel workbook or Reporting Services report requires **Read** permissions on the BI semantic model connection item in a SharePoint library.</span></span> <span data-ttu-id="bbafa-134">Die Berechtigungsebene „Lesen“ schließt die Berechtigung **Elemente öffnen** ein, die das Herunterladen von BI-Semantikmodell-Verbindungsinformationen in eine Excel-Desktopanwendung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="bbafa-134">The Read permission level includes the **Open Items** permission that enables downloading BI semantic model connection information to an Excel desktop application.</span></span>  
  
 <span data-ttu-id="bbafa-135">Es gibt mehrere Möglichkeiten, Berechtigungen in SharePoint zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="bbafa-135">There are several ways to grant permissions in SharePoint.</span></span> <span data-ttu-id="bbafa-136">Die folgenden Anweisungen erläutern, wie Sie eine neue Gruppe mit dem Namen **BISM-Benutzer** erstellen, die die Berechtigungsstufe **Lesen** haben.</span><span class="sxs-lookup"><span data-stu-id="bbafa-136">The following instructions explain how to create a new group called **BISM Users** that have the **Read** permission level.</span></span>  
  
 <span data-ttu-id="bbafa-137">Sie müssen Websitebesitzer sein, um Berechtigungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bbafa-137">You must be a site owner to change permissions.</span></span>  
  
1.  <span data-ttu-id="bbafa-138">Klicken Sie in „Websiteaktionen“ auf **Websiteberechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="bbafa-138">In Site Actions, click **Site Permissions**.</span></span>  
  
2.  <span data-ttu-id="bbafa-139">Klicken Sie auf **Gruppe erstellen** , und nennen Sie die neue Gruppe **BISM-Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="bbafa-139">Click **Create Group** and name the new group **BISM Users**.</span></span>  
  
3.  <span data-ttu-id="bbafa-140">Wählen Sie die Berechtigungsstufe **Lesen** aus, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="bbafa-140">Choose the **Read** permission level and click **Create**.</span></span>  
  
4.  <span data-ttu-id="bbafa-141">Wählen Sie **BISM-Benutzer** in „Personen und Gruppen“ aus.</span><span class="sxs-lookup"><span data-stu-id="bbafa-141">Select **BISM Users** in People and Groups.</span></span>  
  
5.  <span data-ttu-id="bbafa-142">Zeigen Sie auf „Neu“, klicken Sie auf **Benutzer hinzufügen**, und fügen Sie dann Benutzer- oder Gruppenkonten hinzu.</span><span class="sxs-lookup"><span data-stu-id="bbafa-142">Point to New, click **Add Users**, and then add user or group accounts.</span></span>  
  
     <span data-ttu-id="bbafa-143">Diese Benutzer und die Gruppen haben jetzt Leseberechtigungen überall in der Website, einschließlich aller Bibliotheken und Listen, die Berechtigungen von der Websiteebene erben.</span><span class="sxs-lookup"><span data-stu-id="bbafa-143">These users and groups will now have Read permissions throughout the site, including all libraries and lists that inherit permissions from the site level.</span></span> <span data-ttu-id="bbafa-144">Wenn diese Berechtigungen zu hoch sind, können Sie diese Gruppe aus bestimmten Bibliotheken, Listen oder Elementen selektiv entfernen.</span><span class="sxs-lookup"><span data-stu-id="bbafa-144">If these permissions are too high, you can selectively remove this group from specific libraries, lists, or items.</span></span>  
  
 <span data-ttu-id="bbafa-145">Um Berechtigungen auf Elementebene selektiv zu entfernen, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="bbafa-145">To selectively remove permissions at the item level, do the following:</span></span>  
  
1.  <span data-ttu-id="bbafa-146">Wählen Sie in einer Bibliothek ein Dokument aus.</span><span class="sxs-lookup"><span data-stu-id="bbafa-146">In a library, select a document.</span></span> <span data-ttu-id="bbafa-147">Klicken Sie auf den rechten Pfeil nach unten, und klicken Sie auf **Berechtigungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="bbafa-147">Click the right down arrow and then click **Manage Permissions**.</span></span>  
  
2.  <span data-ttu-id="bbafa-148">Standardmäßig erbt ein Element Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="bbafa-148">By default, an item inherits permissions.</span></span> <span data-ttu-id="bbafa-149">Um die Berechtigungen von einzelnen Dokumenten in dieser Bibliothek zu ändern, klicken Sie auf **Berechtigungsvererbung beenden**.</span><span class="sxs-lookup"><span data-stu-id="bbafa-149">To change the permissions of individual documents in this library, click **Stop Inheriting Permissions**.</span></span>  
  
3.  <span data-ttu-id="bbafa-150">Aktivieren Sie das Kontrollkästchen neben **BISM-Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="bbafa-150">Select the checkbox next to **BISM Users**.</span></span>  
  
4.  <span data-ttu-id="bbafa-151">Klicken Sie auf **Benutzerberechtigungen entfernen**.</span><span class="sxs-lookup"><span data-stu-id="bbafa-151">Click **Remove User Permissions**.</span></span>  
  
##  <a name="configure-sharepoint-permissions-on-the-workbook"></a><a name="bkmk_userdb"></a> <span data-ttu-id="bbafa-152">Konfigurieren von SharePoint-Berechtigungen für die Arbeitsmappe</span><span class="sxs-lookup"><span data-stu-id="bbafa-152">Configure SharePoint Permissions on the Workbook</span></span>  
 <span data-ttu-id="bbafa-153">Wenn Sie in einer Excel-Arbeitsmappe eine PowerPivot-Datenbank verwenden, bestimmen die SharePoint-Berechtigungen für die Excel-Arbeitsmappe den Datenzugriff auf die BI-Semantikmodellverbindung.</span><span class="sxs-lookup"><span data-stu-id="bbafa-153">If you are using a PowerPivot database inside an Excel workbook, the SharePoint permissions on the Excel workbook determine data access via the BI semantic model connection.</span></span> <span data-ttu-id="bbafa-154">Alle Benutzer, die auf die Arbeitsmappe zugreifen, müssen Leseberechtigungen für die Arbeitsmappe haben, um sie als externe Datenquelle zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bbafa-154">All users who access the workbook must have Read permissions on the workbook in order to use it as an external data source.</span></span>  
  
 <span data-ttu-id="bbafa-155">Wenn Sie eine Gruppe **BISM-Benutzer** mithilfe der Anweisungen im vorherigen Abschnitt erstellt haben, haben Benutzer- und Gruppenkonten, die Mitglieder von **BISM-Benutzer** sind, ausreichende Berechtigungen für die Arbeitsmappe und für die BI-Semantikmodell-Verbindungsdatei, wenn die Arbeitsmappe geerbte Berechtigungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="bbafa-155">If you created a **BISM Users** group using the instructions in the previous section, user and group accounts that are members of **BISM Users** will have sufficient permission on the workbook as well as the BI semantic model connection file, assuming the workbook uses inherited permissions.</span></span>  
  
##  <a name="next-steps"></a><a name="bkmk_next"></a> <span data-ttu-id="bbafa-156">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="bbafa-156">Next Steps</span></span>  
 <span data-ttu-id="bbafa-157">Nachdem Sie eine BI-Semantikmodellverbindung erstellt und gesichert haben, können Sie sie als Datenquelle angeben.</span><span class="sxs-lookup"><span data-stu-id="bbafa-157">After you create and secure a BI semantic model connection, you can specify it as a data source.</span></span> <span data-ttu-id="bbafa-158">Weitere Informationen finden Sie unter [Verwenden einer BI-Semantikmodellverbindung in Excel oder Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="bbafa-158">For more information, see [Use a BI Semantic Model Connection in Excel or Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbafa-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bbafa-159">See Also</span></span>  
 <span data-ttu-id="bbafa-160">[Power Pivot BI-Semantik Modell Verbindung &#40;. bism-&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span><span class="sxs-lookup"><span data-stu-id="bbafa-160">[PowerPivot BI Semantic Model Connection &#40;.bism&#41;](power-pivot-bi-semantic-model-connection-bism.md) </span></span>  
 <span data-ttu-id="bbafa-161">[Verwenden einer BI-Semantik Modell Verbindung in Excel oder Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="bbafa-161">[Use a BI Semantic Model Connection in Excel or Reporting Services](use-a-bi-semantic-model-connection-in-excel-or-reporting-services.md) </span></span>  
 [<span data-ttu-id="bbafa-162">Erstellen einer BI-Semantikmodellverbindung mit einer tabellarischen Modelldatenbank</span><span class="sxs-lookup"><span data-stu-id="bbafa-162">Create a BI Semantic Model Connection to a Tabular Model Database</span></span>](create-a-bi-semantic-model-connection-to-a-tabular-model-database.md)  
  
  
