---
title: Herstellen einer Verbindung mit Quelldaten (Data Mining-Client für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- connections
ms.assetid: 548672ce-e403-4aca-b67a-c2c797f053dd
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4b4759d94043fdccacdf5b285de50697a18965e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610199"
---
# <a name="connect-to-source-data-data-mining-client-for-excel"></a><span data-ttu-id="4f25b-102">Herstellen von Verbindungen mit Quelldaten (Data Mining-Client für Excel)</span><span class="sxs-lookup"><span data-stu-id="4f25b-102">Connect to Source Data (Data Mining Client for Excel)</span></span>
  <span data-ttu-id="4f25b-103">In diesem Thema wird beschrieben, wie Sie Verbindungen, die zum Speichern von Data Mining-Modellen und für den Zugriff auf die in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] gespeicherten externen Daten verwendet werden, erstellen und verwenden.</span><span class="sxs-lookup"><span data-stu-id="4f25b-103">This topic describes how to create and use connections used for storing data mining models, and for accessing external data stored in [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="4f25b-104">**Data Mining-Verbindungen.**</span><span class="sxs-lookup"><span data-stu-id="4f25b-104">**Data mining connections.**</span></span> <span data-ttu-id="4f25b-105">Die beim Starten des Add-Ins erstellte Verbindung wird für den Zugriff auf Algorithmen, das Analysieren von Daten und das Speichern von Miningstrukturen und -modellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4f25b-105">The initial connection that you create when you start the add-ins is used to access algorithms, analyze data, and store mining structure and models.</span></span>  
  
 <span data-ttu-id="4f25b-106">Eine Verbindung mit einer Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] ist erforderlich, um die Modellierungs- und Visualisierungstools in den Add-Ins zu verwenden. Der Grund dafür ist, dass die Add-Ins von den Algorithmen und Datenstrukturen abhängen, die von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4f25b-106">A connection to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] is required to use the modeling and visualization tools in the add-ins, because the add-ins depend on algorithms and data structures that are provided by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="4f25b-107">**Verbindungen mit externen Datenquellen.**</span><span class="sxs-lookup"><span data-stu-id="4f25b-107">**Connections to external data sources.**</span></span> <span data-ttu-id="4f25b-108">Sie können Verbindungen mit externen Daten auch herstellen, während Sie Modelle erstellen oder Ergebnisse speichern.</span><span class="sxs-lookup"><span data-stu-id="4f25b-108">You can also create connections to external data as you are building models or saving the results.</span></span> <span data-ttu-id="4f25b-109">So können Sie beispielsweise ein Data Mining-Modell auf einem Server erstellen und anschließend mit diesem Data Mining-Modell eine Vorhersage auf der Grundlage von Daten ausführen, die in einer anderen Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], in einer Excel-Datentabelle oder einer externen Datenquelle wie [!INCLUDE[msCoName](../includes/msconame-md.md)] Access gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="4f25b-109">For example, you can create a data mining model on one server, and then perform a prediction query against the data mining model by using data stored in another instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], in an Excel data table, or in an external data source such as [!INCLUDE[msCoName](../includes/msconame-md.md)] Access.</span></span> <span data-ttu-id="4f25b-110">Bei jedem Zugriff auf eine neue Datenquelle werden Sie in einem Dialogfeld aufgefordert, eine Verbindung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4f25b-110">Each time that you access a new data source, you will be prompted to create a connection by using a dialog box.</span></span>  
  
