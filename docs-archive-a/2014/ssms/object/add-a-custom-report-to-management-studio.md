---
title: Hinzufügen eines benutzerdefinierten Berichts zu Management Studio | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], custom reports
ms.assetid: 3cf8d726-0a90-4f80-98d0-352a2a59be0f
author: stevestein
ms.author: sstein
ms.openlocfilehash: 07263edfb9b255257e0c79733c2c34b279b61cd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607519"
---
# <a name="add-a-custom-report-to-management-studio"></a><span data-ttu-id="b3a48-102">Hinzufügen eines benutzerdefinierten Berichts zu Management Studio</span><span class="sxs-lookup"><span data-stu-id="b3a48-102">Add a Custom Report to Management Studio</span></span>
  <span data-ttu-id="b3a48-103">In diesem Thema wird beschrieben, wie ein einfacher, als RDL-Datei gespeicherter [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] -Bericht erstellt und anschließend [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] diese RDL-Datei als benutzerdefinierter Bericht hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="b3a48-103">This topic describes how to create a simple [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] report that is saved as an .rdl file, and then add that rdl file to [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] as a custom report.</span></span> [!INCLUDE[ssRS](../../includes/ssrs.md)] <span data-ttu-id="b3a48-104">kann eine Vielzahl komplexer Berichte erstellen.</span><span class="sxs-lookup"><span data-stu-id="b3a48-104">can create a wide variety of sophisticated reports.</span></span> <span data-ttu-id="b3a48-105">Zum Erstellen eines Berichts mithilfe dieses Themas muss auf dem Computer [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] installiert sein.</span><span class="sxs-lookup"><span data-stu-id="b3a48-105">To create a report by using this topic, you must have [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] installed on the computer.</span></span> <span data-ttu-id="b3a48-106">Sie müssen [!INCLUDE[ssRS](../../includes/ssrs.md)] nicht auf einem Computer mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installieren, um einen benutzerdefinierten Bericht mithilfe von [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b3a48-106">You do not have to install [!INCLUDE[ssRS](../../includes/ssrs.md)] on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to run a custom report using [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span></span>  
  
  
### <a name="to-create-a-simple-report-saved-as-an-rdl-file"></a><span data-ttu-id="b3a48-107">So erstellen Sie einen als RDL-Datei gespeicherten, einfachen Bericht</span><span class="sxs-lookup"><span data-stu-id="b3a48-107">To create a simple report saved as an .rdl file</span></span>  
  
1.  <span data-ttu-id="b3a48-108">Klicken Sie auf **Start**, zeigen sie auf **Alle Programme**und dann auf **Microsoft SQL Server**, und klicken Sie auf **SQL Server Data Tools**.</span><span class="sxs-lookup"><span data-stu-id="b3a48-108">Click **Start**, point to **Programs**, point to **Microsoft SQL Server**, and then click **SQL Server Data Tools**.</span></span>  
  
2.  <span data-ttu-id="b3a48-109">Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="b3a48-109">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="b3a48-110">Klicken Sie in der Liste **Projekttypen** auf **Business Intelligence-Projekte**.</span><span class="sxs-lookup"><span data-stu-id="b3a48-110">In the **Project Types** list, click **Business Intelligence Projects**.</span></span>  
  
4.  <span data-ttu-id="b3a48-111">Klicken Sie in der Liste **Vorlagen** auf **Berichtsserverprojekt-Assistent**.</span><span class="sxs-lookup"><span data-stu-id="b3a48-111">In the **Templates** list, click **Report Server Project Wizard**.</span></span>  
  
5.  <span data-ttu-id="b3a48-112">Geben Sie unter **Name** **ConnectionsReport**ein, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3a48-112">In **Name**, type **ConnectionsReport**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="b3a48-113">Klicken Sie auf der Einführungsseite des **Berichts-Assistenten** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b3a48-113">On the **Report Wizard** introduction page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="b3a48-114">Geben Sie auf der Seite **Datenquelle auswählen** im Feld „Name“ einen Namen für diese Verbindung mit [!INCLUDE[ssDE](../../includes/ssde-md.md)]ein, und klicken Sie anschließend auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="b3a48-114">On the **Select the Data Source** page, in the Name box type a name for this connection to your [!INCLUDE[ssDE](../../includes/ssde-md.md)], and then click **Edit**.</span></span>  
  
8.  <span data-ttu-id="b3a48-115">Geben Sie im Dialogfeld **Verbindungseigenschaften** im Feld **Servername** den Namen Ihrer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]ein.</span><span class="sxs-lookup"><span data-stu-id="b3a48-115">In the **Connection Properties** dialog box, in the **Server name** box, type the name of your instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
9. <span data-ttu-id="b3a48-116">Geben Sie im Feld **Datenbanknamen eingeben oder auswählen** den Namen einer beliebigen Datenbank auf Ihrem Computer mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]ein (z. B. [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]), und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b3a48-116">In the **Select or enter a database name** box, type the name of any database on your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], such as [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], and then click **OK**.</span></span>  
  
