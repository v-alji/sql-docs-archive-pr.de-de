---
title: Erstellen eines Modells mit Berichts-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- report models [Reporting Services], creating
- Report Manager [Reporting Services], model creation
ms.assetid: 8e5d2bd3-48ec-45f3-afee-6d86797c8f28
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 59ce278a22ec9797b001ca37a0bde576483cf5d6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719693"
---
# <a name="create-a-model-using-report-manager"></a><span data-ttu-id="20f62-102">Erstellen eines Modells mithilfe des Berichts-Managers</span><span class="sxs-lookup"><span data-stu-id="20f62-102">Create a Model Using Report Manager</span></span>
  <span data-ttu-id="20f62-103">Mithilfe des Berichts-Managers können Sie Modelle auf der Grundlage eines [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Cubes, einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Datenbank oder einer Oracle-Datenbank generieren.</span><span class="sxs-lookup"><span data-stu-id="20f62-103">You can generate models from an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] cube, a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database, or an Oracle database using Report Manager.</span></span> <span data-ttu-id="20f62-104">Berichtsmodelle werden aus freigegebenen Datenquellen generiert, die auf dem Berichtsserver veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="20f62-104">Report models are generated from shared data sources that are published on the report server.</span></span> <span data-ttu-id="20f62-105">Wenn Sie noch nicht über eine freigegebene Datenquelle verfügen, müssen Sie sie erstellen.</span><span class="sxs-lookup"><span data-stu-id="20f62-105">If you do not already have a shared data source, you must create one.</span></span>  
  
 <span data-ttu-id="20f62-106">Das von Ihnen generierte Berichtsmodell basiert vollständig auf dem Schema der freigegebenen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="20f62-106">The report model that you generate is based entirely on the schema of the shared data source.</span></span> <span data-ttu-id="20f62-107">Sie können weder auswählen, welche Teile der Datenquelle im Modell enthalten sind, noch können Sie die Regeln oder Metadaten eines generierten Modells bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="20f62-107">You cannot choose which parts of the data source are included in the model, nor can you edit the rules or metadata of a generated model.</span></span> <span data-ttu-id="20f62-108">Sie können jedoch Eigenschaften für das Modell festlegen, nachdem es generiert wurde, und Rollenzuweisungen definieren, die den Zugriff auf das gesamte Modell oder auf Teile desselben einschränken.</span><span class="sxs-lookup"><span data-stu-id="20f62-108">However, you can set properties on the model after it is generated and define role assignments that restrict access to all or part of the model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="20f62-109">Ein mit Berichts-Manager oder 2007 generiertes Oracle-basiertes Modell [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[offSPServ](../includes/offspserv-md.md)] [!INCLUDE[SPS2010](../includes/sps2010-md.md)] enthält Datenbankobjekte, die Teil des Schemas für das Benutzerkonto sind, das zum Herstellen einer Verbindung mit der Oracle-Datenquelle verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="20f62-109">An Oracle-based model generated using Report Manager or [!INCLUDE[msCoName](../includes/msconame-md.md)][!INCLUDE[offSPServ](../includes/offspserv-md.md)] 2007 [!INCLUDE[SPS2010](../includes/sps2010-md.md)] will include database objects that are a part of the schema for the user account used to connect to the Oracle data source.</span></span> <span data-ttu-id="20f62-110">Der Name des Benutzerkontos wird in den Anmeldeinformationen für die Datenquelleneigenschaften angegeben.</span><span class="sxs-lookup"><span data-stu-id="20f62-110">The user account name is specified in the data source properties credentials.</span></span>  
  
### <a name="to-create-a-new-data-source-for-a-report-model-using-report-manager"></a><span data-ttu-id="20f62-111">So erstellen Sie mithilfe des Berichts-Managers eine neue Datenquelle für ein Berichtsmodell</span><span class="sxs-lookup"><span data-stu-id="20f62-111">To create a new data source for a report model using Report Manager</span></span>  
  
