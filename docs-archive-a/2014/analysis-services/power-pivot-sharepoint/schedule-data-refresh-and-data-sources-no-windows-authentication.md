---
title: Planen der Datenaktualisierung und Datenquellen, die die Windows-Authentifizierung nicht unterstützen (PowerPivot für SharePoint) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d8d875bc-7823-46b7-a939-867cefd4de12
author: minewiskan
ms.author: owend
ms.openlocfilehash: 63e37dec6f334395c0c1812c6f76d750c16c53ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618319"
---
# <a name="schedule-data-refresh-and-data-sources-that-do-not-support-windows-authentication-powerpivot-for-sharepoint"></a><span data-ttu-id="885be-102">Planen der Datenaktualisierung mit Datenquellen, die die Windows-Authentifizierung nicht unterstützen (PowerPivot für SharePoint)</span><span class="sxs-lookup"><span data-stu-id="885be-102">Schedule Data Refresh and Data Sources That Do Not Support Windows Authentication (PowerPivot for SharePoint)</span></span>
  <span data-ttu-id="885be-103">In diesem Thema wird ein Workflow für eine planmäßige Datenaktualisierung in PowerPivot für SharePoint beschrieben. Dabei können Datenquellen verwendet werden, die die Windows-Authentifizierung **NICHT** unterstützen,</span><span class="sxs-lookup"><span data-stu-id="885be-103">This topic describes a workflow of PowerPivot for SharePoint schedule data fresh that can use data sources that do **NOT** support Windows Authentication.</span></span> <span data-ttu-id="885be-104">z. B. Oracle- oder IDM DB2-Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="885be-104">For example Oracle or IDM DB2 data sources.</span></span> <span data-ttu-id="885be-105">Obwohl sich die Abbildungen und Schritte in diesem Thema auf Oracle-Datenquellen beziehen, gilt der gleiche Workflow auch für andere Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="885be-105">The illustrations and steps in this topic reference Oracle data sources but the same workflow applies to other data sources.</span></span>  
  
||  
|-|  
|<span data-ttu-id="885be-106">**[!INCLUDE[applies](../../includes/applies-md.md)]** SharePoint 2010 &#124; SharePoint 2013.</span><span class="sxs-lookup"><span data-stu-id="885be-106">**[!INCLUDE[applies](../../includes/applies-md.md)]**  SharePoint 2010 &#124; SharePoint 2013.</span></span>|  
  
 <span data-ttu-id="885be-107">**Übersicht:** Erstellen Sie zwei Secure Store-Zielanwendungen.</span><span class="sxs-lookup"><span data-stu-id="885be-107">**Overview:** Create two Secure Store Target Applications.</span></span> <span data-ttu-id="885be-108">Konfigurieren Sie die erste Zielanwendung (PowerPivotDataRefresh) für die Verwendung von Windows-Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="885be-108">Configure the first target application (PowerPivotDataRefresh) to use Windows credentials.</span></span> <span data-ttu-id="885be-109">Konfigurieren Sie die zweite Zielanwendung mit den Anmeldeinformationen einer Datenquelle, die keine Windows-Authentifizierung unterstützt, z. B. eine Oracle-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="885be-109">Configure the second target application with the credentials for a data source that does not support windows authentication, for example, an Oracle database.</span></span> <span data-ttu-id="885be-110">Darüber hinaus wird die erste Zielanwendung von der zweiten Zielanwendung für das unbeaufsichtigte Datenaktualisierungskonto verwendet.</span><span class="sxs-lookup"><span data-stu-id="885be-110">The second target application also uses the first target application for the unattended data refresh account.</span></span>  
  
 <span data-ttu-id="885be-111">![as_powerpivot_refresh_no_windows_auth](../media/as-powerpivot-refresh-no-windows-auth.gif "as_powerpivot_refresh_no_windows_auth")</span><span class="sxs-lookup"><span data-stu-id="885be-111">![as_powerpivot_refresh_no_windows_auth](../media/as-powerpivot-refresh-no-windows-auth.gif "as_powerpivot_refresh_no_windows_auth")</span></span>  
  
-   <span data-ttu-id="885be-112">**(1) PowerPivotDatarefresh:** Eine Secure Store-Zielanwendungs-ID, für die im SET-Befehl die Windows-Authentifizierung angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="885be-112">**(1) PowerPivotDatarefresh:** A Secure Store Target Application ID that is set with windows authentication.</span></span>  
  