##  <a name="prerequisites"></a><a name="bkmk_prereq2"></a> <span data-ttu-id="4f25b-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="4f25b-111">Prerequisites</span></span>  
 <span data-ttu-id="4f25b-112">Bei dieser Version des Add-Ins muss die [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Instanz die Version SQL Server 2012 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4f25b-112">This version of the add-ins requires that your instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] be SQL Server 2012.</span></span> <span data-ttu-id="4f25b-113">Eine separate Version der Add-Ins ist verfügbar, wenn Sie eine Verbindung mit einer früheren Version von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="4f25b-113">A separate version of the add-ins is available if you want to connect to an earlier version of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="4f25b-114">Es gibt Add-In-Versionen, die SQL Server 2005, SQL Server 2008 und SQL Server 2008 R2 unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4f25b-114">There are versions of the add-ins that support SQL Server 2005, SQL Server 2008, and SQL Server 2008 R2.</span></span>  
  
 <span data-ttu-id="4f25b-115">Um eine Verbindung mit einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Datenbank herzustellen, benötigen Sie Zugriffsrechte für den Datenbankserver.</span><span class="sxs-lookup"><span data-stu-id="4f25b-115">To connect to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, you must have permissions to access the database server.</span></span> <span data-ttu-id="4f25b-116">Außerdem müssen Data Mining-Sitzungen aktiviert sein, und Sie benötigen Lese- oder Lese-/Schreibberechtigungen für die Datenbankobjekte, die auf dem Server gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="4f25b-116">Moreover, data mining sessions must be enabled, and you must have read or read/write permissions on database objects stored on the server.</span></span>  
  
##  <a name="creating-data-mining-server-connections"></a><a name="bkmk_connect"></a><span data-ttu-id="4f25b-117">Erstellen von Data Mining-Server Verbindungen</span><span class="sxs-lookup"><span data-stu-id="4f25b-117">Creating Data Mining Server Connections</span></span>  
 <span data-ttu-id="4f25b-118">Die Gruppe **Verbindungen** im Data Mining-Client für Excel und die Tabellenanalyse Tools für Excel bieten Tools zum Verwalten von Verbindungen mit einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f25b-118">The **Connections** group in the Data Mining Client for Excel and the Table Analysis Tools for Excel provides tools for managing connections to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="4f25b-119">Sie können die Verbindung beim Installieren des Add-Ins erstellen oder später hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4f25b-119">You can create the connection when you install the add-in, or you can add a connection later.</span></span>  
  
-   <span data-ttu-id="4f25b-120">Sie können mehrere Verbindungen erstellen und Verbindungen jederzeit ändern, es sei denn, Sie erstellen gerade ein Modell oder führen eine Abfrage für ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="4f25b-120">You can create multiple connections, and change connections at any time, unless you are in the process of creating or querying a model.</span></span>  
  
     <span data-ttu-id="4f25b-121">Ändern oder schließen Sie keine Verbindung, wenn ein Data Mining-Modell gerade verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="4f25b-121">Do not change or close a connection when a data mining model is being processed.</span></span> <span data-ttu-id="4f25b-122">Im Data Mining-Modell können Daten verloren gehen, oder das Modell wird möglicherweise unbrauchbar.</span><span class="sxs-lookup"><span data-stu-id="4f25b-122">The data mining model might lose data, or the model might become unusable.</span></span>  
  
-   <span data-ttu-id="4f25b-123">Es kann jeweils nur eine Verbindung aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="4f25b-123">Only one connection can be active at a particular time.</span></span>  
  
### <a name="connections-in-the-excel-add-ins"></a><span data-ttu-id="4f25b-124">Verbindungen in den Excel-Add-Ins</span><span class="sxs-lookup"><span data-stu-id="4f25b-124">Connections in the Excel Add-ins</span></span>  
 <span data-ttu-id="4f25b-125">Die Gruppe **Verbindungen** im Data Mining-Client für Excel und die Tabellenanalyse Tools für Excel dient zum Verwalten von Verbindungen mit einer Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f25b-125">The **Connections** group in the Data Mining Client for Excel and the Table Analysis Tools for Excel is where you manage connections to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span>  
  
##### <a name="create-a-new-server-connection-in-the-excel-add-ins"></a><span data-ttu-id="4f25b-126">Erstellen einer neuen Serververbindung in den Excel-Add-Ins</span><span class="sxs-lookup"><span data-stu-id="4f25b-126">Create a new server connection in the Excel add-ins</span></span>  
  
1.  <span data-ttu-id="4f25b-127">Klicken Sie im Menüband **analysieren** oder **Data Mining** auf die Schaltfläche **Verbindung** .</span><span class="sxs-lookup"><span data-stu-id="4f25b-127">Click the **Connection** button on the **Analyze** or **Data Mining** ribbon.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="4f25b-128">Der Text auf der Schaltfläche gibt an, ob eine Verbindung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="4f25b-128">The text of the button indicates if a connection exists.</span></span> <span data-ttu-id="4f25b-129">Wenn im Arbeitsblatt keine Verbindung hergestellt wurde, enthält die Schaltfläche den Text " \<No connection> ." Wenn zuvor eine Verbindung in der Arbeitsmappe hergestellt wurde, wird der Name dieser Verbindung in der Schaltfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4f25b-129">When no connection has been made in the worksheet, the button contains the text "\<No connection>." If a connection was previously made in the workbook, the name of that connection appears in the button.</span></span>  
  
2.  <span data-ttu-id="4f25b-130">Klicken Sie im Dialogfeld **Analysis Services Verbindungen** auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="4f25b-130">In the **Analysis Services Connections** dialog box, click **New**.</span></span>  
  
3.  <span data-ttu-id="4f25b-131">Geben Sie im Dialogfeld **neue Analysis Services Verbindung** den Namen des Servers ein.</span><span class="sxs-lookup"><span data-stu-id="4f25b-131">In the **New Analysis Services Connection** dialog box, type the name of the server.</span></span>  
  
4.  <span data-ttu-id="4f25b-132">Geben Sie die Authentifizierungsmethode an.</span><span class="sxs-lookup"><span data-stu-id="4f25b-132">Specify the authentication method.</span></span>  
  
5.  <span data-ttu-id="4f25b-133">Wählen Sie eine Datenbank aus der Dropdown Liste **Katalog Name** aus.</span><span class="sxs-lookup"><span data-stu-id="4f25b-133">Select a database from the **Catalog name** drop-down list.</span></span> <span data-ttu-id="4f25b-134">Wenn keine Datenbank in der Instanz vorhanden ist, wählen Sie **(Standard)** aus.</span><span class="sxs-lookup"><span data-stu-id="4f25b-134">If no database exists on the instance, select **(default)**.</span></span>  
  
6.  <span data-ttu-id="4f25b-135">Geben Sie einen Anzeigenamen für die Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="4f25b-135">Type a friendly name for the connection.</span></span>  
  
7.  <span data-ttu-id="4f25b-136">Klicken Sie auf **Verbindung testen** , um sicherzustellen, dass der Server und die Datenbank verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="4f25b-136">Click **Test Connection** to verify that the server and database are available.</span></span>  
  
8.  <span data-ttu-id="4f25b-137">Klicken Sie auf **OK**und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="4f25b-137">Click **OK**, and then click **Close**.</span></span>  
  
### <a name="connections-using-a-web-service"></a><span data-ttu-id="4f25b-138">Konfigurieren von Verbindungen mithilfe eines Webdiensts</span><span class="sxs-lookup"><span data-stu-id="4f25b-138">Connections using a Web Service</span></span>  
 <span data-ttu-id="4f25b-139">Wenn Sie eine Thin-Client-Architektur verwenden, um das Durchsuchen von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Cubes und -Daten zu ermöglichen, können Sie eine [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Serververbindung auch über Webdienste konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4f25b-139">If you are using a thin-client architecture to enable browsing of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cubes and data, you can also configure a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server through Web services.</span></span> <span data-ttu-id="4f25b-140">Informationen zum Definieren eines webbasierten Clients finden Sie in der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="4f25b-140">For information about how to define a Web-based client, see [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="4f25b-141">Wenn Sie über Zugriff auf einen Server verfügen, der für Webdienste konfiguriert wurde, können Sie beim Erstellen der Verbindung den Verbindungstyp angeben.</span><span class="sxs-lookup"><span data-stu-id="4f25b-141">If you have access to a server that has been configured for Web services, you can specify the connection type when you first create the connection.</span></span>  
  
##### <a name="create-an-http-connection-to-analysis-services"></a><span data-ttu-id="4f25b-142">Herstellen einer HTTP-Verbindung mit Analysis Services</span><span class="sxs-lookup"><span data-stu-id="4f25b-142">Create an HTTP connection to Analysis Services</span></span>  
  
1.  <span data-ttu-id="4f25b-143">Öffnen Sie das Dialogfeld **neue Analysis Services Verbindung** .</span><span class="sxs-lookup"><span data-stu-id="4f25b-143">Open the **New Analysis Services Connection** dialog box.</span></span>  
  
2.  <span data-ttu-id="4f25b-144">Geben Sie als Servernamen http:// und die URL für den entsprechenden [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Server ein.</span><span class="sxs-lookup"><span data-stu-id="4f25b-144">For the server name, type http:// followed by the URL assigned to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server.</span></span>  
  
3.  <span data-ttu-id="4f25b-145">Geben Sie den Benutzernamen und das Kennwort für den Zugriff auf den Webdienst ein.</span><span class="sxs-lookup"><span data-stu-id="4f25b-145">Type the user name and the password that is required to access the Web service.</span></span>  
  
### <a name="connections-in-the-visio-add-in"></a><span data-ttu-id="4f25b-146">Verbindungen im Visio-Add-In</span><span class="sxs-lookup"><span data-stu-id="4f25b-146">Connections in the Visio Add-In</span></span>  
 <span data-ttu-id="4f25b-147">Im Gegensatz zu Excel wird in Visio kein Menüband bereitgestellt, und es stehen keine speziellen Schaltflächen für die Erstellung und Überwachung von Verbindungen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="4f25b-147">Unlike Excel, Visio does not provide a tool ribbon, and there are no buttons specifically for creating or monitoring connections.</span></span> <span data-ttu-id="4f25b-148">Stattdessen wird die Datenverbindung hergestellt, wenn Sie zum ersten Mal ein Data Mining-Shape auswählen und auf einer Visio-Seite ablegen.</span><span class="sxs-lookup"><span data-stu-id="4f25b-148">Instead, the data connection is created when you first select a data mining shape and drop it onto a Visio page.</span></span> <span data-ttu-id="4f25b-149">Ein Assistent fordert Sie auf, das Modell für das Shape auszuwählen und weitere Optionen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="4f25b-149">A wizard will prompt you to select the model for the shape and to set other options.</span></span>  
  
 <span data-ttu-id="4f25b-150">Wenn Sie zuvor eine Verbindung mit einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Datenquelle in Excel verwendet haben, werden diese Verbindungen als mögliche Datenquellen aufgelistet, aus denen Sie auswählen können.</span><span class="sxs-lookup"><span data-stu-id="4f25b-150">If you have previously used a connection to an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] data source in Excel, these connections are listed as possible data sources from which to select.</span></span>  
  
##### <a name="create-a-connection-for-a-visio-shape"></a><span data-ttu-id="4f25b-151">Herstellen einer Verbindung für ein Visio-Shape</span><span class="sxs-lookup"><span data-stu-id="4f25b-151">Create a connection for a Visio shape</span></span>  
  
1.  <span data-ttu-id="4f25b-152">Öffnen Sie die Data Mining-Vorlage, und wählen Sie eines der Data Mining-Shapes aus.</span><span class="sxs-lookup"><span data-stu-id="4f25b-152">Open the Data Mining Template, and select one of the data mining shapes.</span></span>  
  
2.  <span data-ttu-id="4f25b-153">Ziehen Sie das Shape, und legen Sie es auf einer leeren Seite ab.</span><span class="sxs-lookup"><span data-stu-id="4f25b-153">Drag and drop the shape to a blank page.</span></span>  
  
3.  <span data-ttu-id="4f25b-154">Wählen Sie im Dialogfeld **Datenquelle auswählen** eine Datenquelle aus der Liste aus, oder klicken Sie auf **neu**.</span><span class="sxs-lookup"><span data-stu-id="4f25b-154">In the **Select a data source** dialog box, select a data source from the list, or click **New**.</span></span>  
  
4.  <span data-ttu-id="4f25b-155">Wenn Sie **neu**auswählen, befolgen Sie das zuvor beschriebene Verfahren, um einen Server-und Katalognamen anzugeben oder um eine Verbindung über einen Webdienst herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4f25b-155">If you select **New**, follow the procedure that is described earlier to specify a server and catalog name, or to connect through a Web service.</span></span>  
  
##  <a name="changing-connections"></a><a name="bkmk_change"></a><span data-ttu-id="4f25b-156">Ändern von Verbindungen</span><span class="sxs-lookup"><span data-stu-id="4f25b-156">Changing Connections</span></span>  
 <span data-ttu-id="4f25b-157">Sie können mehrere Verbindungen in einem Arbeitsblatt erstellen, aber es kann jeweils nur eine Verbindung aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="4f25b-157">You can create multiple connections in the same worksheet, but only one connection can be active at a time.</span></span> <span data-ttu-id="4f25b-158">Der Name der aktuellen Verbindung wird in der **Verbindungs** Schaltfläche angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4f25b-158">The name of the current connection is displayed in the **Connection** button.</span></span>  
  
 <span data-ttu-id="4f25b-159">Im Data Mining-Client für Excel können Sie auch die Verbindungs Zeichenfolge und den Status der aktuellen Verbindung überprüfen, indem Sie auf Ablauf **Verfolgung** und dann auf **aktuelle Verbindung**klicken.</span><span class="sxs-lookup"><span data-stu-id="4f25b-159">In the Data Mining Client for Excel, you can also verify the connection string and status for the current connection by clicking **Trace** and then clicking **Current Connection**.</span></span>  
  
#### <a name="use-a-different-server-connection"></a><span data-ttu-id="4f25b-160">Verwenden einer anderen Serververbindung</span><span class="sxs-lookup"><span data-stu-id="4f25b-160">Use a different server connection</span></span>  
  
1.  <span data-ttu-id="4f25b-161">Klicken Sie auf **Verbindung**.</span><span class="sxs-lookup"><span data-stu-id="4f25b-161">Click **Connection**.</span></span>  
  
2.  <span data-ttu-id="4f25b-162">Wählen Sie im Bereich **Analysis Services Verbindungen** in der Liste **andere Verbindungen** eine Verbindung aus, und klicken Sie auf **aktuellen erstellen**.</span><span class="sxs-lookup"><span data-stu-id="4f25b-162">In the **Analysis Services Connections** pane, select a connection from the **Other Connections** list, and click **Make Current**.</span></span>  
  
3.  <span data-ttu-id="4f25b-163">Klicken Sie auf **Verbindung testen** , um sicherzustellen, dass die Verbindung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="4f25b-163">Click **Test Connection** to verify that the connection is available.</span></span>  
  
 <span data-ttu-id="4f25b-164">Nachdem ein Miningmodell fertig verarbeitet wurde, werden die Ergebnisse lokal gespeichert. Wenn Sie zu diesem Zeitpunkt die Verbindung mit einem Server schließen und eine Verbindung mit einem anderen Server herstellen, hat dies keine Auswirkungen auf die Daten.</span><span class="sxs-lookup"><span data-stu-id="4f25b-164">After a mining model has finished processing, the results are stored locally, and there is no effect on the data if you close the connection to one server and then connect to another server.</span></span> <span data-ttu-id="4f25b-165">Sie sollten die Verbindung jedoch nicht während der Verarbeitung des Data Mining-Modells ändern oder trennen, da dadurch die Daten beschädigt werden können.</span><span class="sxs-lookup"><span data-stu-id="4f25b-165">However, you should avoid changing connections or losing the connection when a data mining model is being processed, because this could corrupt data.</span></span>  
  
#### <a name="modify-an-existing-server-connection"></a><span data-ttu-id="4f25b-166">Ändern einer vorhandenen Serververbindung</span><span class="sxs-lookup"><span data-stu-id="4f25b-166">Modify an existing server connection</span></span>  
  
1.  <span data-ttu-id="4f25b-167">Bestehende Verbindungen können nicht geändert werden. Wenn Sie eine Verbindung mit einer anderen Datenbank oder einem anderen Server herstellen möchten, sollten Sie eine neue Verbindung erstellen.</span><span class="sxs-lookup"><span data-stu-id="4f25b-167">You cannot modify an existing connection; if you want to connect to a different database or a different server, you should create a new connection.</span></span>  
  
2.  <span data-ttu-id="4f25b-168">Wenn Sie die Verbindungszeichenfolge ändern müssen, um das Abfragetimeout zu erhöhen oder der Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] weitere Parameter hinzuzufügen, besteht eine Möglichkeit darin, die DMC-Datei mit der gespeicherten Verbindungszeichenfolge zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="4f25b-168">If you must modify the connection string to increase the query timeout or add other parameters specific to your instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], one option is to edit the .dmc file, where the connection string is stored.</span></span>  
  
     <span data-ttu-id="4f25b-169">\<drive:>\Users \\<MyUserName \> \appdata\local\microsoft\data Mining-Add-in</span><span class="sxs-lookup"><span data-stu-id="4f25b-169">\<drive:>\Users\\<myusername\>\AppData\Local\Microsoft\Data Mining Add-in</span></span>  
  
