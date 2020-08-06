---
title: Serverberechtigungen für „public“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 9a276caa-ea38-473d-92bc-26302bfcf660
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7913c4715f47b8105b72b1c817dbe77e52d40539
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724537"
---
# <a name="server-public-permissions"></a><span data-ttu-id="f6556-102">Serverberechtigungen für 'public'</span><span class="sxs-lookup"><span data-stu-id="f6556-102">Server public Permissions</span></span>
  <span data-ttu-id="f6556-103">Diese Regel bestimmt, ob die Serverrolle public Serverberechtigung besitzt.</span><span class="sxs-lookup"><span data-stu-id="f6556-103">This rule determines whether the public server role has server permissions.</span></span> <span data-ttu-id="f6556-104">Jede Anmeldung, die auf dem Server erstellt wird, ist ein Element der Serverrolle public.</span><span class="sxs-lookup"><span data-stu-id="f6556-104">Every login that is created on the server is a member of the public server role.</span></span> <span data-ttu-id="f6556-105">Wenn diese Bedingung erfüllt ist, besitzt jede Anmeldung am Server Serverberechtigung.</span><span class="sxs-lookup"><span data-stu-id="f6556-105">If this condition is met, every login on the server will have server permissions.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="f6556-106">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="f6556-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="f6556-107">Gewähren Sie der Serverrolle public keine Serverberechtigung.</span><span class="sxs-lookup"><span data-stu-id="f6556-107">Do not grant server permissions to the server public role.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f6556-108">Nachdem das Setup abgeschlossen ist, verfügt die **Public** -Rolle `CONNECT` über die Berechtigung für alle Endpunkte außer der **dedizierten Administrator Verbindung**.</span><span class="sxs-lookup"><span data-stu-id="f6556-108">After setup completes the **PUBLIC** role has `CONNECT` permission on all the endpoints except the **Dedicated Admin Connection**.</span></span> <span data-ttu-id="f6556-109">Dies ist normal und sollte üblicherweise nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="f6556-109">This is normal and should not be normally changed.</span></span> <span data-ttu-id="f6556-110">(Der Zugriff wird mit der `CONNECT SQL`-Berechtigung gesteuert, die beim Erstellen neuer Anmeldungen automatisch erteilt wird.)</span><span class="sxs-lookup"><span data-stu-id="f6556-110">(Access is controlled by using the `CONNECT SQL` permission which is automatically granted when new logins are created.)</span></span>  
  
### <a name="for-more-information"></a><span data-ttu-id="f6556-111">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="f6556-111">For more information</span></span>  
 [<span data-ttu-id="f6556-112">Sichern von SQL Server</span><span class="sxs-lookup"><span data-stu-id="f6556-112">Securing SQL Server</span></span>](../security/securing-sql-server.md)  
  
  