-   <span data-ttu-id="885be-113">**(2) OracleAuthentication:** Eine Secure Store-Zielanwendungs-ID, für die im SET-Befehl Oracle-Anmeldeinformationen angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="885be-113">**(2) OracleAuthentication:** A Secure Store Target Application ID that is set with Oracle credentials.</span></span>  
  
-   <span data-ttu-id="885be-114">**(3)** die Power Pivot-Dienst Anwendung wird so konfiguriert, dass Sie die Zielanwendung "powerpivotdatarefresh" für das **unbeaufsichtigte Daten Aktualisierungs Konto**verwendet.</span><span class="sxs-lookup"><span data-stu-id="885be-114">**(3)** The PowerPivot Service application is configure to use the target application "PowerPivotDataRefresh" for the **Unattended Data Refresh Account**.</span></span>  
  
-   <span data-ttu-id="885be-115">**(4)** Die PowerPivot-Arbeitsmappe verwendet Oracle-Daten.</span><span class="sxs-lookup"><span data-stu-id="885be-115">**(4)** PowerePivot Workbook uses Oracle data.</span></span> <span data-ttu-id="885be-116">In den Aktualisierungseinstellungen der Arbeitsmappe ist angegeben, dass die Anmeldeinformationen von Zielanwendung **(2)** für die Datenquellenverbindung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="885be-116">The workbook refresh settings specify the data source connection to use the target application **(2)** for credentials.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="885be-117">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="885be-117">Prerequisites</span></span>  
  
-   <span data-ttu-id="885be-118">Eine PowerPivot-Dienstanwendung ist vorhanden.</span><span class="sxs-lookup"><span data-stu-id="885be-118">A PowerPivot Service Application exists.</span></span>  
  
-   <span data-ttu-id="885be-119">Eine Secure Store Service-Anwendung ist vorhanden.</span><span class="sxs-lookup"><span data-stu-id="885be-119">A Secure Store Service Application exists.</span></span>  
  
-   <span data-ttu-id="885be-120">Eine Excel-Arbeitsmappe mit einem PowerPivot-Datenmodell ist vorhanden.</span><span class="sxs-lookup"><span data-stu-id="885be-120">An Excel workbook with a PowerPivot data model exists.</span></span>  
  
## <a name="to-create-a-target-application-id-that-uses-windows-authentication"></a><span data-ttu-id="885be-121">So erstellen Sie eine Zielanwendungs-ID, die die Windows-Authentifizierung verwendet</span><span class="sxs-lookup"><span data-stu-id="885be-121">To Create a Target Application ID that uses Windows Authentication</span></span>  
  
1.  <span data-ttu-id="885be-122">Klicken Sie in der SharePoint-zentral Administration auf **Dienst Anwendungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="885be-122">In SharePoint Central administration, click **Manage Service Applications**.</span></span>  
  
2.  <span data-ttu-id="885be-123">Klicken Sie auf den Namen der Secure Store Service-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="885be-123">Click the name of your secure store service application.</span></span>  
  
3.  <span data-ttu-id="885be-124">Klicken Sie auf der Seite **Verwalten** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="885be-124">On the **Manage** page, click **New**.</span></span> <span data-ttu-id="885be-125">![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application")</span><span class="sxs-lookup"><span data-stu-id="885be-125">![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application")</span></span>  
  
4.  <span data-ttu-id="885be-126">Konfigurieren Sie auf der Seite **Neue Zielanwendung für einmaliges Anmelden erstellen** die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="885be-126">On the **Create New Secure Store Target Application** page, configure the following values:</span></span>  
  
    -   <span data-ttu-id="885be-127">**Zielanwendungs-ID:** PowerPivotDataRefresh</span><span class="sxs-lookup"><span data-stu-id="885be-127">**Target Application ID:** PowerPivotDataRefresh.</span></span>  
  
    -   <span data-ttu-id="885be-128">**Anzeigename:** PowerPivotDataRefresh</span><span class="sxs-lookup"><span data-stu-id="885be-128">**Display Name:** PowerPivotDataRefresh.</span></span>  
  
    -   <span data-ttu-id="885be-129">**Kontakt-E-Mail:** ?</span><span class="sxs-lookup"><span data-stu-id="885be-129">**Contact E-mail:** ?</span></span>  
  
    -   <span data-ttu-id="885be-130">**Zielanwendungstyp:** Gruppe</span><span class="sxs-lookup"><span data-stu-id="885be-130">**Target Application Type:** Group.</span></span>  
  
    -   <span data-ttu-id="885be-131">**Seiten-URL der Zielanwendung:** Keine</span><span class="sxs-lookup"><span data-stu-id="885be-131">**Target Application Page URL:** None.</span></span>  
  