10. <span data-ttu-id="b3a48-117">Klicken Sie auf der Seite **Datenquelle auswählen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b3a48-117">On the **Select the Data Source** page, click **Next**.</span></span>  
  
11. <span data-ttu-id="b3a48-118">Geben Sie auf der Seite **Abfrage entwerfen** im Feld **Abfragezeichenfolge** die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung ein, mit der die aktuellen Verbindungen mit [!INCLUDE[ssDE](../../includes/ssde-md.md)]aufgelistet werden, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="b3a48-118">On the **Design the Query** page, in the **Query string** box, type the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement that lists the current connections to your [!INCLUDE[ssDE](../../includes/ssde-md.md)], and then click **Next**.</span></span> <span data-ttu-id="b3a48-119">Im Feld "Abfragezeichenfolge" des Berichts-Assistenten können keine Berichtsparameter eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b3a48-119">The Report Wizard Query string box will not accept report parameters.</span></span> <span data-ttu-id="b3a48-120">Komplexere benutzerdefinierte Berichte müssen manuell erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b3a48-120">More complex custom reports must be created manually.</span></span>  
  
     `SELECT session_id, net_transport FROM sys.dm_exec_connections;`  
  
12. <span data-ttu-id="b3a48-121">Wählen Sie auf der Seite **Berichtstyp auswählen** die Option **Tabellarisch**aus, und klicken Sie dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="b3a48-121">On the **Select the Report Type** page, select **Tabular**, and then click **Finish**.</span></span>  
  
13. <span data-ttu-id="b3a48-122">Geben Sie auf der Seite **Assistenten abschließen** im Feld **Berichtsname** die Zeichenfolge **ConnectionsReport**ein, und klicken Sie anschließend zum Erstellen und Speichern des Berichts auf **Fertig stellen** .</span><span class="sxs-lookup"><span data-stu-id="b3a48-122">On the **Completing the Wizard** page, in the **Report name** box, type **ConnectionsReport**, and then click **Finish** to create and save the report.</span></span>  
  
