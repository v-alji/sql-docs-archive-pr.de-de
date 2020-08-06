---
title: Erstellen, löschen oder Ändern einer freigegebenen Datenquelle (Berichts-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- shared data sources [Reporting Services]
- removing shared data sources
- data sources [Reporting Services], shared
- deleting shared data sources
- modifying shared data sources
ms.assetid: cd7bace3-f8ec-4ee3-8a9f-2f217cdca9f2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c6f4ff658e656b159995087df3121806b462e687
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618551"
---
# <a name="create-delete-or-modify-a-shared-data-source-report-manager"></a><span data-ttu-id="a9b84-102">Erstellen, Löschen oder Ändern einer freigegebenen Datenquelle (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="a9b84-102">Create, Delete, or Modify a Shared Data Source (Report Manager)</span></span>
  <span data-ttu-id="a9b84-103">Mit einer freigegebenen Datenquelle werden Verbindungseigenschaften für eine Datenquelle angegeben.</span><span class="sxs-lookup"><span data-stu-id="a9b84-103">A shared data source specifies connection properties for a data source.</span></span> <span data-ttu-id="a9b84-104">Falls Sie über eine Datenquelle verfügen, die von einer großen Anzahl Berichte, Modelle oder datengesteuerter Abonnements verwendet wird, sollten Sie die Erstellung einer freigegebenen Datenquelle in Erwägung ziehen, um den Aufwand für die Pflege der Verbindungsinformationen an mehreren Stellen zu verringern.</span><span class="sxs-lookup"><span data-stu-id="a9b84-104">If you have a data source that is used by a large number of reports, models, or data-driven subscriptions, consider creating a shared data source to eliminate the overhead of having to maintain the same connection information in multiple places.</span></span>  
  
 <span data-ttu-id="a9b84-105">Das folgende Symbol bezeichnet eine freigegebene Datenquelle in der Ordnerhierarchie des Berichts-Managers:</span><span class="sxs-lookup"><span data-stu-id="a9b84-105">The following icon indicates a shared data source in the Report Manager folder hierarchy:</span></span>  
  
 <span data-ttu-id="a9b84-106">![Symbol für freigegebene Datenquelle](media/hlp-16datasource.png "Symbol für freigegebene Datenquelle")</span><span class="sxs-lookup"><span data-stu-id="a9b84-106">![Shared data source icon](media/hlp-16datasource.png "Shared data source icon")</span></span>  
<span data-ttu-id="a9b84-107">Symbol für freigegebene Datenquelle</span><span class="sxs-lookup"><span data-stu-id="a9b84-107">shared data source icon</span></span>  
  
### <a name="to-create-a-shared-data-source"></a><span data-ttu-id="a9b84-108">So erstellen Sie eine freigegebene Datenquelle</span><span class="sxs-lookup"><span data-stu-id="a9b84-108">To create a shared data source</span></span>  
  
1.  <span data-ttu-id="a9b84-109">Starten Sie den [Berichts-Manager &#40;einheitlicher SSRS-Modus&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span><span class="sxs-lookup"><span data-stu-id="a9b84-109">Start [Report Manager  &#40;SSRS Native Mode&#41;](../../2014/reporting-services/report-manager-ssrs-native-mode.md).</span></span>  
  
2.  <span data-ttu-id="a9b84-110">Navigieren Sie in Berichts-Manager zur Seite **Inhalt** .</span><span class="sxs-lookup"><span data-stu-id="a9b84-110">In Report Manager, navigate to the **Contents** page.</span></span>  
  
3.  <span data-ttu-id="a9b84-111">Klicken Sie auf **Neue Datenquelle**.</span><span class="sxs-lookup"><span data-stu-id="a9b84-111">Click **New Data Source**.</span></span> <span data-ttu-id="a9b84-112">Die Seite **Neue Datenquelle** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a9b84-112">The **New Data Source** page opens.</span></span>  
  
4.  <span data-ttu-id="a9b84-113">Geben Sie einen Namen für das Element ein.</span><span class="sxs-lookup"><span data-stu-id="a9b84-113">Type a name for the item.</span></span> <span data-ttu-id="a9b84-114">Ein Name muss mindestens ein Zeichen enthalten und muss mit einem Buchstaben beginnen.</span><span class="sxs-lookup"><span data-stu-id="a9b84-114">A name must contain at least one character and it must start with a letter.</span></span> <span data-ttu-id="a9b84-115">Er kann auch Sonderzeichen enthalten, er darf jedoch keine Leerzeichen und folgende Zeichen nicht enthalten: ; ?</span><span class="sxs-lookup"><span data-stu-id="a9b84-115">It can also include certain symbols, but not spaces or the characters ; ?</span></span> <span data-ttu-id="a9b84-116">: \@ & = +, $/\* \< > | " /.</span><span class="sxs-lookup"><span data-stu-id="a9b84-116">: \@ & = + , $ / \* \< > | " /.</span></span>  
  
5.  <span data-ttu-id="a9b84-117">Optional können Sie auch eine Beschreibung eingeben, um Benutzern Informationen zur Verbindung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="a9b84-117">Optionally type a description to provide users with information about the connection.</span></span> <span data-ttu-id="a9b84-118">Diese Beschreibung wird auf der Seite **Inhalt** im Berichts-Manager angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9b84-118">This description will appear on the **Contents** page in Report Manager.</span></span>  
  
6.  <span data-ttu-id="a9b84-119">Geben Sie in der Liste **Datenquellentyp** die Datenverarbeitungserweiterung an, die zum Verarbeiten von Daten aus der Datenquelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a9b84-119">In the **Data source type** list, specify the data processing extension that is used to process data from the data source.</span></span>  
  
7.  <span data-ttu-id="a9b84-120">Geben Sie in das Feld **Verbindungszeichenfolge**die Verbindungszeichenfolge an, die vom Berichtsserver zum Herstellen der Verbindung zur Datenquelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a9b84-120">For **Connection string**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="a9b84-121">Es wird empfohlen, dass Sie keine Anmeldeinformationen in der Verbindungszeichenfolge angeben.</span><span class="sxs-lookup"><span data-stu-id="a9b84-121">It is recommended that you do not specify credentials in the connection string.</span></span>  
  
     <span data-ttu-id="a9b84-122">Das folgende Beispiel veranschaulicht eine Verbindungs Zeichenfolge zum Herstellen einer Verbindung mit der lokalen- [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] Datenbank:</span><span class="sxs-lookup"><span data-stu-id="a9b84-122">The following example illustrates a connection string for connecting to the local [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database:</span></span>  
  
    ```  
    data source=<localservername>; initial catalog=AdventureWorks2012  
    ```  
  
8.  <span data-ttu-id="a9b84-123">Geben Sie für **Verbindung herstellen über**an, wie die Anmeldeinformationen bei Ausführung des Berichts abgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="a9b84-123">For **Connect using**, specify how credentials are obtained when the report runs:</span></span>  
  
    -   <span data-ttu-id="a9b84-124">Wenn der Benutzer zur Eingabe eines Anmeldenamens und eines Kennworts aufgefordert werden soll, klicken Sie auf **Bereitgestellte Anmeldeinformationen vom Benutzer, der den Bericht ausführt**.</span><span class="sxs-lookup"><span data-stu-id="a9b84-124">If you want to prompt the user for a logon name and password, click **Credentials supplied by the user running the report**.</span></span> <span data-ttu-id="a9b84-125">Klicken Sie auf **Beim Herstellen einer Verbindung mit der Datenquelle als Windows-Anmeldeinformationen verwenden**, um die vom Benutzer eingegebenen Anmeldeinformationen als Windows-Anmeldeinformationen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9b84-125">To use the credentials that the user enters as Windows credentials, click **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="a9b84-126">Wenn der Benutzername und das Kennwort Datenbank-Anmeldeinformationen darstellen, sollten Sie diese Option nicht aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a9b84-126">If the user name and password are database credentials, do not select this option.</span></span>  
  
    -   <span data-ttu-id="a9b84-127">Wenn Sie die Datenquelle als freigegebene Datenquelle mit gespeicherten, vom Besitzer der Datenquelle verwalteten Anmeldeinformationen verwenden möchten bzw. für Berichte, die Abonnements oder andere geplante Vorgänge (z.B. automatisierte Berichtsverlaufgenerierung) unterstützen, klicken Sie auf **Anmeldeinformationen, die sicher auf dem Berichtsserver gespeichert sind**.</span><span class="sxs-lookup"><span data-stu-id="a9b84-127">If you intend to use the data source as a shared data source with saved credentials that are managed by the owner of the data source, or for reports that support subscriptions or other scheduled operations (such as automated report history generation), click **Credentials stored securely in the report server**.</span></span> <span data-ttu-id="a9b84-128">Wenn der Datenbankserver Identitätswechsel oder Delegierung unterstützt, können Sie die Option **Die Identität des authentifizierten Benutzers annehmen, nachdem eine Verbindung zur Datenquelle hergestellt wurde**auswählen.</span><span class="sxs-lookup"><span data-stu-id="a9b84-128">If the database server supports impersonation or delegation, you can select **Impersonate the authenticated user after a connection has been made to the data source**.</span></span>  
  
    -   <span data-ttu-id="a9b84-129">Wenn der Berichtsserver die Anmeldeinformationen des auf den Bericht zugreifenden Benutzers an den Server übergeben soll, der die externe Datenquelle hostet, klicken Sie auf **Integrierte Sicherheit von Windows**.</span><span class="sxs-lookup"><span data-stu-id="a9b84-129">If you want the report server to pass the credentials of the user accessing the report to the server hosting the external data source, click **Windows Integrated Security**.</span></span> <span data-ttu-id="a9b84-130">In diesem Fall wird der Benutzer nicht aufgefordert, einen Benutzernamen oder ein Kennwort einzugeben.</span><span class="sxs-lookup"><span data-stu-id="a9b84-130">In this case, the user is not prompted to type a user name or password.</span></span>  
  
    -   <span data-ttu-id="a9b84-131">Klicken Sie auf **Anmeldeinformationen sind nicht erforderlich**, wenn Sie eine Datenquelle verwenden, die nicht mit Anmeldeinformationen arbeitet (z.B. wenn es sich bei der Datenquelle um eine XML-Datei handelt, auf die vom Dateisystem zugegriffen wird).</span><span class="sxs-lookup"><span data-stu-id="a9b84-131">If the data source does not use credentials (for example, if the data source is an XML file that is accessed from the file system), click **Credentials are not required**.</span></span> <span data-ttu-id="a9b84-132">Diesen Typ Anmeldeinformationen sollten Sie nur dann angeben, wenn er von der Datenquelle unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="a9b84-132">You should only specify this credential type if it is valid for the data source.</span></span> <span data-ttu-id="a9b84-133">Wenn Sie diese Option für eine Datenquelle aktivieren, die Authentifizierung erfordert, schlägt die Verbindungsherstellung fehl.</span><span class="sxs-lookup"><span data-stu-id="a9b84-133">If you select this option for a data source that requires authentication, the connection will fail.</span></span> <span data-ttu-id="a9b84-134">Vergewissern Sie sich bei der Auswahl dieser Option, dass Sie das unbeaufsichtigte Ausführungskonto konfigurieren, mit dem der Berichtsserver eine Verbindung zu anderen Computern herstellen kann, um Daten oder Dateien abzurufen, wenn keine Anmeldeinformationen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="a9b84-134">If you select this option, be sure to configure the unattended execution account that allows the report server to connect to other computers to retrieve data or files when user credentials are not available.</span></span>  
  
     <span data-ttu-id="a9b84-135">Weitere Informationen zum Konfigurieren von Anmeldeinformationen finden Sie unter [Angeben der Anmeldeinformationen und Verbindungsinformationen für Berichtsdatenquellen](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="a9b84-135">For more information about configuring credentials, see [Specify Credential and Connection Information for Report Data Sources](report-data/specify-credential-and-connection-information-for-report-data-sources.md).</span></span> <span data-ttu-id="a9b84-136">Weitere Informationen zum Konto für die unbeaufsichtigte Ausführung finden Sie unter [Konfigurieren des unbeaufsichtigten Ausführungskontos (SSRS-Konfigurations-Manager)](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="a9b84-136">For more information about the unattended execution account, see [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
9. <span data-ttu-id="a9b84-137">Klicken Sie auf die Schaltfläche **Verbindung testen** , um die Datenquellenkonfiguration zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a9b84-137">Click the **Test Connection** button to validate the data source configuration.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a9b84-138">Die Schaltfläche zum Testen der Verbindung wird für den XML-Datenquellentyp nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a9b84-138">The Test Connection button is not supported for the XML data source type.</span></span>  
  
10. <span data-ttu-id="a9b84-139">Klicken Sie auf **OK**</span><span class="sxs-lookup"><span data-stu-id="a9b84-139">Click **OK**</span></span>  
  
### <a name="to-modify-a-shared-data-source"></a><span data-ttu-id="a9b84-140">So ändern Sie eine freigegebene Datenquelle</span><span class="sxs-lookup"><span data-stu-id="a9b84-140">To modify a shared data source</span></span>  
  
1.  <span data-ttu-id="a9b84-141">Navigieren Sie im Berichts-Manager zur Seite Inhalt.</span><span class="sxs-lookup"><span data-stu-id="a9b84-141">In Report Manager, navigate to the Contents page.</span></span>  
  
2.  <span data-ttu-id="a9b84-142">Navigieren Sie zum freigegebenen Datenquellenelement, zeigen Sie auf das Element, klicken Sie auf die Dropdownliste, und klicken Sie im Kontextmenü auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="a9b84-142">Navigate to the shared data source item, hover over the item, click the drop-down list, and from the context menu, click **Manage**.</span></span> <span data-ttu-id="a9b84-143">Die Seite **Eigenschaften** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a9b84-143">The **Properties** page opens.</span></span>  
  
3.  <span data-ttu-id="a9b84-144">Ändern Sie die Datenquelle, und klicken Sie anschließend auf **Anwenden**.</span><span class="sxs-lookup"><span data-stu-id="a9b84-144">Modify the data source, and then click **Apply**.</span></span>  
  
### <a name="to-delete-a-shared-data-source"></a><span data-ttu-id="a9b84-145">So löschen Sie eine freigegebene Datenquelle</span><span class="sxs-lookup"><span data-stu-id="a9b84-145">To delete a shared data source</span></span>  
  
-   <span data-ttu-id="a9b84-146">Navigieren Sie im Berichts-Manager zur Seite **Inhalt** , und führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a9b84-146">In Report Manager, navigate to the **Contents** page and do one of the following:</span></span>  
  
    -   <span data-ttu-id="a9b84-147">Navigieren Sie zum Element der freigegebenen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="a9b84-147">Navigate to the shared data source item.</span></span>  
  
         <span data-ttu-id="a9b84-148">Klicken Sie auf das Element, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a9b84-148">Click the item to open it.</span></span> <span data-ttu-id="a9b84-149">Die Seite Allgemeine Eigenschaften wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="a9b84-149">The General Properties page opens.</span></span>  
  
         <span data-ttu-id="a9b84-150">Klicken Sie auf **Löschen** und dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9b84-150">Click **Delete**, and then click **OK**.</span></span>  
  
    -   <span data-ttu-id="a9b84-151">Navigieren Sie auf der Seite **Inhalt** zu dem Ordner, der die zu löschende Datenquelle enthält.</span><span class="sxs-lookup"><span data-stu-id="a9b84-151">In the **Contents** page, navigate to the folder that contains the data source you want to delete.</span></span>  
  
         <span data-ttu-id="a9b84-152">Zeigen Sie auf das Element, klicken Sie auf die Dropdownliste, und klicken Sie im Kontextmenü auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="a9b84-152">Hover over the item, click the drop-down list, and from the context menu, click **Delete**.</span></span>  
  
         [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a9b84-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a9b84-153">See Also</span></span>  
 <span data-ttu-id="a9b84-154">[Datenverbindungen, Datenquellen und Verbindungs Zeichenfolgen in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="a9b84-154">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="a9b84-155">[Die Inhaltsseite &#40;Berichts-Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="a9b84-155">[Contents Page &#40;Report Manager&#41;](../../2014/reporting-services/contents-page-report-manager.md) </span></span>  
 <span data-ttu-id="a9b84-156">[Erstellen, ändern und Löschen von freigegebenen Datenquellen &#40;SSRS-&#41;](report-data/create-modify-and-delete-shared-data-sources-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="a9b84-156">[Create, Modify, and Delete Shared Data Sources &#40;SSRS&#41;](report-data/create-modify-and-delete-shared-data-sources-ssrs.md) </span></span>  
 <span data-ttu-id="a9b84-157">[Verwalten von Berichtsdaten Quellen](report-data/manage-report-data-sources.md) </span><span class="sxs-lookup"><span data-stu-id="a9b84-157">[Manage Report Data Sources](report-data/manage-report-data-sources.md) </span></span>  
 [<span data-ttu-id="a9b84-158">Konfigurieren von Datenquelleneigenschaften für einen Bericht &#40;Berichts-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="a9b84-158">Configure Data Source Properties for a Report  &#40;Report Manager&#41;</span></span>](report-data/configure-data-source-properties-for-a-report-report-manager.md)  
  
  