##  <a name="connecting-to-external-data-sources"></a><a name="bkmk_extconnections"></a><span data-ttu-id="4f25b-170">Herstellen einer Verbindung mit externen Datenquellen</span><span class="sxs-lookup"><span data-stu-id="4f25b-170">Connecting to External Data Sources</span></span>  
 <span data-ttu-id="4f25b-171">Während die Tools im Menüband **analysieren** ausschließlich mit Daten in Excel funktionieren, können Sie mit den Tools im **Data Mining** -Menüband direkt eine Verbindung mit externen Datenquellen herstellen, die als Eingaben für das Modell verwendet werden sollen, oder für die Stichprobenentnahme.</span><span class="sxs-lookup"><span data-stu-id="4f25b-171">Whereas the tools in the **Analyze** ribbon work exclusively with data in Excel, the tools in the **Data Mining** ribbon let you connect directly to external data sources to use as inputs for your model, or for sampling.</span></span>  
  
 <span data-ttu-id="4f25b-172">Die Add-Ins enthalten folgende Tools, die die Verwendung externer Daten für das Data Mining unterstützen:</span><span class="sxs-lookup"><span data-stu-id="4f25b-172">The following tools in these add-ins support use of external data for data mining:</span></span>  
  
-   [<span data-ttu-id="4f25b-173">Beispiel Daten &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="4f25b-173">Sample Data &#40;SQL Server Data Mining Add-ins&#41;</span></span>](sample-data-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="4f25b-174">Assistent zum Klassifizieren &#40;Data Mining-Add-Ins für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4f25b-174">Classify Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](classify-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="4f25b-175">Assistent zum Schätzen von Daten &#40;Data Mining-Add-Ins für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4f25b-175">Estimate Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](estimate-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="4f25b-176">Cluster-Assistent &#40;Data Mining-Add-Ins für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4f25b-176">Cluster Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](cluster-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="4f25b-177">Planungs-Assistent &#40;Data Mining-Add-Ins für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4f25b-177">Forecast Wizard &#40;Data Mining Add-ins for Excel&#41;</span></span>](forecast-wizard-data-mining-add-ins-for-excel.md)  
  
-   [<span data-ttu-id="4f25b-178">Mining Struktur &#40;SQL Server Data Mining-Add-Ins erstellen&#41;</span><span class="sxs-lookup"><span data-stu-id="4f25b-178">Create Mining Structure &#40;SQL Server Data Mining Add-ins&#41;</span></span>](create-mining-structure-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="4f25b-179">Genauigkeits Diagramm &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="4f25b-179">Accuracy Chart &#40;SQL Server Data Mining Add-ins&#41;</span></span>](accuracy-chart-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="4f25b-180">Gewinn Diagramm &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="4f25b-180">Profit Chart &#40;SQL Server Data Mining Add-ins&#41;</span></span>](profit-chart-sql-server-data-mining-add-ins.md)  
  
-   [<span data-ttu-id="4f25b-181">Klassifizierungs Matrix &#40;SQL Server Data Mining-Add-ins&#41;</span><span class="sxs-lookup"><span data-stu-id="4f25b-181">Classification Matrix &#40;SQL Server Data Mining Add-ins&#41;</span></span>](classification-matrix-sql-server-data-mining-add-ins.md)  
  
### <a name="using-analysis-services-as-a-data-source"></a><span data-ttu-id="4f25b-182">Verwenden von Analysis Services als Datenquelle</span><span class="sxs-lookup"><span data-stu-id="4f25b-182">Using Analysis Services as a Data Source</span></span>  
 <span data-ttu-id="4f25b-183">Sie haben keinen direkten Zugriff auf Daten, die in einem [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Cube oder einem tabellarischen Modell gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="4f25b-183">You cannot directly access data stored in an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube or tabular model.</span></span> <span data-ttu-id="4f25b-184">Stellen Sie stattdessen in Excel eine Verbindung mit dem [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Server her, und erstellen Sie auf Grundlage der Daten ein Modell.</span><span class="sxs-lookup"><span data-stu-id="4f25b-184">Instead, create a connection in Excel to the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server, and use the data to create a model.</span></span>  
  
### <a name="relational-data-sources"></a><span data-ttu-id="4f25b-185">Relationale Datenquellen</span><span class="sxs-lookup"><span data-stu-id="4f25b-185">Relational Data Sources</span></span>  
 <span data-ttu-id="4f25b-186">Wenn Sie Daten aus einer relationalen Quelle als Eingabedaten für Ihr Modell verwenden möchten, können Sie eine Verbindung mit den folgenden SQL Server-Versionen herstellen:</span><span class="sxs-lookup"><span data-stu-id="4f25b-186">If you want to use data from a relational source as input to your model, you can connect to the following versions of SQL Server:</span></span>  
  
-   <span data-ttu-id="4f25b-187">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="4f25b-187">SQL Server 2008</span></span>  
  
-   <span data-ttu-id="4f25b-188">SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="4f25b-188">SQL Server 2008 R2</span></span>  
  
-   <span data-ttu-id="4f25b-189">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="4f25b-189">SQL Server 2012</span></span>  
  
 <span data-ttu-id="4f25b-190">Sie können Daten auch aus einer beliebigen relationalen Datenquelle abrufen, die von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] als Datenquelle unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="4f25b-190">You can also get data from any other relational data source that is supported as a data source by [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)].</span></span> <span data-ttu-id="4f25b-191">Informationen zu unterstützten Datenquellen finden Sie unter [Datenquellen in mehrdimensionalen Modellen](multidimensional-models/data-sources-in-multidimensional-models.md) .</span><span class="sxs-lookup"><span data-stu-id="4f25b-191">For information about supported data sources, see [Data Sources in Multidimensional Models](multidimensional-models/data-sources-in-multidimensional-models.md)</span></span>  
  
 <span data-ttu-id="4f25b-192">Beachten Sie, dass die folgenden Datentypen nicht für das Data Mining verwendet werden können und einen Fehler verursachen, wenn sie beim Erstellen eines Modells eingefügt werden:</span><span class="sxs-lookup"><span data-stu-id="4f25b-192">Note that the following data types cannot be used for data mining and will result in an error if included when you build a model:</span></span>  
  
-   <span data-ttu-id="4f25b-193">ntext</span><span class="sxs-lookup"><span data-stu-id="4f25b-193">ntext</span></span>  
  
-   <span data-ttu-id="4f25b-194">BINARY</span><span class="sxs-lookup"><span data-stu-id="4f25b-194">binary</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f25b-195">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4f25b-195">See Also</span></span>  
 [<span data-ttu-id="4f25b-196">Ablauf Verfolgung &#40;Data Mining-Client für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="4f25b-196">Trace &#40;Data Mining Client for Excel&#41;</span></span>](trace-data-mining-client-for-excel.md)  
  
  
