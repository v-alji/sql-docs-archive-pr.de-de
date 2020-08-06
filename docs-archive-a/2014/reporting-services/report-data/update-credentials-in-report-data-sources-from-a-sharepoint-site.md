---
title: Aktualisieren von Anmeldeinformationen in Berichtsdatenquellen von einer SharePoint-Website | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e0c50b6e-89e7-4b4d-8fe5-c90682c5d1b1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 923fee5656ed6032201fb4276fcca75be799e42d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608311"
---
# <a name="update-credentials-in-report-data-sources-from-a-sharepoint-site"></a><span data-ttu-id="f0c17-102">Aktualisieren von Anmeldeinformationen in Berichtsdatenquellen von einer SharePoint-Website</span><span class="sxs-lookup"><span data-stu-id="f0c17-102">Update Credentials in Report Data Sources from a SharePoint Site</span></span>
  <span data-ttu-id="f0c17-103">In diesem Thema wird beschrieben, wie sich in Berichte eingebettete Datenquellen und freigegebene Datenquellen, die in einer SharePoint-Dokumentbibliothek gespeichert sind, aktualisieren lassen.</span><span class="sxs-lookup"><span data-stu-id="f0c17-103">This topic describes how to update data sources embedded in reports and shared data sources that are saved in a SharePoint document library.</span></span>  
  
 <span data-ttu-id="f0c17-104">Viele der Berichte können Datenquellen beinhalten oder freigegebene Datenquellen verwenden, die zur Verwendung der Windows-Authentifizierung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="f0c17-104">Many of your reports might include data sources or use shared data sources that are configured to use Windows Authentication.</span></span> <span data-ttu-id="f0c17-105">In einigen Fällen wie bei der Erstellung von Datenwarnungen für in einer SharePoint-Dokumentbibliothek gespeicherte Berichte müssen Sie die Anmeldeinformationen der Datenquelle auf gespeicherte Anmeldeinformationen aktualisieren. Verlangen Sie alternativ keine Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="f0c17-105">Under some circumstances, such as creating data alerts on reports saved to a SharePoint document library, you need to update the data source credentials to stored credentials or require no credentials.</span></span>  
  
 <span data-ttu-id="f0c17-106">Um gespeicherte Anmeldeinformationen in Berichten zu verwenden, erstellen und verwenden Sie ggf. eine neue SQL Server-Anmeldung.</span><span class="sxs-lookup"><span data-stu-id="f0c17-106">To use stored credentials in reports, you might decide to create and use a new SQL Server login.</span></span> <span data-ttu-id="f0c17-107">Weitere Informationen finden Sie unter [Erstellen eines Anmeldenamens](../../relational-databases/security/authentication-access/create-a-login.md).</span><span class="sxs-lookup"><span data-stu-id="f0c17-107">For more information, see [Create a Login](../../relational-databases/security/authentication-access/create-a-login.md).</span></span>  
  
### <a name="to-update-an-embedded-data-source-to-use-stored-credentials"></a><span data-ttu-id="f0c17-108">So aktualisieren Sie eine eingebettete Datenquelle zur Verwendung von gespeicherten Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="f0c17-108">To update an embedded data source to use stored credentials</span></span>  
  
1.  <span data-ttu-id="f0c17-109">Wechseln Sie zur SharePoint-Dokumentbibliothek, in der Sie den Bericht gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="f0c17-109">Go to the SharePoint document library where you saved the report.</span></span>  
  
2.  <span data-ttu-id="f0c17-110">Klicken Sie für den Bericht auf das Symbol des Dropdownmenüs zum Erweitern, und klicken Sie dann auf **Datenquellen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="f0c17-110">Click the icon for the expand drop-down menu on the report and then click **Manage Data Sources**.</span></span>  
  
     <span data-ttu-id="f0c17-111">Die Seite "Datenquellen verwalten" wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f0c17-111">The Manage Data Sources page opens.</span></span>  
  
3.  <span data-ttu-id="f0c17-112">Klicken Sie in der Spalte **Name** auf die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="f0c17-112">In the **Name** column, click the data source.</span></span>  
  
4.  <span data-ttu-id="f0c17-113">Überprüfen Sie für **Verbindungstyp** , ob die Option **Benutzerdefinierte Datenquelle** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f0c17-113">For **Connection Type** verify that the **Custom data source** option is selected.</span></span>  
  
     <span data-ttu-id="f0c17-114">Diese Option gibt an, dass die Datenquelle in den Bericht eingebettet ist.</span><span class="sxs-lookup"><span data-stu-id="f0c17-114">This option indicates that the data source is embedded in the report.</span></span>  
  
