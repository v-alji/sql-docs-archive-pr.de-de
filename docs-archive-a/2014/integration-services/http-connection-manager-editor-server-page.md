---
title: HTTP-Verbindungs-Manager-Editor (Seite Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.httpconnection.server.f1
helpviewer_keywords:
- HTTP Connection Manager Editor
ms.assetid: 774778a0-ece6-4971-b93f-b121d8fc1fc1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a2349766b11b28ff258496dc966d554d49c7657b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609325"
---
# <a name="http-connection-manager-editor-server-page"></a><span data-ttu-id="98973-102">HTTP-Verbindungs-Manager-Editor (Seite Server)</span><span class="sxs-lookup"><span data-stu-id="98973-102">HTTP Connection Manager Editor (Server Page)</span></span>
  <span data-ttu-id="98973-103">Mithilfe der Registerkarte **Server** des Dialogfelds **HTTP-Verbindungs-Manager-Editor** können Sie den HTTP-Verbindungs-Manager konfigurieren, indem Sie Eigenschaften, z. B. URL und Sicherheitseinstellungen, angeben.</span><span class="sxs-lookup"><span data-stu-id="98973-103">Use the **Server** tab of the **HTTP Connection Manager Editor** dialog box to configure the HTTP Connection Manager by specifying properties such as the URL and security credentials.</span></span> <span data-ttu-id="98973-104">Eine HTTP-Verbindung ermöglicht Paketen den Zugriff auf einen Webserver, indem zum Senden und Empfangen von Dateien HTTP verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="98973-104">An HTTP connection enables a package to access a Web server by using HTTP to send or receive files.</span></span> <span data-ttu-id="98973-105">Nach der Konfiguration des HTTP-Verbindungs-Managers können Sie die Verbindung testen.</span><span class="sxs-lookup"><span data-stu-id="98973-105">After configuring the HTTP Connection Manager, you can also test the connection.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="98973-106">Der HTTP-Verbindungs-Manager unterstützt nur die anonyme Authentifizierung und die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="98973-106">The HTTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="98973-107">Er unterstützt keine Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="98973-107">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="98973-108">Weitere Informationen zum HTTP-Verbindungs-Manager finden Sie unter [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="98973-108">To learn more about the HTTP connection manager, see [HTTP Connection Manager](connection-manager/http-connection-manager.md).</span></span> <span data-ttu-id="98973-109">Weitere Informationen zu einem allgemeinen Verwendungsszenario für den HTTP-Verbindungs-Manager finden Sie unter [Web Service Task](control-flow/web-service-task.md).</span><span class="sxs-lookup"><span data-stu-id="98973-109">To learn more about a common usage scenario for the HTTP Connection Manager, see [Web Service Task](control-flow/web-service-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="98973-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="98973-110">Options</span></span>  
 <span data-ttu-id="98973-111">**Server-URL**</span><span class="sxs-lookup"><span data-stu-id="98973-111">**Server URL**</span></span>  
 <span data-ttu-id="98973-112">Geben Sie die URL für den Server ein.</span><span class="sxs-lookup"><span data-stu-id="98973-112">Type the URL for the server.</span></span>  
  
 <span data-ttu-id="98973-113">Wenn Sie die Schaltfläche **WSDL herunterladen** auf der Seite **Allgemein** im **Editor für den Task 'Webdienst'** verwenden möchten, um eine WSDL-Datei herunterzuladen, geben Sie die URL für die WSDL-Datei ein.</span><span class="sxs-lookup"><span data-stu-id="98973-113">If you plan to use the **Download WSDL** button on the **General** page of the **Web Service Task Editor** to download a WSDL file, type the URL for the WSDL file.</span></span> <span data-ttu-id="98973-114">Diese URL endet mit "? wsdl".</span><span class="sxs-lookup"><span data-stu-id="98973-114">This URL ends with "?wsdl".</span></span>  
  
 <span data-ttu-id="98973-115">**Anmeldeinformationen verwenden**</span><span class="sxs-lookup"><span data-stu-id="98973-115">**Use credentials**</span></span>  
 <span data-ttu-id="98973-116">Geben Sie an, ob der HTTP-Verbindungs-Manager zur Authentifizierung die Sicherheitsanmeldeinformationen des Benutzers verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="98973-116">Specify whether you want the HTTP Connection Manager to use the user's security credentials for authentication.</span></span>  
  
 <span data-ttu-id="98973-117">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="98973-117">**User name**</span></span>  
 <span data-ttu-id="98973-118">Wenn der HTTP-Verbindungs-Manager Anmeldeinformationen verwendet, müssen Sie einen Benutzernamen, ein Kennwort und eine Domäne angeben.</span><span class="sxs-lookup"><span data-stu-id="98973-118">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="98973-119">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="98973-119">**Password**</span></span>  
 <span data-ttu-id="98973-120">Wenn der HTTP-Verbindungs-Manager Anmeldeinformationen verwendet, müssen Sie einen Benutzernamen, ein Kennwort und eine Domäne angeben.</span><span class="sxs-lookup"><span data-stu-id="98973-120">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="98973-121">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="98973-121">**Domain**</span></span>  
 <span data-ttu-id="98973-122">Wenn der HTTP-Verbindungs-Manager Anmeldeinformationen verwendet, müssen Sie einen Benutzernamen, ein Kennwort und eine Domäne angeben.</span><span class="sxs-lookup"><span data-stu-id="98973-122">If the HTTP Connection Manager uses credentials, you must specify a user name, password, and domain.</span></span>  
  
 <span data-ttu-id="98973-123">**Clientzertifikat verwenden**</span><span class="sxs-lookup"><span data-stu-id="98973-123">**Use client certificate**</span></span>  
 <span data-ttu-id="98973-124">Geben Sie an, ob der HTTP-Verbindungs-Manager zur Authentifizierung ein Clientzertifikat verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="98973-124">Specify whether you want the HTTP Connection Manager to use a client certificate for authentication.</span></span>  
  
 <span data-ttu-id="98973-125">**Certificate**</span><span class="sxs-lookup"><span data-stu-id="98973-125">**Certificate**</span></span>  
 <span data-ttu-id="98973-126">Wählen Sie mithilfe des Dialogfelds **Zertifikat auswählen** ein Zertifikat aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="98973-126">Select a certificate from the list by using the **Select Certificate** dialog box.</span></span> <span data-ttu-id="98973-127">Im Textfeld wird der dem Zertifikat zugeordnete Name angezeigt.</span><span class="sxs-lookup"><span data-stu-id="98973-127">The text box displays the name associated with this certificate.</span></span>  
  
 <span data-ttu-id="98973-128">**Timeout (in Sekunden)**</span><span class="sxs-lookup"><span data-stu-id="98973-128">**Time-out (in seconds)**</span></span>  
 <span data-ttu-id="98973-129">Geben Sie ein Timeout für Verbindungen mit dem Webserver an.</span><span class="sxs-lookup"><span data-stu-id="98973-129">Provide a time-out for connecting to the Web server.</span></span> <span data-ttu-id="98973-130">Der Standardwert dieser Eigenschaft beträgt 30 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="98973-130">The default value of this property is 30 seconds.</span></span>  
  
 <span data-ttu-id="98973-131">**Segmentgröße (in KB)**</span><span class="sxs-lookup"><span data-stu-id="98973-131">**Chunk size (in KB)**</span></span>  
 <span data-ttu-id="98973-132">Geben Sie eine Segmentgröße zum Schreiben von Daten an.</span><span class="sxs-lookup"><span data-stu-id="98973-132">Provide a chunk size for writing data.</span></span>  
  
 <span data-ttu-id="98973-133">**Verbindung testen**</span><span class="sxs-lookup"><span data-stu-id="98973-133">**Test Connection**</span></span>  
 <span data-ttu-id="98973-134">Nachdem die Konfiguration des HTTP-Verbindungs-Managers abgeschlossen ist, bestätigen Sie die Gültigkeit der Verbindung, indem Sie auf **Verbindung testen**klicken.</span><span class="sxs-lookup"><span data-stu-id="98973-134">After configuring the HTTP Connection Manager, confirm that the connection is viable by clicking **Test Connection**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98973-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="98973-135">See Also</span></span>  
 <span data-ttu-id="98973-136">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="98973-136">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="98973-137">HTTP-Verbindungs-Manager-Editor &#40;Seite „Proxy“&#41;</span><span class="sxs-lookup"><span data-stu-id="98973-137">HTTP Connection Manager Editor &#40;Proxy Page&#41;</span></span>](../../2014/integration-services/http-connection-manager-editor-proxy-page.md)  
  
  
