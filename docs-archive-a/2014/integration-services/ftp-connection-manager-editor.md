---
title: FTP-Verbindungs-Manager-Editor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.ftpconnectionmanager.f1
helpviewer_keywords:
- FTP Connection Manager Editor
ms.assetid: 874b6585-255b-4a43-8396-bb08c3e8ac2b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d14635a4d90c267801f6d372dda5c7bcc7f4869f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727046"
---
# <a name="ftp-connection-manager-editor"></a><span data-ttu-id="e26e3-102">FTP-Verbindungs-Manager-Editor</span><span class="sxs-lookup"><span data-stu-id="e26e3-102">FTP Connection Manager Editor</span></span>
  <span data-ttu-id="e26e3-103">Mithilfe des Dialogfelds **FTP-Verbindungs-Manager-Editor** können Sie Eigenschaften für Verbindungen mit einem FTP-Server angeben.</span><span class="sxs-lookup"><span data-stu-id="e26e3-103">Use the **FTP Connection Manager Editor** dialog box to specify properties for connecting to an FTP server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e26e3-104">Der FTP-Verbindungs-Manager unterstützt nur die anonyme Authentifizierung und die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="e26e3-104">The FTP connection manager supports only anonymous authentication and basic authentication.</span></span> <span data-ttu-id="e26e3-105">Er unterstützt keine Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="e26e3-105">It does not support Windows Authentication.</span></span>  
  
 <span data-ttu-id="e26e3-106">Weitere Informationen zum FTP-Verbindungs-Manager finden Sie unter [FTP Connection Manager](connection-manager/ftp-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="e26e3-106">To learn more about the FTP connection manager, see [FTP Connection Manager](connection-manager/ftp-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e26e3-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="e26e3-107">Options</span></span>  
 <span data-ttu-id="e26e3-108">**Servername**</span><span class="sxs-lookup"><span data-stu-id="e26e3-108">**Server name**</span></span>  
 <span data-ttu-id="e26e3-109">Geben Sie den Namen des FTP-Servers an.</span><span class="sxs-lookup"><span data-stu-id="e26e3-109">Provide the name of the FTP server.</span></span>  
  
 <span data-ttu-id="e26e3-110">**Serverport**</span><span class="sxs-lookup"><span data-stu-id="e26e3-110">**Server port**</span></span>  
 <span data-ttu-id="e26e3-111">Geben Sie die Portnummer des FTP-Servers an, der für die Verbindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e26e3-111">Specify the port number on the FTP server to use for the connection.</span></span> <span data-ttu-id="e26e3-112">Der Standardwert dieser Eigenschaft ist **21**.</span><span class="sxs-lookup"><span data-stu-id="e26e3-112">The default value of this property is **21**.</span></span>  
  
 <span data-ttu-id="e26e3-113">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="e26e3-113">**User name**</span></span>  
 <span data-ttu-id="e26e3-114">Geben Sie einen Benutzernamen für den Zugriff auf den FTP-Server an.</span><span class="sxs-lookup"><span data-stu-id="e26e3-114">Provide a user name to access the FTP server.</span></span> <span data-ttu-id="e26e3-115">Der Standardwert dieser Eigenschaft ist **anonymous**.</span><span class="sxs-lookup"><span data-stu-id="e26e3-115">The default value of this property is **anonymous**.</span></span>  
  
 <span data-ttu-id="e26e3-116">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="e26e3-116">**Password**</span></span>  
 <span data-ttu-id="e26e3-117">Geben Sie das Kennwort für den Zugriff auf den FTP-Server an.</span><span class="sxs-lookup"><span data-stu-id="e26e3-117">Provide the password to access the FTP server.</span></span>  
  
 <span data-ttu-id="e26e3-118">**Timeout (in Sekunden)**</span><span class="sxs-lookup"><span data-stu-id="e26e3-118">**Time-out (in seconds)**</span></span>  
 <span data-ttu-id="e26e3-119">Geben Sie die Anzahl von Sekunden an, die der Task vor einem Timeout dauert. Der Wert **0** gibt einen unbegrenzten Zeitraum an.</span><span class="sxs-lookup"><span data-stu-id="e26e3-119">Specify the number of seconds the task takes before timing out. A value of **0** indicates an infinite amount of time.</span></span> <span data-ttu-id="e26e3-120">Der Standardwert dieser Eigenschaft ist **60**.</span><span class="sxs-lookup"><span data-stu-id="e26e3-120">The default value of this property is **60**.</span></span>  
  
 <span data-ttu-id="e26e3-121">**Passivmodus verwenden**</span><span class="sxs-lookup"><span data-stu-id="e26e3-121">**Use passive mode**</span></span>  
 <span data-ttu-id="e26e3-122">Geben Sie an, ob die Verbindung durch den Server oder durch den Client initiiert wird.</span><span class="sxs-lookup"><span data-stu-id="e26e3-122">Specify whether the server or the client initiates the connection.</span></span> <span data-ttu-id="e26e3-123">Die Initiierung der Verbindung durch den Server erfolgt im Aktivmodus; der Client aktiviert die Verbindung im Passivmodus.</span><span class="sxs-lookup"><span data-stu-id="e26e3-123">The server initiates the connection in active mode, and the client activates the connection in passive mode.</span></span> <span data-ttu-id="e26e3-124">Der Standardwert dieser Eigenschaft ist der **Aktivmodus**.</span><span class="sxs-lookup"><span data-stu-id="e26e3-124">The default value of this property is **active mode**.</span></span>  
  
 <span data-ttu-id="e26e3-125">**Wiederholungsversuche**</span><span class="sxs-lookup"><span data-stu-id="e26e3-125">**Retries**</span></span>  
 <span data-ttu-id="e26e3-126">Geben Sie die Häufigkeit an, mit der der Task versucht, eine Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="e26e3-126">Specify the number of times the task attempts to make a connection.</span></span> <span data-ttu-id="e26e3-127">Der Wert **0** gibt eine unbegrenzte Anzahl von Versuchen an.</span><span class="sxs-lookup"><span data-stu-id="e26e3-127">A value of **0** indicates no limit to the number of attempts.</span></span>  
  
 <span data-ttu-id="e26e3-128">**Segmentgröße (in KB)**</span><span class="sxs-lookup"><span data-stu-id="e26e3-128">**Chunk size (in KB)**</span></span>  
 <span data-ttu-id="e26e3-129">Geben Sie eine Segmentgröße in KB für das Übertragen von Daten an.</span><span class="sxs-lookup"><span data-stu-id="e26e3-129">Provide a chunk size in kilobytes for transmitting data.</span></span>  
  
 <span data-ttu-id="e26e3-130">**Verbindung testen**</span><span class="sxs-lookup"><span data-stu-id="e26e3-130">**Test Connection**</span></span>  
 <span data-ttu-id="e26e3-131">Nachdem die Konfiguration des FTP-Verbindungs-Managers abgeschlossen ist, bestätigen Sie die Gültigkeit der Verbindung, indem Sie auf **Verbindung testen**klicken.</span><span class="sxs-lookup"><span data-stu-id="e26e3-131">After configuring the FTP Connection Manager, confirm that the connection is viable by clicking **Test Connection**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e26e3-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e26e3-132">See Also</span></span>  
 [<span data-ttu-id="e26e3-133">Fehler- und Meldungsreferenz von Integration Services</span><span class="sxs-lookup"><span data-stu-id="e26e3-133">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