1.  <span data-ttu-id="20f62-112">Geben Sie in der Adressleiste des Webbrowsers die URL für den Berichtsserver ein.</span><span class="sxs-lookup"><span data-stu-id="20f62-112">In your Web browser, type the URL for your report server in the address bar.</span></span>  
  
2.  <span data-ttu-id="20f62-113">Klicken Sie auf **Neue Datenquelle**.</span><span class="sxs-lookup"><span data-stu-id="20f62-113">Click **New Data Source**.</span></span>  
  
3.  <span data-ttu-id="20f62-114">Geben Sie im Feld **Name** einen Namen für die Datenquelle ein.</span><span class="sxs-lookup"><span data-stu-id="20f62-114">In the **Name** box, enter a name for the data source.</span></span>  
  
4.  <span data-ttu-id="20f62-115">Geben Sie optional eine kurze Beschreibung in das Textfeld **Beschreibung** ein.</span><span class="sxs-lookup"><span data-stu-id="20f62-115">Optionally, enter a brief description of the mode in the **Description** text box.</span></span>  
  
5.  <span data-ttu-id="20f62-116">Überprüfen Sie, ob das Kontrollkästchen **Diese Datenquelle aktivieren** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="20f62-116">Verify that the **Enable this data source** check box is selected.</span></span>  
  
6.  <span data-ttu-id="20f62-117">Wählen Sie in der Liste **Verbindungstyp** den Typ der Datenquelle aus, mit der Sie eine Verbindung herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="20f62-117">In the **Connection type** list, select the data source type to which you want to connect.</span></span> <span data-ttu-id="20f62-118">Als Verbindungstyp muss einer der folgenden angegeben werden: **Oracle**, **Microsoft SQL Server** oder **Microsoft SQL Server Analysis Services**.</span><span class="sxs-lookup"><span data-stu-id="20f62-118">The connection type must be one of the following: **Oracle**, **Microsoft SQL Server** or **Microsoft SQL Server Analysis Services**.</span></span>  
  
7.  <span data-ttu-id="20f62-119">Geben Sie im Feld **Verbindungszeichenfolge** die Verbindungszeichenfolge ein, die auf die Datenbank zeigt.</span><span class="sxs-lookup"><span data-stu-id="20f62-119">In the **Connection string** box, enter the connection string that points to the database.</span></span>  
  
