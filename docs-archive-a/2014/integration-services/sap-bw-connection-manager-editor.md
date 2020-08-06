---
title: SAP BW Verbindungs-Manager-Editor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: ec970319-e749-4753-8675-9cf76ed99669
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 527af979fc9c92062f24e1fe161b93e88ed4ab4a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698433"
---
# <a name="sap-bw-connection-manager-editor"></a><span data-ttu-id="a1523-102">SAP BW-Verbindungs-Manager-Editor</span><span class="sxs-lookup"><span data-stu-id="a1523-102">SAP BW Connection Manager Editor</span></span>
  <span data-ttu-id="a1523-103">Verwenden Sie den **SAP BW-Verbindungs-Manager-Editor** , um die Eigenschaften festzulegen, mit denen eine Verbindung mit einem SAP NetWeaver BW-System, Version 7, hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a1523-103">Use the **SAP BW Connection Manager Editor** to specify the properties to use to connect to an SAP Netweaver BW version 7 system.</span></span>  
  
 <span data-ttu-id="a1523-104">Der SAP BW-Verbindungs-Manager stellt Verbindungen mit einem SAP NetWeaver BW-System (Version 7) her, die von einer SAP BW-Quelle oder einem SAP BW-Ziel verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a1523-104">The SAP BW connection manager provides connectivity to an SAP Netweaver BW 7 system for use by the SAP BW source or destination.</span></span> <span data-ttu-id="a1523-105">Weitere Informationen zum SAP BW-Verbindungs-Manager von [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW finden Sie unter [SAP BW-Verbindungs-Manager](connection-manager/sap-bw-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="a1523-105">To learn more about the SAP BW connection manager of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW, see [SAP BW Connection Manager](connection-manager/sap-bw-connection-manager.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a1523-106">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="a1523-106">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="a1523-107">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="a1523-107">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
 <span data-ttu-id="a1523-108">**So öffnen Sie den SAP BW-Verbindungs-Manager-Editor**</span><span class="sxs-lookup"><span data-stu-id="a1523-108">**To open the SAP BW Connection Manager Editor**</span></span>  
  
1.  <span data-ttu-id="a1523-109">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket, das den SAP BW-Verbindungs-Manager enthält.</span><span class="sxs-lookup"><span data-stu-id="a1523-109">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that contains the SAP BW connection manager.</span></span>  
  
