---
title: SMTP-Verbindungs-Manager-Editor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.smtpconnection.f1
helpviewer_keywords:
- SMTP Connection Manager Editor
ms.assetid: 2693de0d-b04d-4325-a856-ce667d2b8aa1
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e14ed49f64b9faca40f575fc6760a8d25c0d4573
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726029"
---
# <a name="smtp-connection-manager-editor"></a><span data-ttu-id="90c93-102">SMTP-Verbindungs-Manager-Editor</span><span class="sxs-lookup"><span data-stu-id="90c93-102">SMTP Connection Manager Editor</span></span>
  <span data-ttu-id="90c93-103">Mithilfe des Dialogfelds **SMTP-Verbindungs-Manager-Editor** können Sie einen SMTP-Server (Simple Mail Transfer Protocol) angeben.</span><span class="sxs-lookup"><span data-stu-id="90c93-103">Use the **SMTP Connection Manager Editor** dialog box to specify a Simple Mail Transfer Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="90c93-104">Weitere Informationen zum SMTP-Verbindungs-Manager finden Sie unter [SMTP Connection Manager](connection-manager/smtp-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="90c93-104">To learn more about the SMTP connection manager, see [SMTP Connection Manager](connection-manager/smtp-connection-manager.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="90c93-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="90c93-105">Options</span></span>  
 <span data-ttu-id="90c93-106">**Name**</span><span class="sxs-lookup"><span data-stu-id="90c93-106">**Name**</span></span>  
 <span data-ttu-id="90c93-107">Geben Sie einen eindeutigen Namen für den Verbindungs-Manager an.</span><span class="sxs-lookup"><span data-stu-id="90c93-107">Provide a unique name for the connection manager.</span></span>  
  
 <span data-ttu-id="90c93-108">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="90c93-108">**Description**</span></span>  
 <span data-ttu-id="90c93-109">Beschreiben Sie den Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="90c93-109">Describe the connection manager.</span></span> <span data-ttu-id="90c93-110">Die bewährte Methode ist hierbei, den Verbindungs-Manager zweckbezogen zu beschreiben, sodass Pakete selbsterklärend und leichter zu verwalten sind.</span><span class="sxs-lookup"><span data-stu-id="90c93-110">As a best practice, describe the connection manager in terms of its purpose, to make packages self-documenting and easier to maintain.</span></span>  
  
 <span data-ttu-id="90c93-111">**SMTP-Server**</span><span class="sxs-lookup"><span data-stu-id="90c93-111">**SMTP server**</span></span>  
 <span data-ttu-id="90c93-112">Geben Sie den Namen des SMTP-Servers an.</span><span class="sxs-lookup"><span data-stu-id="90c93-112">Provide the name of the SMTP server.</span></span>  
  
 <span data-ttu-id="90c93-113">**Windows-Authentifizierung verwenden**</span><span class="sxs-lookup"><span data-stu-id="90c93-113">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="90c93-114">Wählen Sie diese Option aus, um E-Mail über einen SMTP-Server zu senden, der zum Authentifizieren des Zugriffs auf den Server die Windows-Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="90c93-114">Select to send mail using an SMTP server that uses Windows Authentication to authenticate access to the server.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="90c93-115">Der SMTP-Verbindungs-Manager unterstützt nur die anonyme Authentifizierung und die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="90c93-115">The SMTP connection manager supports only anonymous authentication and Windows Authentication.</span></span> <span data-ttu-id="90c93-116">Er unterstützt keine Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="90c93-116">It does not support basic authentication.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="90c93-117">Wenn Sie Microsoft Exchange als SMTP-Server verwenden, müssen Sie möglicherweise die **Windows-Authentifizierung verwenden** auf festlegen `True` .</span><span class="sxs-lookup"><span data-stu-id="90c93-117">When using Microsoft Exchange as the SMTP server, you may need to set **Use Windows Authentication** to `True`.</span></span> <span data-ttu-id="90c93-118">Exchange-Server können so konfiguriert sein, dass keine nicht authentifizierten SMTP-Verbindungen zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="90c93-118">Exchange servers may be configured to disallow unauthenticated SMTP connections.</span></span>  
  
 <span data-ttu-id="90c93-119">**Secure Sockets Layer (SSL) aktivieren**</span><span class="sxs-lookup"><span data-stu-id="90c93-119">**Enable Secure Sockets Layer (SSL)**</span></span>  
 <span data-ttu-id="90c93-120">Wählen Sie diese Option aus, um beim Senden von E-Mail-Nachrichten die Kommunikation mit SSL (Secure Sockets Layer) zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="90c93-120">Select to encrypt communication using Secure Sockets Layer (SSL) when sending e-mail messages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90c93-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90c93-121">See Also</span></span>  
 [<span data-ttu-id="90c93-122">Fehler- und Meldungsreferenz von Integration Services</span><span class="sxs-lookup"><span data-stu-id="90c93-122">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