8.  <span data-ttu-id="20f62-120">Wählen Sie die Verbindungsmethode aus, die Benutzer des Berichts-Generators zum Herstellen der Verbindung mit der Datenbank verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="20f62-120">Select the connection method that Report Builder users will need to use to connect to the database.</span></span>  
  
    -   <span data-ttu-id="20f62-121">Windows-Authentifizierung: Wählen Sie diese Option aus, wenn [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Benutzer vom Betriebssystem authentifiziert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="20f62-121">Windows Authentication: Select this option when you want the operating system to authenticate [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] users.</span></span> <span data-ttu-id="20f62-122">Diese Option ermöglicht es [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , Sicherheitsfunktionen von Windows, z. B. die Kennwortverschlüsselung, für die Authentifizierung von Benutzern zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="20f62-122">This option allows [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to use Windows security features, such as password encryption, to authenticate users.</span></span> <span data-ttu-id="20f62-123">Es wird nachdrücklich empfohlen, diese Option auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="20f62-123">It is strongly recommended that you select this option.</span></span>  
  
    -   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="20f62-124">Authentifizierung: Wählen Sie diese Option aus, wenn Sie möchten, dass Benutzer ein von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Ihnen erstelltes Anmelde Konto verwenden.</span><span class="sxs-lookup"><span data-stu-id="20f62-124">Authentication: Select this option when you want users to use a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login account that you created.</span></span> <span data-ttu-id="20f62-125">Die Benutzer müssen einen gültigen [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Anmeldenamen und ein Kennwort angeben.</span><span class="sxs-lookup"><span data-stu-id="20f62-125">Users must supply a valid [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login name and password.</span></span>  
  
        > [!CAUTION]  
        >  <span data-ttu-id="20f62-126">Verwenden Sie nach Möglichkeit die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="20f62-126">Whenever possible, use Windows Authentication.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
### <a name="to-create-a-report-model-using-report-manager"></a><span data-ttu-id="20f62-127">So erstellen Sie ein Berichtsmodell mit dem Berichts-Manager</span><span class="sxs-lookup"><span data-stu-id="20f62-127">To create a report model using Report Manager</span></span>  
  
1.  <span data-ttu-id="20f62-128">Wählen Sie im Berichts-Manager die Datenquelle aus, die Sie für das Modell verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="20f62-128">In Report Manager, select the data source that you want to use for your model.</span></span>  
  
     <span data-ttu-id="20f62-129">Die Eigenschaftenseite wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20f62-129">The Properties page is displayed.</span></span>  
  
2.  <span data-ttu-id="20f62-130">Überprüfen Sie, ob Sie Optionen verwenden möchten, die für die Datenquelle angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="20f62-130">Verify that you want to use the options specified for the data source.</span></span>  
  
3.  <span data-ttu-id="20f62-131">Klicken Sie auf **Modell generieren**.</span><span class="sxs-lookup"><span data-stu-id="20f62-131">Click **Generate Model**.</span></span>  
  
     <span data-ttu-id="20f62-132">Die Seite Allgemein für die Datenquelle wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20f62-132">The General page is displayed for the data source.</span></span>  
  
4.  <span data-ttu-id="20f62-133">Geben Sie im Feld **Name** einen Namen für das Berichtsmodell ein.</span><span class="sxs-lookup"><span data-stu-id="20f62-133">In the **Name** box, enter a name for the report model.</span></span>  
  
5.  <span data-ttu-id="20f62-134">Geben Sie im Feld **Beschreibung** eine kurze Beschreibung des Modells ein.</span><span class="sxs-lookup"><span data-stu-id="20f62-134">In the **Description** box, enter a brief description of the model.</span></span>  
  
6.  <span data-ttu-id="20f62-135">Klicken Sie auf **Speicherort ändern**, um einen neuen Speicherort für das Berichtsmodell anzugeben.</span><span class="sxs-lookup"><span data-stu-id="20f62-135">To specify a new location to save the report model to, click **Change Location**.</span></span>  
  
     <span data-ttu-id="20f62-136">Standardmäßig wird das Berichtsmodell im Stammordner des Berichts-Managers gespeichert.</span><span class="sxs-lookup"><span data-stu-id="20f62-136">By default, the report model is saved to Report Manager Home.</span></span>  
  
7.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
     <span data-ttu-id="20f62-137">Das Berichtsmodell wird erstellt und in dem von Ihnen angegebenen Ordner gespeichert.</span><span class="sxs-lookup"><span data-stu-id="20f62-137">The report model is created and saved to the location that you specified.</span></span> <span data-ttu-id="20f62-138">Sie können diesem Modell Berechtigungen mit dem Berichts-Manager zuweisen.</span><span class="sxs-lookup"><span data-stu-id="20f62-138">You can assign permissions to this model by using Report Manager.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f62-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20f62-139">See Also</span></span>  
 <span data-ttu-id="20f62-140">[Erteilen von Berechtigungen für einen Berichtsserver im einheitlichen Modus](security/granting-permissions-on-a-native-mode-report-server.md) </span><span class="sxs-lookup"><span data-stu-id="20f62-140">[Granting Permissions on a Native Mode Report Server](security/granting-permissions-on-a-native-mode-report-server.md) </span></span>  
 <span data-ttu-id="20f62-141">[Datenverbindungen, Datenquellen und Verbindungs Zeichenfolgen in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="20f62-141">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="20f62-142">Neue Datenquelle (Seite, Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="20f62-142">New Data Source Page &#40;Report Manager&#41;</span></span>](../../2014/reporting-services/new-data-source-page-report-manager.md)  
  
  
