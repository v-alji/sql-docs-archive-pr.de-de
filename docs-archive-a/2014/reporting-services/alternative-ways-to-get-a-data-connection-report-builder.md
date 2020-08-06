---
title: Alternative Methoden zum Herstellen einer Datenverbindung (Berichts-Generator) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: aebc5f3d-97d5-4d54-b525-753fed073a9a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2be693469318172b2a55fbcb17b33e1deaaed3df
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609745"
---
# <a name="alternative-ways-to-get-a-data-connection-report-builder"></a><span data-ttu-id="85493-102">Alternative Methoden zum Herstellen einer Datenverbindung (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="85493-102">Alternative Ways to Get a Data Connection (Report Builder)</span></span>
  <span data-ttu-id="85493-103">Eine Datenverbindung enthält die Informationen zum Herstellen einer Verbindung mit einer externen Datenquelle, z. B. einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="85493-103">A data connection contains the information to connect to an external data source such as a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span> <span data-ttu-id="85493-104">Normalerweise erhalten Sie die Verbindungsinformationen und den zu verwendenden Anmeldeinformationstyp vom Datenquellenbesitzer.</span><span class="sxs-lookup"><span data-stu-id="85493-104">Usually, you get the connection information and the type of credentials to use from the data source owner.</span></span>  
  
 <span data-ttu-id="85493-105">Sie können zum Angeben einer Datenverbindung eine freigegebene Datenquelle vom Berichtsserver verwenden oder eine eingebettete Datenquelle erstellen, die nur in einem bestimmten Bericht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="85493-105">To specify a data connection, you can use a shared data source from the report server or create an embedded data source that is used only in a specific report.</span></span>  
  
 <span data-ttu-id="85493-106">In den meisten Lernprogrammen werden eingebettete Datenquellen verwendet. Wenn Sie jedoch über Zugriff auf freigegebene Datenquellen verfügen, können stattdessen diese verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="85493-106">In most tutorials you use embedded data sources, but if you have access to shared data sources, then you can use them instead.</span></span>  
  
## <a name="getting-a-data-connection-from-a-shared-data-source"></a><span data-ttu-id="85493-107">Abrufen einer Datenverbindung von einer freigegebenen Datenquelle</span><span class="sxs-lookup"><span data-stu-id="85493-107">Getting a Data Connection From a Shared Data Source</span></span>  
 <span data-ttu-id="85493-108">Wenn der Berichtsserver verfügbare freigegebene Datenquellen enthält, zu deren Verwendung Sie berechtigt sind, können Sie diese Datenquellen anstelle einer eingebetteten Datenquelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="85493-108">If the report server has available shared data source that you have permissions to use, you can use them instead of an embedded data source.</span></span> <span data-ttu-id="85493-109">In den folgenden Verfahren wird gezeigt, wie Sie nach den freigegebenen Datenquellen suchen und die für die Verwendung erforderlichen Anmeldeinformationen angeben.</span><span class="sxs-lookup"><span data-stu-id="85493-109">The following procedures tell how to locate the shared data sources and provide any credentials needed to use them.</span></span>  
  
 <span data-ttu-id="85493-110">Sie müssen zu einem Berichtsserver navigieren und eine freigegebene Datenquelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="85493-110">To use a shared data source, you must browse to a report server and select one.</span></span> <span data-ttu-id="85493-111">Normalerweise erhalten Sie die Berichtsserver-URL vom Berichtsserveradministrator.</span><span class="sxs-lookup"><span data-stu-id="85493-111">Usually, you get the report server URL from the report server administrator.</span></span>  
  
#### <a name="to-specify-a-data-connection-from-a-list-of-shared-data-sources"></a><span data-ttu-id="85493-112">So geben Sie eine Datenverbindung aus einer Liste freigegebener Datenquellen an</span><span class="sxs-lookup"><span data-stu-id="85493-112">To specify a data connection from a list of shared data sources</span></span>  
  
1.  <span data-ttu-id="85493-113">Klicken Sie auf der Seite **Dataset auswählen** auf **Dataset erstellen**und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="85493-113">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="85493-114">Die Seite **Verbindung mit einer Datenquelle auswählen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="85493-114">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="85493-115">Wählen Sie in der Liste der Datenquellen eine Datenquelle aus, für Sie Zugriffsberechtigungen besitzen.</span><span class="sxs-lookup"><span data-stu-id="85493-115">From the list of data sources, select a data source that you have permission to access.</span></span>  
  
3.  <span data-ttu-id="85493-116">Klicken Sie auf **Verbindung testen**, um sicherzustellen, dass die Verbindung mit der Datenquelle hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="85493-116">To verify that you can connect to the data source, click **Test Connection**.</span></span> <span data-ttu-id="85493-117">Die Meldung "Die Verbindung wurde erfolgreich hergestellt" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="85493-117">The message "Connection created successfully" appears.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
4.  <span data-ttu-id="85493-118">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="85493-118">Click **Next**.</span></span>  
  
     <span data-ttu-id="85493-119">Geben Sie ggf. die Anmeldeinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="85493-119">If necessary, enter your credentials.</span></span> <span data-ttu-id="85493-120">Aktivieren Sie **Kennwort mit Verbindung speichern**, wenn Sie die Anmeldeinformationen lokal speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="85493-120">To save the credentials locally, select **Save password with connection**.</span></span> <span data-ttu-id="85493-121">Falls Sie diese Option nicht aktivieren, werden Sie jedes Mal, wenn Sie den Bericht ausführen, zur Eingabe von Anmeldeinformationen aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="85493-121">If you not select this option, you will be prompted for credentials every time that you run the report</span></span>  
  