2.  <span data-ttu-id="a1523-110">Führen Sie im Bereich Verbindungs-Manager auf der Registerkarte **Ablaufsteuerung** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="a1523-110">In the Connection Managers area on the **Control Flow** tab, do one of the following steps:</span></span>  
  
    -   <span data-ttu-id="a1523-111">Doppelklicken Sie auf den SAP BW-Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="a1523-111">Double-click the SAP BW connection manager.</span></span>  
  
         <span data-ttu-id="a1523-112">Oder</span><span class="sxs-lookup"><span data-stu-id="a1523-112">-or-</span></span>  
  
    -   <span data-ttu-id="a1523-113">Klicken Sie mit der rechten Maustaste auf den SAP BW-Verbindungs-Manager, und wählen Sie dann **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="a1523-113">Right-click the SAP BW connection manager, and then select **Edit**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="a1523-114">Tastatur</span><span class="sxs-lookup"><span data-stu-id="a1523-114">Options</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a1523-115">Wenn Sie nicht alle Werte kennen, die zur Konfiguration des Verbindungs-Managers erforderlich sind, müssen Sie ggf. Ihren SAP-Administrator um Unterstützung bitten.</span><span class="sxs-lookup"><span data-stu-id="a1523-115">If you do not know all the values that are required to configure the connection manager, you might have to ask your SAP administrator.</span></span>  
  
 <span data-ttu-id="a1523-116">**Client**</span><span class="sxs-lookup"><span data-stu-id="a1523-116">**Client**</span></span>  
 <span data-ttu-id="a1523-117">Geben Sie die Clientanzahl des Systems an.</span><span class="sxs-lookup"><span data-stu-id="a1523-117">Specify the client number of the system.</span></span>  
  
 <span data-ttu-id="a1523-118">**Sprache**</span><span class="sxs-lookup"><span data-stu-id="a1523-118">**Language**</span></span>  
 <span data-ttu-id="a1523-119">Geben Sie die Sprache an, die vom System verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a1523-119">Specify the language that the system uses.</span></span> <span data-ttu-id="a1523-120">Geben Sie beispielsweise **EN** für Englisch an.</span><span class="sxs-lookup"><span data-stu-id="a1523-120">For example, specify **EN** for English.</span></span>  
  
 <span data-ttu-id="a1523-121">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="a1523-121">**User name**</span></span>  
 <span data-ttu-id="a1523-122">Geben Sie den Benutzernamen an, über den eine Verbindung mit dem System hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="a1523-122">Specify the user name that will be used to connect to the system.</span></span>  
  
 <span data-ttu-id="a1523-123">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="a1523-123">**Password**</span></span>  
 <span data-ttu-id="a1523-124">Geben Sie das Kennwort an, das mit dem Benutzernamen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a1523-124">Specify the password that will be used with the user name.</span></span>  
  
 <span data-ttu-id="a1523-125">**Einzelnen Anwendungsserver verwenden**</span><span class="sxs-lookup"><span data-stu-id="a1523-125">**Use single application server**</span></span>  
 <span data-ttu-id="a1523-126">Stellen Sie eine Verbindung mit einem einzelnen Anwendungsserver her.</span><span class="sxs-lookup"><span data-stu-id="a1523-126">Connect to a single application server.</span></span>  
  
 <span data-ttu-id="a1523-127">Um eine Verbindung mit einer Gruppe von Servern mit Lastenausgleich herzustellen, verwenden Sie stattdessen die Option **Lastenausgleich verwenden** .</span><span class="sxs-lookup"><span data-stu-id="a1523-127">To connect to a group of load-balanced servers, use the **Use load balancing** option instead.</span></span>  
  
 <span data-ttu-id="a1523-128">**Host**</span><span class="sxs-lookup"><span data-stu-id="a1523-128">**Host**</span></span>  
 <span data-ttu-id="a1523-129">Wenn Sie eine Verbindung mit einem einzelnen Anwendungsserver herstellen, geben Sie den Hostnamen an.</span><span class="sxs-lookup"><span data-stu-id="a1523-129">If connecting to a single application server, specify the host name.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a1523-130">Diese Option ist nur verfügbar, wenn Sie die Option **Einzelnen Anwendungsserver verwenden** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a1523-130">This option is only available if you have selected the **Use single application server** option.</span></span>  
  
 <span data-ttu-id="a1523-131">**Systemnummer**</span><span class="sxs-lookup"><span data-stu-id="a1523-131">**System number**</span></span>  
 <span data-ttu-id="a1523-132">Wenn Sie eine Verbindung mit einem Einzelanwendungsserver herstellen, geben Sie die Systemnummer an.</span><span class="sxs-lookup"><span data-stu-id="a1523-132">If connecting to a single application server, specify the system number.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a1523-133">Diese Option ist nur verfügbar, wenn Sie die Option **Einzelnen Anwendungsserver verwenden** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a1523-133">This option is only available if you have selected the **Use single application server** option.</span></span>  
  
 <span data-ttu-id="a1523-134">**Lastenausgleich verwenden**</span><span class="sxs-lookup"><span data-stu-id="a1523-134">**Use load balancing**</span></span>  
 <span data-ttu-id="a1523-135">Stellen Sie einen Verbindung mit einer Gruppe von Servern mit Lastenausgleich her.</span><span class="sxs-lookup"><span data-stu-id="a1523-135">Connect to a group of load-balanced servers.</span></span>  
  
 <span data-ttu-id="a1523-136">Um eine Verbindung mit einem Einzelanwendungsserver herzustellen, verwenden Sie stattdessen die Option **Einzelnen Anwendungsserver verwenden** .</span><span class="sxs-lookup"><span data-stu-id="a1523-136">To connect to a single application server, use the **Use single application server** option instead.</span></span>  
  
 <span data-ttu-id="a1523-137">**Nachrichtenserver**</span><span class="sxs-lookup"><span data-stu-id="a1523-137">**Message server**</span></span>  
 <span data-ttu-id="a1523-138">Beim Herstellen einer Verbindung mit einer Gruppe von Servern mit Lastenausgleich, geben Sie den Namen des Nachrichtenservers an.</span><span class="sxs-lookup"><span data-stu-id="a1523-138">If connecting to a group of load-balanced servers, specify the name of the message server.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a1523-139"> Diese Option ist nur verfügbar, wenn Sie die Option **Lastenausgleich verwenden** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a1523-139">This option is only available if you have selected the **Use load balancing** option.</span></span>  
  
 <span data-ttu-id="a1523-140">**Gruppe**</span><span class="sxs-lookup"><span data-stu-id="a1523-140">**Group**</span></span>  
 <span data-ttu-id="a1523-141">Beim Herstellen einer Verbindung mit einer Gruppe von Servern mit Lastenausgleich geben Sie den Namen der Servergruppe an.</span><span class="sxs-lookup"><span data-stu-id="a1523-141">If connecting to a group of load-balanced servers, specify the name of the server group name.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a1523-142"> Diese Option ist nur verfügbar, wenn Sie die Option **Lastenausgleich verwenden** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a1523-142">This option is only available if you have selected the **Use load balancing** option.</span></span>  
  
 <span data-ttu-id="a1523-143">**SID**</span><span class="sxs-lookup"><span data-stu-id="a1523-143">**SID**</span></span>  
 <span data-ttu-id="a1523-144">Beim Herstellen einer Verbindung mit einer Gruppe von Servern mit Lastenausgleich geben Sie die System-ID für die Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="a1523-144">If connecting to a group of load-balanced servers, specify the System ID for the connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a1523-145"> Diese Option ist nur verfügbar, wenn Sie die Option **Lastenausgleich verwenden** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="a1523-145">This option is only available if you have selected the **Use load balancing** option.</span></span>  
  
 <span data-ttu-id="a1523-146">**Protokollverzeichnis**</span><span class="sxs-lookup"><span data-stu-id="a1523-146">**Log directory**</span></span>  
 <span data-ttu-id="a1523-147">Aktivieren Sie die Protokollierung für die Komponenten von [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span><span class="sxs-lookup"><span data-stu-id="a1523-147">Enable logging for the components of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
 <span data-ttu-id="a1523-148">Um die Protokollierung zu aktivieren, geben Sie ein Verzeichnis für die Protokolldateien an, die vor und nach jedem RFC-Funktionsaufruf erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a1523-148">To enable logging, specify a directory for the log files that are created before and after each RFC function call.</span></span> <span data-ttu-id="a1523-149">(Durch diese Protokollierungsfunktion werden viele Protokolldateien im XML-Format erstellt.</span><span class="sxs-lookup"><span data-stu-id="a1523-149">(This logging feature creates many log files in XML format.</span></span> <span data-ttu-id="a1523-150">Da diese Protokolldateien auch alle übertragenen Datenzeilen enthalten, können sie viel Speicherplatz auf dem Datenträger beanspruchen.)</span><span class="sxs-lookup"><span data-stu-id="a1523-150">As these log files also contain all the rows of data that are transferred, these log files may consume a large amount of disk space.)</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="a1523-151">Wenn die übertragenen Daten vertrauliche Informationen enthalten, sind diese auch in den Protokolldateien enthalten.</span><span class="sxs-lookup"><span data-stu-id="a1523-151">If the data that is transferred contains sensitive information, the log files will also contain that sensitive information.</span></span>  
  
 <span data-ttu-id="a1523-152">Um das Protokollverzeichnis anzugeben, können Sie entweder den Verzeichnispfad manuell eingeben oder auf **Durchsuchen** klicken und zum Protokollverzeichnis navigieren.</span><span class="sxs-lookup"><span data-stu-id="a1523-152">To specify the log directory, you can either enter the directory path manually, or click **Browse** and browse to the log directory.</span></span>  
  
 <span data-ttu-id="a1523-153">Wenn Sie kein Protokollverzeichnis auswählen, wird die Protokollierung nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a1523-153">If you do not select a log directory, logging is not enabled.</span></span>  
  
 <span data-ttu-id="a1523-154">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="a1523-154">**Browse**</span></span>  
 <span data-ttu-id="a1523-155">Wechseln Sie zu einem Ordner, der als Protokollverzeichnis verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a1523-155">Browse to select a folder for the log directory.</span></span>  
  
 <span data-ttu-id="a1523-156">**Verbindung testen**</span><span class="sxs-lookup"><span data-stu-id="a1523-156">**Test Connection**</span></span>  
 <span data-ttu-id="a1523-157">Testen Sie die Verbindung mithilfe der Werte, die Sie eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="a1523-157">Test the connection using the values that you have provided.</span></span> <span data-ttu-id="a1523-158">Nachdem Sie auf **Verbindung testen**geklickt haben, wird in einem Meldungsfeld angezeigt, ob die Verbindung erfolgreich war oder nicht.</span><span class="sxs-lookup"><span data-stu-id="a1523-158">After clicking **Test Connection**, a message box appears and indicates whether the connection succeeded or failed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1523-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a1523-159">See Also</span></span>  
 [<span data-ttu-id="a1523-160">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="a1523-160">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](microsoft-connector-for-sap-bw-f1-help.md)  
  
  
