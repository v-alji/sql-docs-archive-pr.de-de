---
title: Speichern von Anmeldeinformationen in einer Reporting Services-Datenquelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/23/2015
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- credentials [Reporting Services]
- security [Analysis Services], data sources
- stored credentials [Reporting Services]
- data sources [Reporting Services], stored credentials
ms.assetid: dc700922-97fa-4b30-9547-05bbbec4f09c
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: fccf8669d1f39d19a26b443ffcead8e86db66a34
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620225"
---
# <a name="store-credentials-in-a-reporting-services-data-source"></a><span data-ttu-id="c2104-102">Speichern von Anmeldeinformationen in einer Reporting Services-Datenquelle</span><span class="sxs-lookup"><span data-stu-id="c2104-102">Store Credentials in a Reporting Services Data Source</span></span>
  <span data-ttu-id="c2104-103">Sie können gespeicherte Anmeldeinformationen, mit denen ein [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] -Berichtsserver auf externe Daten für einen Bericht zugreift, konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c2104-103">You can configure stored credentials that a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] report server uses to access external data for a report.</span></span> <span data-ttu-id="c2104-104">Gespeicherte Anmeldeinformationen werden verwendet, wenn der unbeaufsichtigt ausgeführt, beispielsweise bei einem [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] -Abonnement, das einen Bericht als E-Mail veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="c2104-104">Stored credentials are used if the report runs unattended, for example a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] subscription that publishes a report as an e-mail.</span></span> <span data-ttu-id="c2104-105">Der Berichtsserver ruft die Anmeldeinformationen ab und verwendet sie, wenn die Berichtsverarbeitung geplant oder ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="c2104-105">The report server retrieves and uses the credentials when report processing is scheduled or triggered.</span></span> <span data-ttu-id="c2104-106">In diesem Thema werden die einzelnen Schritte für die Konfiguration gespeicherter Anmeldeinformationen für Berichtsserver im einheitlichen Modus und im SharePoint-Modus dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c2104-106">This topic walks you through configuring stored credentials for both Native mode and SharePoint mode report servers.</span></span>

||
|-|
|<span data-ttu-id="c2104-107">**[!INCLUDE[applies](../../includes/applies-md.md)]** [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] im einheitlichen Modus &#124; [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] im SharePoint-Modus</span><span class="sxs-lookup"><span data-stu-id="c2104-107">**[!INCLUDE[applies](../../includes/applies-md.md)]**  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] Native mode &#124; [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] SharePoint mode</span></span>|

 <span data-ttu-id="c2104-108">**In diesem Thema:**</span><span class="sxs-lookup"><span data-stu-id="c2104-108">**In this topic:**</span></span>