5.  [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
#### <a name="to-specify-a-data-connection-by-browsing-to-a-shared-data-source-on-a-report-server"></a><span data-ttu-id="85493-122">So geben Sie eine Datenverbindung an, indem Sie zu einer freigegebenen Datenquelle auf einem Berichtsserver navigieren</span><span class="sxs-lookup"><span data-stu-id="85493-122">To specify a data connection by browsing to a shared data source on a report server</span></span>  
  
1.  <span data-ttu-id="85493-123">Klicken Sie auf der Seite **Dataset auswählen** auf **Dataset erstellen**und anschließend auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="85493-123">On the **Choose a dataset** page, select **Create a dataset**, and then click **Next**.</span></span> <span data-ttu-id="85493-124">Die Seite **Verbindung mit einer Datenquelle auswählen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="85493-124">The **Choose a connection to a data source** page opens.</span></span>  
  
2.  <span data-ttu-id="85493-125">Klicken Sie auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="85493-125">Click **Browse**.</span></span> <span data-ttu-id="85493-126">Das Dialogfeld **Datenquelle auswählen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="85493-126">The **Select Data Source** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="85493-127">Wählen Sie in der Dropdownliste **Suchen in** die Option **Letzte Sites und Server**aus.</span><span class="sxs-lookup"><span data-stu-id="85493-127">From the **Look in** drop-down list, select **Recent Sites and Servers**.</span></span> <span data-ttu-id="85493-128">Klicken Sie im Datenquellenbereich auf die URL für den Server, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="85493-128">In the data source pane, click the URL for your server, and then click **Open**.</span></span>  
  
     <span data-ttu-id="85493-129">Die Liste der Datenquellen oder Modelle wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="85493-129">The list of data sources or models appears.</span></span>  
  
4.  <span data-ttu-id="85493-130">Alternativ können Sie die URL zum Berichtsserver im Feld **Name**eingeben.</span><span class="sxs-lookup"><span data-stu-id="85493-130">Alternatively, in **Name**, type the URL to the report server.</span></span> <span data-ttu-id="85493-131">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="85493-131">Click **Open**.</span></span>  
  
     <span data-ttu-id="85493-132">Der Berichts-Generator stellt eine Verbindung mit dem Berichtsserver her und lädt die im Stammordner verfügbaren Datenquellen.</span><span class="sxs-lookup"><span data-stu-id="85493-132">Report Builder connects to the report server and loads the data sources that are available at the root folder.</span></span>  
  
5.  <span data-ttu-id="85493-133">Navigieren Sie zu einem Ordner mit einer Datenquelle, für die Sie ausreichende Berechtigungen besitzen, wählen Sie die Datenquelle aus, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="85493-133">Navigate to a folder that contains a data source that you have sufficient permissions to connect to, select the data source, and then click **Open**.</span></span>  
  
     <span data-ttu-id="85493-134">Nun wird wieder die Seite **Verbindung mit einer Datenquelle auswählen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="85493-134">You are back on the **Choose a connection to a data source** page.</span></span>  
  
6.  <span data-ttu-id="85493-135">Klicken Sie auf **Verbindung testen**, um sicherzustellen, dass die Verbindung mit der Datenquelle hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="85493-135">To verify that you can connect to the data source, click **Test Connection**.</span></span>  
  
     <span data-ttu-id="85493-136">Die Meldung "Die Verbindung wurde erfolgreich hergestellt" wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="85493-136">The message "Connection created successfully" appears.</span></span> [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
7.  <span data-ttu-id="85493-137">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="85493-137">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="85493-138">Geben Sie die Anmeldeinformationen ein, wenn Sie zur Eingabe eines Benutzernamens und Kennworts aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="85493-138">If you are prompted for a user name and password, enter your credentials.</span></span> <span data-ttu-id="85493-139">Aktivieren Sie **Kennwort mit Verbindung speichern**, wenn Sie die Anmeldeinformationen lokal speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="85493-139">To save the credentials locally, select **Save password with connection**.</span></span>  
  
9. [!INCLUDE[clickOK](../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="85493-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85493-140">See Also</span></span>  
 <span data-ttu-id="85493-141">[Hinzufügen von Daten zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="85493-141">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 [<span data-ttu-id="85493-142">Lernprogramme &#40;Berichts-Generator&#41;</span><span class="sxs-lookup"><span data-stu-id="85493-142">Tutorials &#40;Report Builder&#41;</span></span>](report-builder-tutorials.md)  
  
  
