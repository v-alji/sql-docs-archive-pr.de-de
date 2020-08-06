---
title: Hilfsprogramm für die Server Konfiguration (Data Mining-Add-Ins für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 28435f86-5cec-4a1e-9b7d-b2069c1ddddb
author: minewiskan
ms.author: owend
ms.openlocfilehash: f985338e44bf0f4b591fcb70a4e093901626149f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727190"
---
# <a name="server-configuration-utility-data-mining-add-ins-for-excel"></a><span data-ttu-id="83970-102">Serverkonfigurations-Hilfsprogramm (Data Mining-Add-Ins für Excel)</span><span class="sxs-lookup"><span data-stu-id="83970-102">Server Configuration Utility (Data Mining Add-ins for Excel)</span></span>
  <span data-ttu-id="83970-103">Wenn Sie die Data Mining-Add-Ins für Excel installieren, wird auch ein Server Konfigurationsprogramm installiert, das beim erstmaligen Öffnen der Add-Ins ausgeführt wird. In diesem Thema wird beschrieben, wie das-Hilfsprogramm verwendet wird, um eine Verbindung mit einer Instanz von herzustellen [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] und eine Datenbank für die Arbeit mit Data Mining Modellen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="83970-103">When you install the Data Mining Add-ins for Excel, a Server Configuration Utility is also installed, and will run the first time you open the add-ins. This topic describes how to use the utility to connect to an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] and set up a database for working with data mining models.</span></span>  
  

  