-   [<span data-ttu-id="c2104-109">Konfigurieren von gespeicherten Anmeldeinformationen für eine berichtsspezifische Datenquelle (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="c2104-109">Configure stored credentials for a report-specific data source (Native mode)</span></span>](#bkmk_stored_credentials_data_source_native)

-   [<span data-ttu-id="c2104-110">Konfigurieren von gespeicherten Anmeldeinformationen für eine berichtsspezifische Datenquelle (SharePoint-Modus)</span><span class="sxs-lookup"><span data-stu-id="c2104-110">Configure stored credentials for a report-specific data source (SharePoint mode)</span></span>](#bkmk_stored_credentials_data_source_sharepoint)

-   [<span data-ttu-id="c2104-111">Konfigurieren von gespeicherten Anmeldeinformationen für eine freigegebene Datenquelle (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="c2104-111">Configure stored credentials for a shared data source (Native mode)</span></span>](#bkmk_stored_credentials_shared_data_source_native)

-   [<span data-ttu-id="c2104-112">Konfigurieren von gespeicherten Anmeldeinformationen für eine freigegebene Datenquelle (SharePoint-Modus)</span><span class="sxs-lookup"><span data-stu-id="c2104-112">Configure stored credentials for a shared data source (SharePoint mode)</span></span>](#bkmk_stored_credentials_shared_data_source_sharepoint)

##  <a name="security-policy-requirements-for-stored-credentials"></a><a name="bkmk_top"></a><span data-ttu-id="c2104-113">Sicherheitsrichtlinien Anforderungen für gespeicherte Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="c2104-113">Security policy requirements for stored credentials</span></span>
 <span data-ttu-id="c2104-114">![as_powerpivot_refresh_sss_set_key](../../analysis-services/media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key") Für das Konto, das Sie für gespeicherte Anmeldeinformationen verwenden, muss eine der folgenden Sicherheitsrichtlinien auf dem Berichtsserver konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="c2104-114">![as_powerpivot_refresh_sss_set_key](../../analysis-services/media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key") It is required that the account you use for stored credentials, is configured for one of the following security policies on the report server.</span></span> <span data-ttu-id="c2104-115">Es wird empfohlen, dass Sie die Richtlinie mit den mindestens erforderlichen Berechtigungen für Ihre Umgebung auswählen.</span><span class="sxs-lookup"><span data-stu-id="c2104-115">It is recommended you select the policy with the minimum level of permissions you require for your environment.</span></span>

1.  <span data-ttu-id="c2104-116">**Lokale Anmeldung zulassen**</span><span class="sxs-lookup"><span data-stu-id="c2104-116">**Allow log on locally**.</span></span> <span data-ttu-id="c2104-117">Weitere Informationen finden Sie unter [Lokal anmelden zulassen](https://technet.microsoft.com/library/cc756809\(v=WS.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="c2104-117">For more information, see [Allow log on locally](https://technet.microsoft.com/library/cc756809\(v=WS.10\).aspx).</span></span>

2.  <span data-ttu-id="c2104-118">**Anmelden als Stapelverarbeitungsauftrag**.</span><span class="sxs-lookup"><span data-stu-id="c2104-118">**Log on as a batch job**.</span></span> <span data-ttu-id="c2104-119">Weitere Informationen finden Sie unter [Anmelden als Stapelverarbeitungsauftrag](https://technet.microsoft.com/library/cc755659\(v=ws.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="c2104-119">For more information, see [Log on as a batch job](https://technet.microsoft.com/library/cc755659\(v=ws.10\).aspx).</span></span>

3.  <span data-ttu-id="c2104-120">Allgemeine Informationen zu Richtlinien finden Sie unter [Bearbeiten von Sicherheitseinstellungen für ein Gruppenrichtlinienobjekt](https://technet.microsoft.com/library/cc736516\(v=ws.10\).aspx).</span><span class="sxs-lookup"><span data-stu-id="c2104-120">For general information on policies, see [Edit security settings on a Group Policy object](https://technet.microsoft.com/library/cc736516\(v=ws.10\).aspx).</span></span>

##  <a name="configure-stored-credentials-for-a-report-specific-data-source-native-mode"></a><a name="bkmk_stored_credentials_data_source_native"></a><span data-ttu-id="c2104-121">Konfigurieren gespeicherter Anmelde Informationen für eine Berichts spezifische Datenquelle (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="c2104-121">Configure stored credentials for a report-specific data source (Native mode)</span></span>

1.  <span data-ttu-id="c2104-122">Navigieren Sie im Berichts-Manager im einheitlichen Modus zu dem Ordner, der den Bericht enthält.</span><span class="sxs-lookup"><span data-stu-id="c2104-122">In Native mode Report Manager, browse to the folder that contains the report.</span></span> <span data-ttu-id="c2104-123">Klicken Sie ![im Berichts-Manager für SSRS-Elemente](../media/ssrs-report-manager-item-context-menu.png "Kontextmenü im Berichts-Manager für SSRS-Elemente")auf das Kontextmenü Element Kontextmenü.</span><span class="sxs-lookup"><span data-stu-id="c2104-123">Click the item context menu ![context menu in report manager for ssrs items](../media/ssrs-report-manager-item-context-menu.png "context menu in report manager for ssrs items").</span></span>

2.  <span data-ttu-id="c2104-124">Klicken Sie auf **Verwalten** und dann auf **Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="c2104-124">Click **Manage** and then click **Data Sources**.</span></span>

3.  <span data-ttu-id="c2104-125">Wählen Sie **Eine benutzerdefinierte Datenquelle**.</span><span class="sxs-lookup"><span data-stu-id="c2104-125">Select **A custom data source**.</span></span>

4.  <span data-ttu-id="c2104-126">Wählen Sie in der Liste **Datenquellentyp** die Datenverarbeitungserweiterung aus, die zum Verarbeiten von Daten aus der Datenquelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c2104-126">In the **Data Source Type** list, select the data processing extension that is used to process data from the data source.</span></span>

5.  <span data-ttu-id="c2104-127">Geben Sie für **Verbindungs Zeichenfolge**die Verbindungs Zeichenfolge an, die der Berichts Server zum Herstellen einer Verbindung mit der Datenquelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2104-127">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="c2104-128">Das folgende Beispiel veranschaulicht eine Verbindungs Zeichenfolge zum Herstellen einer Verbindung mit der- [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] Datenbank:</span><span class="sxs-lookup"><span data-stu-id="c2104-128">The following example illustrates a connection string used to connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<servername>;initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="c2104-129">Wählen Sie für **Verbindung herstellen über**die Option **Anmeldeinformationen, die sicher auf dem Berichtsserver gespeichert sind**aus.</span><span class="sxs-lookup"><span data-stu-id="c2104-129">For **Connect Using**, select **Credentials stored securely in the report server**.</span></span>

7.  <span data-ttu-id="c2104-130">Geben Sie einen Benutzernamen und ein Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="c2104-130">Type a user name and password.</span></span>

    -   <span data-ttu-id="c2104-131">Wenn das Konto ein Windows-Domänen Benutzerkonto ist, geben Sie es im folgenden Format an: \<domain> \\<Konto \> , und wählen Sie dann **beim Herstellen einer Verbindung mit der Datenquelle als Windows-Anmelde Informationen verwenden aus.**</span><span class="sxs-lookup"><span data-stu-id="c2104-131">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>

    -   <span data-ttu-id="c2104-132">Wenn Benutzername und Kennwort Datenbank-Anmeldeinformationen sind, wählen Sie **Beim Herstellen einer Verbindung mit der Datenquelle als Windows-Anmeldeinformationen verwenden**nicht aus.</span><span class="sxs-lookup"><span data-stu-id="c2104-132">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="c2104-133">Wenn der Datenbankserver Identitätswechsel oder Delegierung unterstützt, können Sie die Option **Die Identität des authentifizierten Benutzers annehmen, nachdem eine Verbindung zur Datenquelle hergestellt wurde**auswählen.</span><span class="sxs-lookup"><span data-stu-id="c2104-133">If the database server supports impersonation or delegation, you can select **Impersonate the authenticated user after a connection has been made to the data source**.</span></span>

8.  <span data-ttu-id="c2104-134">Klicken Sie auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="c2104-134">Click **Apply**.</span></span>

     <span data-ttu-id="c2104-135">![Pfeilsymbol mit Rückverweis auf den Seitenanfang](../../2014-toc/media/uparrow16x16.gif "Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird") [Anforderungen an Sicherheitsrichtlinien für gespeicherte Anmeldeinformationen](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="c2104-135">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

##  <a name="configure-stored-credentials-for-a-report-specific-data-source-sharepoint-mode"></a><a name="bkmk_stored_credentials_data_source_sharepoint"></a><span data-ttu-id="c2104-136">Konfigurieren gespeicherter Anmelde Informationen für eine Berichts spezifische Datenquelle (SharePoint-Modus)</span><span class="sxs-lookup"><span data-stu-id="c2104-136">Configure stored credentials for a report-specific data source (SharePoint mode)</span></span>

1.  <span data-ttu-id="c2104-137">Rufen Sie die Dokumentbibliothek mit dem Bericht auf, und klicken Sie anschließend auf das offene Menü ![Kontextmenü der Dokumentbibliothek für SSRS-Elemente](../media/ssrs-sharepoint-item-context-menu.png "Kontextmenü der Dokumentbibliothek für SSRS-Elemente").</span><span class="sxs-lookup"><span data-stu-id="c2104-137">Browse to the document library that contains the report and then click the open menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items").</span></span>

2.  <span data-ttu-id="c2104-138">Klicken Sie erst auf das zweite offene Menü ![Kontextmenü der Dokumentbibliothek für SSRS-Elemente](../media/ssrs-sharepoint-item-context-menu.png "Kontextmenü der Dokumentbibliothek für SSRS-Elemente") und anschließend auf **Datenquellen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="c2104-138">Click second open menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items") and then click **Manage Data Sources**.</span></span>

3.  <span data-ttu-id="c2104-139">Klicken Sie auf den Namen der **benutzerdefinierten** Datenquelle, die Sie mit gespeicherten Anmeldeinformationen konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c2104-139">Click the name of the **Custom** data source you want to configure with stored credentials.</span></span>

4.  <span data-ttu-id="c2104-140">Wählen Sie in der Liste **Datenquellentyp** die Datenverarbeitungserweiterung aus, die zum Verarbeiten von Daten aus der Datenquelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c2104-140">In the **Data Source Type** list, select the data processing extension that is used to process data from the data source.</span></span>

5.  <span data-ttu-id="c2104-141">Geben Sie für **Verbindungs Zeichenfolge**die Verbindungs Zeichenfolge an, die der Berichts Server zum Herstellen einer Verbindung mit der Datenquelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2104-141">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> <span data-ttu-id="c2104-142">Das folgende Beispiel veranschaulicht eine Verbindungs Zeichenfolge zum Herstellen einer Verbindung mit der- [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] Datenbank:</span><span class="sxs-lookup"><span data-stu-id="c2104-142">The following example illustrates a connection string used to connect to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<servername>;initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="c2104-143">Wählen Sie für **Anmelde**Informationen die Option **gespeicherte Anmelde**Informationen aus.</span><span class="sxs-lookup"><span data-stu-id="c2104-143">For **Credentials**, select **Stored Credentials**.</span></span>

7.  <span data-ttu-id="c2104-144">Geben Sie einen **Benutzernamen** und ein **Kennwort**ein.</span><span class="sxs-lookup"><span data-stu-id="c2104-144">Type a **user name** and **password**.</span></span>

    -   <span data-ttu-id="c2104-145">Wenn das Konto ein Windows-Domänen Benutzerkonto ist, geben Sie es im folgenden Format an: \<domain> \\<Konto \> , und wählen Sie dann **beim Herstellen einer Verbindung mit der Datenquelle als Windows-Anmelde Informationen verwenden aus.**</span><span class="sxs-lookup"><span data-stu-id="c2104-145">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>

    -   <span data-ttu-id="c2104-146">Wenn der Benutzername und das Kennwort Datenbankanmeldeinformationen sind, wählen Sie nicht **Als Windows-Anmeldeinformationen verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="c2104-146">If the user name and password are database credentials, do not select **Use as Windows credentials**.</span></span> <span data-ttu-id="c2104-147">Wenn der Datenbankserver Identitätswechsel oder Delegierung unterstützt, wählen Sie ggf. die Option **Ausführungskontext für dieses Konto festlegen**aus.</span><span class="sxs-lookup"><span data-stu-id="c2104-147">If the database server supports impersonation or delegation, you can select **Set execution context to this account**.</span></span>

8.  <span data-ttu-id="c2104-148">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2104-148">Click **ok**.</span></span>

     <span data-ttu-id="c2104-149">![Pfeilsymbol mit Rückverweis auf den Seitenanfang](../../2014-toc/media/uparrow16x16.gif "Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird") [Anforderungen an Sicherheitsrichtlinien für gespeicherte Anmeldeinformationen](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="c2104-149">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

##  <a name="configure-stored-credentials-for-a-shared-data-source-native-mode"></a><a name="bkmk_stored_credentials_shared_data_source_native"></a><span data-ttu-id="c2104-150">Konfigurieren gespeicherter Anmelde Informationen für eine freigegebene Datenquelle (einheitlicher Modus)</span><span class="sxs-lookup"><span data-stu-id="c2104-150">Configure stored credentials for a shared data source (Native mode)</span></span>

1.  <span data-ttu-id="c2104-151">Navigieren Sie im Berichts-Manager im einheitlichen Modus zum freigegebenen Datenquellenelement.</span><span class="sxs-lookup"><span data-stu-id="c2104-151">In Native mode Report Manager, browse to the shared data source item.</span></span> <span data-ttu-id="c2104-152">![Symbol für freigegebene Datenquelle](../media/hlp-16datasource.png "Symbol für freigegebene Datenquelle")</span><span class="sxs-lookup"><span data-stu-id="c2104-152">![Shared data source icon](../media/hlp-16datasource.png "Shared data source icon")</span></span>

2.  <span data-ttu-id="c2104-153">Klicken Sie ![im Berichts-Manager für SSRS-Elemente](../media/ssrs-report-manager-item-context-menu.png "Kontextmenü im Berichts-Manager für SSRS-Elemente") auf das Kontextmenü Kontextmenü, und klicken Sie dann auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="c2104-153">Click the context menu ![context menu in report manager for ssrs items](../media/ssrs-report-manager-item-context-menu.png "context menu in report manager for ssrs items") and then click **Manage**.</span></span>

3.  <span data-ttu-id="c2104-154">Geben Sie in der Liste **Daten Quellentyp** die Datenverarbeitungs Erweiterung an, die zum Verarbeiten von Daten aus der Datenquelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c2104-154">In the **Data Source Type** list, specify the data processing extension that is used to process data from the data source.</span></span>

4.  <span data-ttu-id="c2104-155">Geben Sie für **Verbindungs Zeichenfolge**die Verbindungs Zeichenfolge an, die der Berichts Server zum Herstellen einer Verbindung mit der Datenquelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2104-155">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="c2104-156">empfiehlt, dass Sie keine Anmeldeinformationen in der Verbindungszeichenfolge angeben.</span><span class="sxs-lookup"><span data-stu-id="c2104-156">recommends that you do not specify credentials in the connection string.</span></span>

     <span data-ttu-id="c2104-157">Das folgende Beispiel veranschaulicht eine Verbindungs Zeichenfolge, die zum Herstellen einer Verbindung mit der lokalen Datenbank verwendet wird [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="c2104-157">The following example illustrates a connection string used to connect to the local [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<localservername>; initial catalog=AdventureWorks2012
    ```

5.  <span data-ttu-id="c2104-158">Geben Sie einen Benutzernamen und ein Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="c2104-158">Type a user name and password.</span></span>

    -   <span data-ttu-id="c2104-159">Wenn das Konto ein Windows-Domänen Benutzerkonto ist, geben Sie es im folgenden Format an: \<domain> \\<Konto \> , und wählen Sie dann **beim Herstellen einer Verbindung mit der Datenquelle als Windows-Anmelde Informationen verwenden aus.**</span><span class="sxs-lookup"><span data-stu-id="c2104-159">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>

    -   <span data-ttu-id="c2104-160">Wenn Benutzername und Kennwort Datenbank-Anmeldeinformationen sind, wählen Sie **Beim Herstellen einer Verbindung mit der Datenquelle als Windows-Anmeldeinformationen verwenden**nicht aus.</span><span class="sxs-lookup"><span data-stu-id="c2104-160">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="c2104-161">Wenn der Datenbankserver Identitätswechsel oder Delegierung unterstützt, können Sie die Option **Die Identität des authentifizierten Benutzers annehmen, nachdem eine Verbindung zur Datenquelle hergestellt wurde**auswählen.</span><span class="sxs-lookup"><span data-stu-id="c2104-161">If the database server supports impersonation or delegation, you can select **Impersonate the authenticated user after a connection has been made to the data source**.</span></span>

6.  <span data-ttu-id="c2104-162">Klicken Sie auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="c2104-162">Click **Apply**.</span></span>

     <span data-ttu-id="c2104-163">![Pfeilsymbol mit Rückverweis auf den Seitenanfang](../../2014-toc/media/uparrow16x16.gif "Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird") [Anforderungen an Sicherheitsrichtlinien für gespeicherte Anmeldeinformationen](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="c2104-163">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

##  <a name="configure-stored-credentials-for-a-shared-data-source-sharepoint-mode"></a><a name="bkmk_stored_credentials_shared_data_source_sharepoint"></a><span data-ttu-id="c2104-164">Konfigurieren gespeicherter Anmelde Informationen für eine freigegebene Datenquelle (SharePoint-Modus)</span><span class="sxs-lookup"><span data-stu-id="c2104-164">Configure stored credentials for a shared data source (SharePoint mode)</span></span>

1.  <span data-ttu-id="c2104-165">Rufen Sie in der Dokumentbibliothek das freigegebene Datenquellelement auf. ![Freigegebenes Datenquellsymbol](../media/hlp-16datasource.png "Symbol für freigegebene Datenquelle")</span><span class="sxs-lookup"><span data-stu-id="c2104-165">In the document library, browse to the shared data source item.![Shared data source icon](../media/hlp-16datasource.png "Shared data source icon")</span></span>

2.  <span data-ttu-id="c2104-166">Klicken Sie erst auf das zweite offene Menü ![Kontextmenü der Dokumentbibliothek für SSRS-Elemente](../media/ssrs-sharepoint-item-context-menu.png "Kontextmenü der Dokumentbibliothek für SSRS-Elemente") und anschließend auf ![Datenquellen verwalten](../media/ssrs-sharepoint-item-context-menu.png "Kontextmenü der Dokumentbibliothek für SSRS-Elemente").</span><span class="sxs-lookup"><span data-stu-id="c2104-166">Click the context menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items") and then click the second context menu ![document library context menu for ssrs items](../media/ssrs-sharepoint-item-context-menu.png "document library context menu for ssrs items").</span></span>

3.  <span data-ttu-id="c2104-167">Klicken Sie auf **Datenquellendefinition bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c2104-167">Click **Edit Data Source Definition**.</span></span>

4.  <span data-ttu-id="c2104-168">Geben Sie in der Liste **Daten Quellentyp** die Datenverarbeitungs Erweiterung an, die zum Verarbeiten von Daten aus der Datenquelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c2104-168">In the **Data Source Type** list, specify the data processing extension that is used to process data from the data source.</span></span>

5.  <span data-ttu-id="c2104-169">Geben Sie für **Verbindungs Zeichenfolge**die Verbindungs Zeichenfolge an, die der Berichts Server zum Herstellen einer Verbindung mit der Datenquelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2104-169">For **Connection String**, specify the connection string that the report server uses to connect to the data source.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="c2104-170">empfiehlt, dass Sie keine Anmeldeinformationen in der Verbindungszeichenfolge angeben.</span><span class="sxs-lookup"><span data-stu-id="c2104-170">recommends that you do not specify credentials in the connection string.</span></span>

     <span data-ttu-id="c2104-171">Das folgende Beispiel veranschaulicht eine Verbindungs Zeichenfolge, die zum Herstellen einer Verbindung mit der lokalen Datenbank verwendet wird [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="c2104-171">The following example illustrates a connection string used to connect to the local [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database:</span></span>

    ```
    data source=<localservername>; initial catalog=AdventureWorks2012
    ```

6.  <span data-ttu-id="c2104-172">Geben Sie einen Benutzernamen und ein Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="c2104-172">Type a user name and password.</span></span>

    -   <span data-ttu-id="c2104-173">Wenn das Konto ein Windows-Domänen Benutzerkonto ist, geben Sie es im folgenden Format an: \<domain> \\<Konto \> , und wählen Sie dann **als Windows-Anmelde Informationen verwenden aus.**</span><span class="sxs-lookup"><span data-stu-id="c2104-173">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials.**</span></span>

    -   <span data-ttu-id="c2104-174">Wenn der Benutzername und das Kennwort Datenbankanmeldeinformationen sind, wählen Sie nicht **Als Windows-Anmeldeinformationen verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="c2104-174">If the user name and password are database credentials, do not select **Use as Windows credentials**.</span></span> <span data-ttu-id="c2104-175">Wenn der Datenbankserver Identitätswechsel oder Delegierung unterstützt, können Sie die Option **Ausführungs Kontext für dieses Konto festlegen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="c2104-175">If the database server supports impersonation or delegation, you can select **Set Execution context to this account**.</span></span>

7.  <span data-ttu-id="c2104-176">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c2104-176">Click **Ok**.</span></span>

     <span data-ttu-id="c2104-177">![Pfeilsymbol mit Rückverweis auf den Seitenanfang](../../2014-toc/media/uparrow16x16.gif "Pfeilsymbol, das mit dem Link „Zurück zum Anfang“ verwendet wird") [Anforderungen an Sicherheitsrichtlinien für gespeicherte Anmeldeinformationen](#bkmk_top)</span><span class="sxs-lookup"><span data-stu-id="c2104-177">![Arrow icon used with Back to Top link](../../2014-toc/media/uparrow16x16.gif "Arrow icon used with Back to Top link") [Security policy requirements for stored credentials](#bkmk_top)</span></span>

## <a name="see-also"></a><span data-ttu-id="c2104-178">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c2104-178">See Also</span></span>
 <span data-ttu-id="c2104-179">[Angeben von Anmelde Informationen und Verbindungsinformationen für Berichtsdaten Quellen](../../integration-services/connection-manager/data-sources.md) [Konfigurieren von Datenquellen Eigenschaften für einen Bericht &#40;Berichts-Manager&#41;](configure-data-source-properties-for-a-report-report-manager.md) [erstellen, löschen oder Ändern einer freigegebenen Datenquelle &#40;Berichts-Manager&#41;&#40;](../create-delete-or-modify-a-shared-data-source-report-manager.md) [Datenquellen Eigenschaften Seite](../data-sources-properties-page-report-manager.md) Berichts-Manager&#41;&#40;[Seite neue Datenquelle](../new-data-source-page-report-manager.md) Berichts-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="c2104-179">[Specify Credential and Connection Information for Report Data Sources](../../integration-services/connection-manager/data-sources.md) [Configure Data Source Properties for a Report  &#40;Report Manager&#41;](configure-data-source-properties-for-a-report-report-manager.md) [Create, Delete, or Modify a Shared Data Source &#40;Report Manager&#41;](../create-delete-or-modify-a-shared-data-source-report-manager.md) [Data Sources Properties Page &#40;Report Manager&#41;](../data-sources-properties-page-report-manager.md) [New Data Source Page &#40;Report Manager&#41;](../new-data-source-page-report-manager.md)</span></span>