14. <span data-ttu-id="b3a48-123">Schließen Sie [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b3a48-123">Close [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
15. <span data-ttu-id="b3a48-124">Kopieren Sie die Datei **ConnectionsReport.rdl** in einen Ordner, den Sie auf Ihrem Datenbankserver für benutzerdefinierte Berichte erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="b3a48-124">Copy **ConnectionsReport.rdl** to a folder that you created on the database server for custom reports.</span></span>  
  
### <a name="to-add-a-report-to-management-studio"></a><span data-ttu-id="b3a48-125">So fügen Sie Management Studio einen Bericht hinzu</span><span class="sxs-lookup"><span data-stu-id="b3a48-125">To add a report to Management Studio</span></span>  
  
-   <span data-ttu-id="b3a48-126">Klicken Sie in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]mit der rechten Maustaste auf einen Knoten im Objekt-Explorer, zeigen Sie auf **Berichte**, und klicken Sie auf **Benutzerdefinierte Berichte**.</span><span class="sxs-lookup"><span data-stu-id="b3a48-126">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], right-click a node in Object Explorer, point to **Reports**, click **Custom Reports**.</span></span> <span data-ttu-id="b3a48-127">Suchen Sie im Dialogfeld **Datei öffnen** den Ordner mit den benutzerdefinierten Berichten, wählen Sie die Datei **ConnectionsReport.rdl** aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="b3a48-127">In the **Open File** dialog box, locate the custom reports folder and select the **ConnectionsReport.rdl** file, and then click **Open**.</span></span>  
  
     <span data-ttu-id="b3a48-128">Wenn ein neuer benutzerdefinierter Bericht erstmalig von einem Knoten des Objekt-Explorers aus geöffnet wird, wird der Liste zuletzt verwendeter Objekte im Kontextmenü dieses Knotens unter **Benutzerdefinierte Berichte** dieser benutzerdefinierte Bericht hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b3a48-128">When a new custom report is first opened from an Object Explorer node, the custom report is added to the most recently used list under **Custom Reports** on the shortcut menu of that node.</span></span> <span data-ttu-id="b3a48-129">Wenn ein Standardbericht erstmalig geöffnet wird, wird er auch in der Liste zuletzt verwendeter Objekte unter **Benutzerdefinierte Berichte**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3a48-129">When a standard report is opened for the first time, it will also appear on the most recently used list under **Custom Reports**.</span></span> <span data-ttu-id="b3a48-130">Wenn eine benutzerdefinierte Berichtsdatei gelöscht wird, wird beim nächsten Auswählen des Elements eine Aufforderung angezeigt, das Element aus der Liste zuletzt verwendeter Objekte zu löschen.</span><span class="sxs-lookup"><span data-stu-id="b3a48-130">If a custom report file is deleted, the next time that the item is selected, a prompt will appear to delete the item from the most recently used list.</span></span>  
  
    1.  <span data-ttu-id="b3a48-131">Klicken Sie im Menü **Extras** auf **Optionen** , erweitern Sie den Ordner **Umgebung** , und klicken Sie dann auf **Allgemein**, um die Anzahl der in der Liste zuletzt verwendeter Objekte angezeigten Dateien zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b3a48-131">To change the number of files that are displayed on the recently used list, on the **Tools** menu, click **Options,** expand the **Environment** folder, and then click **General**.</span></span>  
  
    2.  <span data-ttu-id="b3a48-132">Passen Sie die Anzahl für **Dateien in „Zuletzt geöffnet“-Liste angezeigt**an.</span><span class="sxs-lookup"><span data-stu-id="b3a48-132">Adjust the number for **Display files in recently used list**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3a48-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b3a48-133">See Also</span></span>  
 <span data-ttu-id="b3a48-134">[Benutzerdefinierte Berichte in Management Studio](custom-reports-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b3a48-134">[Custom Reports in Management Studio](custom-reports-in-management-studio.md) </span></span>  
 <span data-ttu-id="b3a48-135">[Verwenden benutzerdefinierter Berichte mit Eigenschaften des Objekt-Explorer Knotens](use-custom-reports-with-object-explorer-node-properties.md) </span><span class="sxs-lookup"><span data-stu-id="b3a48-135">[Use Custom Reports with Object Explorer Node Properties](use-custom-reports-with-object-explorer-node-properties.md) </span></span>  
 <span data-ttu-id="b3a48-136">[Nicht unterdrücken von Warnungen für benutzerdefinierten Bericht ausführen](unsuppress-run-custom-report-warnings.md) </span><span class="sxs-lookup"><span data-stu-id="b3a48-136">[Unsuppress Run Custom Report Warnings](unsuppress-run-custom-report-warnings.md) </span></span>  
 [<span data-ttu-id="b3a48-137">Reporting Services &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b3a48-137">Reporting Services &#40;SSRS&#41;</span></span>](../../reporting-services/create-deploy-and-manage-mobile-and-paginated-reports.md)  
  
  
