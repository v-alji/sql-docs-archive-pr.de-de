---
title: MSSQLSERVER_26014 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 26014 (Database Engine error)
ms.assetid: e2b0dfc7-0681-4e5d-8875-1d5f63534086
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8114183b212767d01013eee9387d8b2efa2e0d7f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618037"
---
# <a name="mssqlserver_26014"></a><span data-ttu-id="aa707-102">MSSQLSERVER_26014</span><span class="sxs-lookup"><span data-stu-id="aa707-102">MSSQLSERVER_26014</span></span>
    
## <a name="details"></a><span data-ttu-id="aa707-103">Details</span><span class="sxs-lookup"><span data-stu-id="aa707-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="aa707-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="aa707-104">Product Name</span></span>|<span data-ttu-id="aa707-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="aa707-105">SQL Server</span></span>|  
|<span data-ttu-id="aa707-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="aa707-106">Event ID</span></span>|<span data-ttu-id="aa707-107">26014</span><span class="sxs-lookup"><span data-stu-id="aa707-107">26014</span></span>|  
|<span data-ttu-id="aa707-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="aa707-108">Event Source</span></span>|<span data-ttu-id="aa707-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="aa707-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="aa707-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="aa707-110">Component</span></span>|<span data-ttu-id="aa707-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="aa707-111">SQLEngine</span></span>|  
|<span data-ttu-id="aa707-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="aa707-112">Symbolic Name</span></span>|<span data-ttu-id="aa707-113">SNI_SSL_USER_CERT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="aa707-113">SNI_SSL_USER_CERT_FAILURE</span></span>|  
|<span data-ttu-id="aa707-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="aa707-114">Message Text</span></span>|<span data-ttu-id="aa707-115">Das vom Benutzer angegebene Zertifikat [Cert Hash(sha1) "%hs"] kann nicht geladen werden.</span><span class="sxs-lookup"><span data-stu-id="aa707-115">Unable to load user-specified certificate [Cert Hash(sha1) "%hs"].</span></span> <span data-ttu-id="aa707-116">Vom Server wird keine Verbindung akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="aa707-116">The server will not accept a connection.</span></span> <span data-ttu-id="aa707-117">Überprüfen Sie, ob das Zertifikat richtig installiert ist.</span><span class="sxs-lookup"><span data-stu-id="aa707-117">You should verify that the certificate is correctly installed.</span></span> <span data-ttu-id="aa707-118">Lesen Sie "Konfigurieren eines Zertifikats zur Verwendung durch SSL" in der Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="aa707-118">See "Configuring Certificate for Use by SSL" in Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="aa707-119">Erklärung</span><span class="sxs-lookup"><span data-stu-id="aa707-119">Explanation</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="aa707-120">hat versucht, das in der Meldung genannte Zertifikat zu laden, aber bei dem Vorgang ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="aa707-120">attempted to load the certificate named in the message but the operation failed.</span></span> <span data-ttu-id="aa707-121">Dieses Problem muss behoben werden, bevor [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dieses Zertifikat verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="aa707-121">This problem must be resolved before [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can use this certificate.</span></span>  
  
 <span data-ttu-id="aa707-122">Zu den möglichen Ursachen für den Fehler zählen die folgenden:</span><span class="sxs-lookup"><span data-stu-id="aa707-122">Possible causes of the error include:</span></span>  
  
-   <span data-ttu-id="aa707-123">Möglicherweise wurde das Zertifikat verschoben oder gelöscht.</span><span class="sxs-lookup"><span data-stu-id="aa707-123">The certificate could have been moved or deleted.</span></span>  
  
-   <span data-ttu-id="aa707-124">Falls sich der von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendete Anmeldename geändert hat, verfügt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] möglicherweise nicht über die Berechtigung für den Zugriff auf das Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="aa707-124">If the login used by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] has changed, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] may not have permission to access the certificate.</span></span>  
  
-   <span data-ttu-id="aa707-125">Das Zertifikat ist möglicherweise abgelaufen.</span><span class="sxs-lookup"><span data-stu-id="aa707-125">The certificate may have expired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="aa707-126">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="aa707-126">User Action</span></span>  
 <span data-ttu-id="aa707-127">Stellen Sie sicher, dass das in der Meldung genannte Zertifikat im System vorhanden ist, dass darauf zugegriffen werden kann und dass es für die Verwendung zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="aa707-127">Make sure the certificate named in the message exists on the system, is accessible, and it is valid for use.</span></span>  
  
  