5.  <span data-ttu-id="f0c17-115">Lassen Sie die Optionen **Datenquellentyp** und **Verbindungszeichenfolge** unverändert, sofern für den Bericht keine Verbindung zu einer anderen Datenquelle, einem anderen Server oder einem anderen Datenspeicher hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f0c17-115">Leave the **Data Source Type** and **Connection string** options as they are, unless you want the report to connect to different type of data source, a different server, or data store.</span></span>  
  
6.  <span data-ttu-id="f0c17-116">Wählen Sie für **Anmeldeinformationen**die Option **Gespeicherte Anmeldeinformationen**aus.</span><span class="sxs-lookup"><span data-stu-id="f0c17-116">For **Credentials**, select **Stored credentials**.</span></span> <span data-ttu-id="f0c17-117">Diese Option kann nur verwendet werden, wenn die Datenquelle keine Anmeldeinformationen annimmt oder wenn Sie Anmeldeinformationen anderweitig übergeben.</span><span class="sxs-lookup"><span data-stu-id="f0c17-117">This option works only if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
     <span data-ttu-id="f0c17-118">Die Option **Anmeldeinformationen sind nicht erforderlich** kann auch in einigen Fällen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0c17-118">The **Credentials are not required** option can also be used under some circumstances.</span></span>  
  
     <span data-ttu-id="f0c17-119">Bei einigen Datenquellentypen muss das Konto mit unbeaufsichtigter Ausführung auf dem Berichtsserver konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f0c17-119">From some data source types, the unattended execution account must be configured on the report server.</span></span> <span data-ttu-id="f0c17-120">Weitere Informationen finden Sie im Thema für den entsprechenden Datenquellentyp in [Hinzufügen von Daten aus externen Datenquellen (SSRS)](add-data-from-external-data-sources-ssrs.md) und [Konfigurieren des unbeaufsichtigten Ausführungskontos (SSRS-Konfigurations-Manager)](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f0c17-120">For more information, see the topic for the corresponding data source type in [Add Data from External Data Sources &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) and [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
7.  <span data-ttu-id="f0c17-121">Geben Sie einen Benutzernamen und ein Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="f0c17-121">Type a user name and password.</span></span>  
  
    -   <span data-ttu-id="f0c17-122">Wenn das Konto ein Windows-Domänen Benutzerkonto ist, geben Sie es im folgenden Format an: \<domain> \\<Konto \> , und wählen Sie dann **beim Herstellen einer Verbindung mit der Datenquelle als Windows-Anmelde Informationen verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="f0c17-122">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source**.</span></span>  
  
    -   <span data-ttu-id="f0c17-123">Wenn Benutzername und Kennwort Datenbank-Anmeldeinformationen sind, wählen Sie **Beim Herstellen einer Verbindung mit der Datenquelle als Windows-Anmeldeinformationen verwenden**nicht aus.</span><span class="sxs-lookup"><span data-stu-id="f0c17-123">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="f0c17-124">Wenn der Datenbankserver Identitätswechsel oder Delegierung unterstützt, wählen Sie ggf. die Option **Ausführungskontext für dieses Konto festlegen**aus.</span><span class="sxs-lookup"><span data-stu-id="f0c17-124">If the database server supports impersonation or delegation, you can select **Set execution context to this account**.</span></span>  
  
8.  <span data-ttu-id="f0c17-125">Klicken Sie zum Überprüfen, ob mit den aktualisierten Anmeldeinformationen für die Datenquelle eine Verbindung hergestellt werden kann, auf **Verbindung testen**.</span><span class="sxs-lookup"><span data-stu-id="f0c17-125">To verify the data source can connect by using the updated credentials, click **Test connection**.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-update-a-shared-data-source-to-use-stored-credentials"></a><span data-ttu-id="f0c17-126">So aktualisieren Sie eine freigegebene Datenquelle zur Verwendung von gespeicherten Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="f0c17-126">To update a shared data source to use stored credentials</span></span>  
  
1.  <span data-ttu-id="f0c17-127">Wechseln Sie zur SharePoint-Dokumentbibliothek, in der Sie die freigegebene Datenquelle gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="f0c17-127">Go to the SharePoint document library where you saved the shared data source.</span></span>  
  
2.  <span data-ttu-id="f0c17-128">Klicken Sie für die freigegebene Datenquelle auf das Symbol des Dropdownmenüs zum Erweitern, und klicken Sie dann auf **Datenquellendefinition bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f0c17-128">Click the icon for the expand drop-down menu on shared data source, and then click **Edit Data Source Definition**.</span></span>  
  
     <span data-ttu-id="f0c17-129">Die Seite "Datenquelle" wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="f0c17-129">The Data Source page opens.</span></span>  
  
3.  <span data-ttu-id="f0c17-130">Lassen Sie die Optionen **Datenquellentyp** und **Verbindungszeichenfolge** unverändert, sofern für die freigegebene Datenquelle keine Verbindung zu einer anderen Datenquelle, einem anderen Server oder einem anderen Datenspeicher hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f0c17-130">Leave the **Data Source Type** and **Connection string** options as they are, unless you want the shared data source to connect to different type of data source, a different server, or data store.</span></span>  
  
4.  <span data-ttu-id="f0c17-131">Wählen Sie für **Anmeldeinformationen**die Option **Gespeicherte Anmeldeinformationen**aus.</span><span class="sxs-lookup"><span data-stu-id="f0c17-131">For **Credentials**, select **Stored credentials**.</span></span>  
  
     <span data-ttu-id="f0c17-132">Die Option **Anmeldeinformationen sind nicht erforderlich** kann auch in einigen Fällen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f0c17-132">The **Credentials are not required** option can also be used under some circumstances.</span></span> <span data-ttu-id="f0c17-133">Diese Option kann nur verwendet werden, wenn die Datenquelle keine Anmeldeinformationen annimmt oder wenn Sie Anmeldeinformationen anderweitig übergeben.</span><span class="sxs-lookup"><span data-stu-id="f0c17-133">This option works only if the data source does not accept credentials or if you are passing credentials some other way.</span></span>  
  
     <span data-ttu-id="f0c17-134">Bei einigen Datenquellentypen muss das Konto mit unbeaufsichtigter Ausführung auf dem Berichtsserver konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="f0c17-134">From some data source types, the unattended execution account must be configured on the report server.</span></span> <span data-ttu-id="f0c17-135">Weitere Informationen finden Sie im Thema für den entsprechenden Datenquellentyp in [Hinzufügen von Daten aus externen Datenquellen (SSRS)](add-data-from-external-data-sources-ssrs.md) und [Konfigurieren des unbeaufsichtigten Ausführungskontos (SSRS-Konfigurations-Manager)](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span><span class="sxs-lookup"><span data-stu-id="f0c17-135">For more information, see the topic for the corresponding data source type in [Add Data from External Data Sources &#40;SSRS&#41;](add-data-from-external-data-sources-ssrs.md) and [Configure the Unattended Execution Account &#40;SSRS Configuration Manager&#41;](../install-windows/configure-the-unattended-execution-account-ssrs-configuration-manager.md).</span></span>  
  
5.  <span data-ttu-id="f0c17-136">Geben Sie einen Benutzernamen und ein Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="f0c17-136">Type a user name and password.</span></span>  
  
    -   <span data-ttu-id="f0c17-137">Wenn das Konto ein Windows-Domänen Benutzerkonto ist, geben Sie es im folgenden Format an: \<domain> \\<Konto \> , und wählen Sie dann **beim Herstellen einer Verbindung mit der Datenquelle als Windows-Anmelde Informationen verwenden aus.**</span><span class="sxs-lookup"><span data-stu-id="f0c17-137">If the account is a Windows domain user account, specify it in this format: \<domain>\\<account\>, and then select **Use as Windows credentials when connecting to the data source.**</span></span>  
  
    -   <span data-ttu-id="f0c17-138">Wenn Benutzername und Kennwort Datenbank-Anmeldeinformationen sind, wählen Sie **Beim Herstellen einer Verbindung mit der Datenquelle als Windows-Anmeldeinformationen verwenden**nicht aus.</span><span class="sxs-lookup"><span data-stu-id="f0c17-138">If the user name and password are database credentials, do not select **Use as Windows credentials when connecting to the data source**.</span></span> <span data-ttu-id="f0c17-139">Wenn der Datenbankserver Identitätswechsel oder Delegierung unterstützt, wählen Sie ggf. die Option **Ausführungskontext für dieses Konto festlegen**aus.</span><span class="sxs-lookup"><span data-stu-id="f0c17-139">If the database server supports impersonation or delegation, you can select **Set execution context to this account**.</span></span>  
  
6.  <span data-ttu-id="f0c17-140">Klicken Sie zum Überprüfen, ob mit den aktualisierten Anmeldeinformationen für die Datenquelle eine Verbindung hergestellt werden kann, auf **Verbindung testen**.</span><span class="sxs-lookup"><span data-stu-id="f0c17-140">To verify the data source can connect using the updated credentials, **Test connection**.</span></span>  
  
7.  <span data-ttu-id="f0c17-141">Stellen Sie sicher, dass die Option "Diese Datenquelle aktivieren" aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f0c17-141">Verify that Enable this data source is selected.</span></span>  
  
8.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f0c17-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0c17-142">See Also</span></span>  
 [<span data-ttu-id="f0c17-143">Hochladen von Dokumenten in eine SharePoint-Bibliothek &#40;Reporting Services im SharePoint-Modus&#41;</span><span class="sxs-lookup"><span data-stu-id="f0c17-143">Upload Documents to a SharePoint Library &#40;Reporting Services in SharePoint Mode&#41;</span></span>](../upload-documents-to-a-sharepoint-library-reporting-services-in-sharepoint-mode.md)  
  
  