5.  <span data-ttu-id="885be-132">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="885be-132">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="885be-133">Übernehmen Sie auf der Seite „Anmeldeinformationen“ die beiden Standardfeldnamen und -typen **Windows-Benutzername** und **Windows-Kennwort**.</span><span class="sxs-lookup"><span data-stu-id="885be-133">On the Credentials page, leave the two default field names and field types for **Windows User Name** and **Windows Password**.</span></span>  
  
7.  <span data-ttu-id="885be-134">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="885be-134">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="885be-135">Fügen Sie auf der Seite **Mitgliedschaftseinstellungen** mindestens einen **Zielanwendungs-Administrator** und anschließend Mitglieder hinzu, die Zugriff auf die Zielanwendung benötigen.</span><span class="sxs-lookup"><span data-stu-id="885be-135">On the **Membership Settings** page, add at least one **Target Application Administrator** and then add members that need access to the target application.</span></span>  
  
9. <span data-ttu-id="885be-136">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="885be-136">Click **OK**.</span></span>  
  
10. <span data-ttu-id="885be-137">Die neue Zielanwendungs-ID wird der Liste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="885be-137">The new Target Application ID is added to the list.</span></span> <span data-ttu-id="885be-138">Wählen Sie die Zielanwendungs-ID aus, und klicken Sie auf **Anmelde**Informationen![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key")</span><span class="sxs-lookup"><span data-stu-id="885be-138">Select the Target application ID and click **Set Credentials**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span></span>  
  
11. <span data-ttu-id="885be-139">Geben Sie den Windows-Benutzernamen und das Windows-Kennwort ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="885be-139">Type the Windows User Name and Windows Password and then click **OK**.</span></span>  
  
## <a name="to-create-a-target-application-id-that-uses-oracle-credentials"></a><span data-ttu-id="885be-140">So erstellen Sie eine Zielanwendungs-ID, die Oracle-Anmeldeinformationen verwendet</span><span class="sxs-lookup"><span data-stu-id="885be-140">To Create a Target Application ID that uses Oracle credentials</span></span>  
  
1.  <span data-ttu-id="885be-141">Klicken Sie in der SharePoint-zentral Administration auf **Dienst Anwendungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="885be-141">In SharePoint Central administration, click **Manage Service Applications**.</span></span>  
  
2.  <span data-ttu-id="885be-142">Klicken Sie auf den Namen der Secure Store Service-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="885be-142">Click the name of your Secure Store Service application.</span></span>  
  
3.  <span data-ttu-id="885be-143">Klicken Sie auf der Seite **Verwalten** auf **neu**![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application").</span><span class="sxs-lookup"><span data-stu-id="885be-143">On the **Manage** page, click **New**![as_powerpivot_refresh_sss_new_target_application](../media/as-powerpivot-refresh-sss-new-target-application.gif "as_powerpivot_refresh_sss_new_target_application").</span></span>  
  
4.  <span data-ttu-id="885be-144">Konfigurieren Sie auf der Seite **Neue Zielanwendung für einmaliges Anmelden erstellen** die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="885be-144">On the **Create New Secure Store Target Application** page, configure the following values:</span></span>  
  
    -   <span data-ttu-id="885be-145">**Zielanwendungs-ID:** OracleAuthentication</span><span class="sxs-lookup"><span data-stu-id="885be-145">**Target Application ID:** OracleAuthentication.</span></span>  
  
    -   <span data-ttu-id="885be-146">**Anzeigename:** OracleAuthentication</span><span class="sxs-lookup"><span data-stu-id="885be-146">**Display Name:** OracleAuthentication.</span></span>  
  
    -   <span data-ttu-id="885be-147">**Kontakt-E-Mail:** ?</span><span class="sxs-lookup"><span data-stu-id="885be-147">**Contact E-mail:** ?</span></span>  
  
    -   <span data-ttu-id="885be-148">**Zielanwendungstyp:** Gruppe</span><span class="sxs-lookup"><span data-stu-id="885be-148">**Target Application Type:** Group.</span></span>  
  
    -   <span data-ttu-id="885be-149">**Seiten-URL der Zielanwendung:** Keine</span><span class="sxs-lookup"><span data-stu-id="885be-149">**Target Application Page URL:** None.</span></span>  
  
5.  <span data-ttu-id="885be-150">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="885be-150">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="885be-151">Ändern Sie auf der Seite **Anmelde** Informationen den ersten Feldnamen in, `Oracle User ID` und ändern Sie den **Feldtyp** in `User Name` .</span><span class="sxs-lookup"><span data-stu-id="885be-151">On the **Credentials** page, change the first field name to `Oracle User ID` and change the **Field Type** to `User Name`.</span></span>  
  
     <span data-ttu-id="885be-152">Ändern Sie den zweiten Feldnamen in `Oracle Password` und den **Feldtyp** in `Password` .</span><span class="sxs-lookup"><span data-stu-id="885be-152">Change the second field name to `Oracle Password` and the **Field Type** to `Password`.</span></span>  
  
7.  <span data-ttu-id="885be-153">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="885be-153">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="885be-154">Fügen Sie auf der Seite **Mitgliedschaftseinstellungen** mindestens einen **Zielanwendungs-Administrator** und anschließend Mitglieder hinzu, die Zugriff auf die Zielanwendung benötigen.</span><span class="sxs-lookup"><span data-stu-id="885be-154">On the **Membership Settings** page, add at least one **Target Application Administrator** and then add members that need access to the target application.</span></span>  
  
9. <span data-ttu-id="885be-155">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="885be-155">Click **OK**.</span></span>  
  
10. <span data-ttu-id="885be-156">Die neue Zielanwendungs-ID wird der Liste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="885be-156">The new Target Application ID is added to the list.</span></span> <span data-ttu-id="885be-157">Wählen Sie die Zielanwendungs-ID aus, und klicken Sie auf **Anmelde**Informationen![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key")</span><span class="sxs-lookup"><span data-stu-id="885be-157">Select the Target application ID and click **Set Credentials**![as_powerpivot_refresh_sss_set_key](../media/as-powerpivot-refresh-sss-set-key.gif "as_powerpivot_refresh_sss_set_key").</span></span>  
  
11. <span data-ttu-id="885be-158">Geben Sie die Oracle-Benutzer-ID und das Oracle-Kennwort ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="885be-158">Type the Oracle User ID and Oracle Password and then click **OK**.</span></span>  
  
 <span data-ttu-id="885be-159">Weitere Informationen finden Sie im Abschnitt "So erstellen Sie eine Zielanwendung für SQL Server Authentifizierung" in [Verwenden von Secure Store mit SQL Server Authentifizierung (SharePoint Server 2013)](https://technet.microsoft.com/library/gg298949.aspx) ( https://technet.microsoft.com/library/gg298949.aspx) .</span><span class="sxs-lookup"><span data-stu-id="885be-159">For more information, see section "To Create a target application for SQL Server Authentication" in [Use Secure Store with SQL Server Authentication (SharePoint Server 2013)](https://technet.microsoft.com/library/gg298949.aspx) (https://technet.microsoft.com/library/gg298949.aspx).</span></span>  
  
## <a name="to-configure-the-powerpivot-service-application"></a><span data-ttu-id="885be-160">So konfigurieren Sie die PowerPivot-Dienstanwendung</span><span class="sxs-lookup"><span data-stu-id="885be-160">To Configure the PowerPivot Service Application</span></span>  
  
1.  <span data-ttu-id="885be-161">Klicken Sie in der SharePoint-Zentraladministration auf Dienstanwendungen verwalten.</span><span class="sxs-lookup"><span data-stu-id="885be-161">In SharePoint central administration, click Manage Service Applications.</span></span>  
  
2.  <span data-ttu-id="885be-162">Klicken Sie auf den Namen der Power Pivot-Dienst Anwendung, z. b. "Power Pivot-Standard Dienst Anwendung".</span><span class="sxs-lookup"><span data-stu-id="885be-162">Click the name of your PowerPivot Service Application, for example "Default PowerPivot Service Application".</span></span>  
  
3.  <span data-ttu-id="885be-163">Klicken Sie im Abschnitt „Aktionen“ auf **Einstellungen für Dienstanwendung konfigurieren** .</span><span class="sxs-lookup"><span data-stu-id="885be-163">Click **Configure service application settings** in the Actions section.</span></span>  
  
4.  <span data-ttu-id="885be-164">Legen Sie im Abschnitt **Datenaktualisierung** das **unbeaufsichtigte Daten Aktualisierungs Konto für Power Pivot**auf fest, `PowerPivotDataRefresh` und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="885be-164">In the **Data Refresh** section, set the **PowerPivot Unattended Data Refresh Account**to`PowerPivotDataRefresh` and then click **OK**.</span></span>  
  
     <span data-ttu-id="885be-165">![as_powerpivot_refresh_new_refresh_acount](../media/as-powerpivot-refresh-new-refresh-acount.gif "as_powerpivot_refresh_new_refresh_acount")</span><span class="sxs-lookup"><span data-stu-id="885be-165">![as_powerpivot_refresh_new_refresh_acount](../media/as-powerpivot-refresh-new-refresh-acount.gif "as_powerpivot_refresh_new_refresh_acount")</span></span>  
  
## <a name="to-configure-the-workbook"></a><span data-ttu-id="885be-166">So konfigurieren Sie die Arbeitsmappe</span><span class="sxs-lookup"><span data-stu-id="885be-166">To configure the workbook</span></span>  
  
1.  <span data-ttu-id="885be-167">Navigieren Sie im Power Pivot-Katalog zu Ihrer Arbeitsmappe, und klicken Sie auf **Datenaktualisierung verwalten**![as_powerpivot_refresh_manage_reresh](../media/as-powerpivot-refresh-manage-reresh.gif "as_powerpivot_refresh_manage_reresh").</span><span class="sxs-lookup"><span data-stu-id="885be-167">Browse to your workbook in the PowerPivot Gallery and click **Manage Data Refresh**![as_powerpivot_refresh_manage_reresh](../media/as-powerpivot-refresh-manage-reresh.gif "as_powerpivot_refresh_manage_reresh").</span></span>  
  
2.  <span data-ttu-id="885be-168">Sobald die Seite **Verlauf der Datenaktualisierung** angezeigt wird, klicken Sie auf **Zeitplan konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="885be-168">If you see the **Data Refresh History** page, click **Configure Schedule**.</span></span>  
  
3.  <span data-ttu-id="885be-169">Klicken Sie auf **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="885be-169">Click **Enable**.</span></span>  
  
4.  <span data-ttu-id="885be-170">Klicken Sie auf **Außerdem so bald wie möglich aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="885be-170">Click **Also Refresh as soon as possible**.</span></span>  
  
5.  <span data-ttu-id="885be-171">Klicken Sie im Abschnitt **Anmeldeinformationen** auf **Das vom Administrator konfigurierte Konto für die Datenaktualisierung verwenden**.</span><span class="sxs-lookup"><span data-stu-id="885be-171">In the **Credentials** section, click **Use the Data refresh account configured by the administrator**.</span></span>  
  
6.  <span data-ttu-id="885be-172">Deaktivieren Sie **Alle Datenquellen**.</span><span class="sxs-lookup"><span data-stu-id="885be-172">Clear **All data sources**.</span></span>  
  
7.  <span data-ttu-id="885be-173">Wählen Sie für die Datenquelle, die Oracle-Daten verwendet, die Option **Aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="885be-173">Select **Refresh** for the data source that uses the Oracle data.</span></span> <span data-ttu-id="885be-174">Der Name der Datenquelle kann in Microsoft Excel geändert werden, indem Sie auf das Menü **Daten**und dann auf **Verbindungen**und auf **Eigenschaften** klicken.</span><span class="sxs-lookup"><span data-stu-id="885be-174">The name of the data source name can be changed in Microsoft Excel in the **Data**, **Connections**, **Properties** menu.</span></span>  
  
8.  <span data-ttu-id="885be-175">Wählen Sie unter Ihrer Datenquelle die Option **Standardzeitplan verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="885be-175">Under your data source, Select **Use Default Schedule**.</span></span>  
  
9. <span data-ttu-id="885be-176">Wählen Sie **Stellen Sie mithilfe der in Secure Store Service (SSS) gespeicherten Anmeldeinformationen eine Verbindung her, um sich bei der Datenquelle anzumelden. Geben Sie die ID, mit der die Anmeldeinformationen nachgeschlagen werden, in das Feld „SSS-ID“ ein.**</span><span class="sxs-lookup"><span data-stu-id="885be-176">Select **Connect using the credentials saved in Secure Store Service (SSS) to log on to the data source. Enter the ID used to look up the credentials in the SSS ID box**.</span></span>  
  
10. <span data-ttu-id="885be-177">Geben Sie im Feld **ID:** Folgendes ein: `OracleAuthentication` .</span><span class="sxs-lookup"><span data-stu-id="885be-177">In the **ID:** box, type `OracleAuthentication`.</span></span>  
  
11. <span data-ttu-id="885be-178">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="885be-178">Click **OK**.</span></span>  
  
     <span data-ttu-id="885be-179">Wenn eine Fehlermeldung mit etwa dem Wortlaut `The provided Secure Store target application is either incorrectly configured or does not exist`angezeigt wird,</span><span class="sxs-lookup"><span data-stu-id="885be-179">If you see an error message similar to: `The provided Secure Store target application is either incorrectly configured or does not exist`.</span></span>  
  
     <span data-ttu-id="885be-180">gibt es zwei Lösungswege:</span><span class="sxs-lookup"><span data-stu-id="885be-180">The two common solutions are:</span></span>  
  
    -   <span data-ttu-id="885be-181">Überprüfen Sie, ob die Zielanwendungs-ID richtig ist.</span><span class="sxs-lookup"><span data-stu-id="885be-181">Verify that the Target Application ID is correct.</span></span>  
  
    -   <span data-ttu-id="885be-182">Stellen Sie sicher, dass Sie Anmeldeinformationen für die Zielanwendung festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="885be-182">Verify that you set credentials for the Target Application.</span></span>  
  
## <a name="to-verify-data-refresh-with-the-new-authentication"></a><span data-ttu-id="885be-183">So überprüfen Sie die Datenaktualisierung mit der neuen Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="885be-183">To Verify Data Refresh with the new authentication</span></span>  
 <span data-ttu-id="885be-184">Wenn Sie auf **OK**klicken, wird die Seite **Verlauf aktualisieren** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="885be-184">When you click **ok**, you see the **Refresh History** page.</span></span> <span data-ttu-id="885be-185">Binnen weniger Minuten sollte ein neues Element im Verlauf angezeigt werden, da Sie in den vorangehenden Schritten **Außerdem sobald wie möglich aktualisieren**ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="885be-185">Within a few minutes, you should see a new item in the refresh history because in the previous steps you selected **Also Refresh as soon as possible**.</span></span> <span data-ttu-id="885be-186">Der Standardwert für den Zeitgeberauftrag **Zeitgeberauftrag für die PowerPivot-Datenaktualisierung** beträgt 1 Minute.</span><span class="sxs-lookup"><span data-stu-id="885be-186">The default value for the timer job **PowerPivot Data Refresh Timer Job** is 1 minute.</span></span> <span data-ttu-id="885be-187">Wenn im Verlauf kein neues Element angezeigt wird, warten Sie einige Minuten, und aktualisieren Sie Ihren Browser.</span><span class="sxs-lookup"><span data-stu-id="885be-187">If you do not see a new item in the refresh history, wait a few minutes and refresh your browser.</span></span> <span data-ttu-id="885be-188">Sollte das neue Element auch dann nicht sichtbar sein, überprüfen Sie den aktuellen Wert des Zeitgeberauftrags.</span><span class="sxs-lookup"><span data-stu-id="885be-188">If you still do not see the new item, verify the current value of the timer job.</span></span>  
  
## <a name="more-information"></a><span data-ttu-id="885be-189">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="885be-189">More Information</span></span>  
  
-   <span data-ttu-id="885be-190">[Konfigurieren von Secure Store Service in SharePoint 2013](https://technet.microsoft.com/library/ee806866.aspx).</span><span class="sxs-lookup"><span data-stu-id="885be-190">[Configure the Secure Store Service in SharePoint 2013](https://technet.microsoft.com/library/ee806866.aspx).</span></span>  
  
-   <span data-ttu-id="885be-191">Weitere Informationen finden Sie im Abschnitt "geplante Datenaktualisierung" unter [Power Pivot-Datenaktualisierung mit SharePoint 2013 und SQL Server 2012 SP1 (Analysis Services)](https://msdn.microsoft.com/library/jj879294.aspx#bkmk_windows_auth_interactive_data_refresh).</span><span class="sxs-lookup"><span data-stu-id="885be-191">See the "Scheduled Data Refresh" section of [PowerPivot Data Refresh with SharePoint 2013 and SQL Server 2012 SP1 (Analysis Services)](https://msdn.microsoft.com/library/jj879294.aspx#bkmk_windows_auth_interactive_data_refresh).</span></span>  
  
  