##  <a name="step-1-connect-to-analysis-services"></a><a name="bkmk_step1"></a><span data-ttu-id="83970-104">Schritt 1: Herstellen einer Verbindung mit Analysis Services</span><span class="sxs-lookup"><span data-stu-id="83970-104">Step 1: Connect to Analysis Services</span></span>  
 <span data-ttu-id="83970-105">Wählen Sie den [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Server aus, der die Data Mining-Algorithmen bereitstellt und auf dem die Data Mining-Modelle gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="83970-105">Choose the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that provides the data mining algorithms and stores your data mining models.</span></span>  
  
 <span data-ttu-id="83970-106">Beim Erstellen einer Verbindung zum Ermöglichen des Data Mining sollten Sie einen Server auswählen, auf dem Sie mit Data Mining-Modellen experimentieren können.</span><span class="sxs-lookup"><span data-stu-id="83970-106">When you create a connection to enable data mining, you should choose a server where you can experiment with data mining models.</span></span> <span data-ttu-id="83970-107">Es empfiehlt sich, dass Sie eine neue Datenbank auf dem Server erstellen und die neue Datenbank für das Data Mining reservieren. Sie können sich auch an Ihren Administrator wenden, damit dieser einen Data Mining-Server für Sie vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="83970-107">We recommend that you create a new database on the server and dedicate the new database to data mining, or ask your administrator to prepare a data mining server for you.</span></span> <span data-ttu-id="83970-108">Auf diese Weise können Sie Modelle erstellen, ohne dass die Leistung anderer Dienste beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="83970-108">That way you can build models without affecting the performance of other services.</span></span>  
  
 <span data-ttu-id="83970-109">Beachten Sie, dass der für das Data Mining genutzte [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Server sich nicht unbedingt auf demselben Server wie die Quelldaten befinden muss.</span><span class="sxs-lookup"><span data-stu-id="83970-109">Note that the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server that you use for data mining does not need to be on the same server as your source data.</span></span>  
  
 <span data-ttu-id="83970-110">**Servername**</span><span class="sxs-lookup"><span data-stu-id="83970-110">**Server name**</span></span>  
 <span data-ttu-id="83970-111">Geben Sie den Namen des Servers ein, auf dem sich die Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] befindet, die für das Data Mining verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="83970-111">Type the name of the server that contains the instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that you will use for data mining.</span></span>  
  
 <span data-ttu-id="83970-112">**Authentifizierung**</span><span class="sxs-lookup"><span data-stu-id="83970-112">**Authentication**</span></span>  
 <span data-ttu-id="83970-113">Geben Sie die Authentifizierungsmethoden an.</span><span class="sxs-lookup"><span data-stu-id="83970-113">Specify the authentication methods.</span></span> <span data-ttu-id="83970-114">Die Windows-Authentifizierung ist für Verbindungen mit [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] erforderlich, es sei denn, der Administrator hat den Zugriff auf den Server über die HTTPPump konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="83970-114">Windows Authentication is required for connections to [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], unless your administrator has configured access to the server via the HTTPPump.</span></span>  
  
##  <a name="step-2-allow-temporary-models"></a><a name="bkmk_step2"></a><span data-ttu-id="83970-115">Schritt 2: temporäre Modelle zulassen</span><span class="sxs-lookup"><span data-stu-id="83970-115">Step 2: Allow Temporary Models</span></span>  
 <span data-ttu-id="83970-116">Bevor Sie die Add-Ins verwenden können, muss eine [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Servereigenschaft geändert werden, um das Erstellen temporärer Miningmodelle zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="83970-116">Before you can use the add-ins, an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server property must be changed to permit the creation of temporary mining models.</span></span>  
  
 <span data-ttu-id="83970-117">Temporäre Mining Modelle werden auch als *Sitzungs Modelle*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="83970-117">Temporary mining models are also called *session models*.</span></span> <span data-ttu-id="83970-118">Das liegt daran, dass die Modelle nur gespeichert werden, solange die aktuelle Sitzung geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="83970-118">This is because the models are stored only as long as your current session is open.</span></span> <span data-ttu-id="83970-119">Wenn Sie die Verbindung mit dem Server schließen, wird die Sitzung beendet, und alle während der Sitzung verwendeten Modelle werden gelöscht.</span><span class="sxs-lookup"><span data-stu-id="83970-119">When you close your connection to the server, the session is ended and any models used during the session are deleted.</span></span>  
  
 <span data-ttu-id="83970-120">Das Verwenden von Sitzungsminingmodellen wirkt sich nicht auf den Speicherplatz des Servers aus. Die höhere Auslastung beim Erstellen von Data Mining-Modellen wirkt sich jedoch möglicherweise auf die Serverleistung aus.</span><span class="sxs-lookup"><span data-stu-id="83970-120">The use of session mining models does not affect storage space on the server, but the overhead involved in creating data mining models may affect the performance of the server.</span></span>  
  
 <span data-ttu-id="83970-121">Der Assistent erkennt zuerst die Einstellungen auf dem Server, den Sie angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="83970-121">The wizard first detects the settings on the server that you specified.</span></span> <span data-ttu-id="83970-122">Wenn der Server temporäre Mining Modelle bereits zulässt, klicken Sie auf **weiter, um** den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="83970-122">If the server already allows temporary mining models, you can click **Next** to continue.</span></span> <span data-ttu-id="83970-123">Der Assistent bietet zudem Anweisungen zum Aktivieren temporärer Miningmodelle auf dem angegebenen [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Server sowie zum Senden von Anforderungen an den [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Administrator.</span><span class="sxs-lookup"><span data-stu-id="83970-123">The wizard also provides instructions for how to enable temporary mining models on the specified [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] server, or how to make a request to your [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] administrator.</span></span>  
  
##  <a name="step-3-create-database-for-add-in-users"></a><a name="bkmk_step3"></a><span data-ttu-id="83970-124">Schritt 3: Erstellen einer Datenbank für Add-in-Benutzer</span><span class="sxs-lookup"><span data-stu-id="83970-124">Step 3: Create Database for Add-in Users</span></span>  
 <span data-ttu-id="83970-125">Auf dieser Seite des Setup- und Konfigurations-Assistenten können Sie eine neue Datenbank erstellen, die für das Data Mining reserviert ist. Sie können aber auch eine vorhandene [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Datenbank auswählen.</span><span class="sxs-lookup"><span data-stu-id="83970-125">On this page of the setup and configuration wizard, you can create a new database that is dedicated to data mining, or select an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="83970-126">Data Mining erfordert eine Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], die im mehrdimensionalen Modus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="83970-126">Data mining requires an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] that is running in multidimensional mode.</span></span> <span data-ttu-id="83970-127">Das Data Mining wird im Tabellenmodus nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="83970-127">Tabular mode does not support data mining.</span></span>  
  
 <span data-ttu-id="83970-128">Es empfiehlt sich, eine separate Datenbank zu erstellen, die für das Data Mining reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="83970-128">We recommend that you create a separate database dedicated to data mining.</span></span> <span data-ttu-id="83970-129">Dadurch können Sie mit Data Mining-Modellen experimentieren, ohne dass andere Objekte der Projektmappe beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="83970-129">This lets you experiment with data mining models without affecting other solution objects.</span></span>  
  
 <span data-ttu-id="83970-130">Wenn Sie eine vorhandene Datenbank in einer Instanz von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]auswählen, beachten Sie Folgendes: Vorhandene Modelle können überschrieben werden, wenn Sie mit den Add-Ins ein Modell erstellen und ein gleichnamiges Modell bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="83970-130">If you choose an existing database on an instance of [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)], note that it is possible to overwrite existing models if you use the add-ins to create a model and a model of that name already exists.</span></span>  
  
 <span data-ttu-id="83970-131">**Neue Datenbank erstellen**</span><span class="sxs-lookup"><span data-stu-id="83970-131">**Create new database**</span></span>  
 <span data-ttu-id="83970-132">Wählen Sie diese Option aus, um eine neue Datenbank auf dem ausgewählten Server zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="83970-132">Select this option to create a new database on the selected server.</span></span> <span data-ttu-id="83970-133">In einer Data Mining-Datenbank werden die Datenquellen, Miningstrukturen und Miningmodelle gespeichert.</span><span class="sxs-lookup"><span data-stu-id="83970-133">A data mining database will store your data sources, mining structures, and mining models.</span></span>  
  
 <span data-ttu-id="83970-134">**Datenbankname**</span><span class="sxs-lookup"><span data-stu-id="83970-134">**Database name**</span></span>  
 <span data-ttu-id="83970-135">Geben Sie den Namen der neuen Datenbank ein.</span><span class="sxs-lookup"><span data-stu-id="83970-135">Type the name of the new database.</span></span> <span data-ttu-id="83970-136">Wenn der Name nicht bereits verwendet wird, wird er automatisch erstellt.</span><span class="sxs-lookup"><span data-stu-id="83970-136">If the name is not already in use, it will be created for you.</span></span>  
  
 <span data-ttu-id="83970-137">**Vorhandene Datenbank verwenden**</span><span class="sxs-lookup"><span data-stu-id="83970-137">**Use existing database**</span></span>  
 <span data-ttu-id="83970-138">Wählen Sie diese Option aus, um eine vorhandene [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)]-Datenbank zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="83970-138">Select this option to use an existing [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="83970-139">**Datenbank**</span><span class="sxs-lookup"><span data-stu-id="83970-139">**Database**</span></span>  
 <span data-ttu-id="83970-140">Wenn Sie die Option zum Verwenden einer vorhandenen Datenbank ausgewählt haben, müssen Sie den Datenbanknamen in der Liste auswählen.</span><span class="sxs-lookup"><span data-stu-id="83970-140">If you chose the option to use an existing database, you must select the database name from the list.</span></span>  
  
##  <a name="step-4-give-add-in-users-appropriate-permissions"></a><a name="bkmk_step4"></a><span data-ttu-id="83970-141">Schritt 4: Add-in-Benutzern entsprechende Berechtigungen geben</span><span class="sxs-lookup"><span data-stu-id="83970-141">Step 4: Give Add-in Users Appropriate Permissions</span></span>  
 <span data-ttu-id="83970-142">Sie müssen sicherstellen, dass Sie (und alle anderen Benutzer, die die Add-Ins verwenden) über die erforderlichen Berechtigungen zum Durchsuchen, Bearbeiten, Verarbeiten oder Erstellen von Data Mining-Strukturen und -Modellen verfügen.</span><span class="sxs-lookup"><span data-stu-id="83970-142">You must ensure that you (and any other users of the add-ins) have the necessary permissions to browse, edit, process, or create data mining structures and models.</span></span>  
  
 <span data-ttu-id="83970-143">Standardmäßig ist die integrierte Windows-Authentifizierung erforderlich, um die Add-Ins zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="83970-143">By default, integrated Windows Authentication is required to use the add-ins.</span></span>  
  
 <span data-ttu-id="83970-144">**Add-In-Benutzern Administratorberechtigungen für die Datenbank erteilen**</span><span class="sxs-lookup"><span data-stu-id="83970-144">**Give add-in users database administration permissions**</span></span>  
 <span data-ttu-id="83970-145">Wählen Sie diese Option aus, um den aufgeführten Benutzern administrativen Zugriff auf die Datenbank zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="83970-145">Select this option to give the listed users administrative access to the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="83970-146">Diese Berechtigungen gelten nur für die Datenbank, die im Feld **Datenbankname** aufgelistet ist.</span><span class="sxs-lookup"><span data-stu-id="83970-146">These permissions apply only to the database listed in the **Database name** box.</span></span>  
  
 <span data-ttu-id="83970-147">**Datenbankname**</span><span class="sxs-lookup"><span data-stu-id="83970-147">**Database name**</span></span>  
 <span data-ttu-id="83970-148">Zeigt den Namen der ausgewählten Datenbank an.</span><span class="sxs-lookup"><span data-stu-id="83970-148">Displays the name of the selected database.</span></span>  
  
 <span data-ttu-id="83970-149">**Hinzuzufügende Benutzer oder Gruppen angeben**</span><span class="sxs-lookup"><span data-stu-id="83970-149">**Specify users or groups to add**</span></span>  
 <span data-ttu-id="83970-150">Wählen Sie die Anmeldenamen aus, die über Zugriff auf die für Data Mining verwendete Datenbank verfügen sollen.</span><span class="sxs-lookup"><span data-stu-id="83970-150">Select the logins that will have access to the database used for data mining.</span></span>  
  
 <span data-ttu-id="83970-151">**Add**</span><span class="sxs-lookup"><span data-stu-id="83970-151">**Add**</span></span>  
 <span data-ttu-id="83970-152">Klicken Sie auf diese Option, um ein Dialogfeld zu öffnen und Benutzer oder Gruppen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="83970-152">Click to open a dialog box and add users or groups.</span></span>  
  
 <span data-ttu-id="83970-153">**Entfernen**</span><span class="sxs-lookup"><span data-stu-id="83970-153">**Remove**</span></span>  
 <span data-ttu-id="83970-154">Klicken Sie auf diese Option, um den ausgewählten Benutzer oder die ausgewählte Gruppe aus der Liste der Benutzer mit Administratorberechtigungen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="83970-154">Click to remove the selected user or group from the list of users with administration permissions.</span></span>  
  
  
