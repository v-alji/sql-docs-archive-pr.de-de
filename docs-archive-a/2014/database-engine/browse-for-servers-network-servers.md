---
title: Nach Servern suchen (Netzwerkserver) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
f1_keywords:
- sql12.swb.browseservers.network.f1
ms.assetid: a59ffcd6-4b69-4c5c-9740-699ccb2183fb
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 0ba5e4e5dd6d9a6541a98e0cb30229d7335bac24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619372"
---
# <a name="browse-for-servers-network-servers"></a><span data-ttu-id="f8ba4-102">Nach Servern suchen (Netzwerkserver)</span><span class="sxs-lookup"><span data-stu-id="f8ba4-102">Browse for Servers (Network Servers)</span></span>
  <span data-ttu-id="f8ba4-103">Wenn Sie eine Verbindung mit einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Komponente herstellen und nicht den genauen Namen der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Instanz kennen, klicken Sie im Feld **Servername** auf **Suche fortsetzen** , um das Dialogfeld **Nach Servern suchen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f8ba4-103">If you are connecting to a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] component and you do not know the exact name of the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance, click **Browse for more** in the **Server name** box to open the **Browse for Servers** dialog box.</span></span>  
  
 <span data-ttu-id="f8ba4-104">Dieses Dialogfeld wird vom [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Browser-Dienst aufgefüllt, sofern dieser auf den Servercomputern ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f8ba4-104">This dialog is populated by the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Browser service on the server computers.</span></span> <span data-ttu-id="f8ba4-105">Es gibt mehrere Gründe, warum der Name einer Instanz ggf. nicht in der Liste angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="f8ba4-105">There are several reasons why the name of an instance might not appear in the list:</span></span>  
  
-   <span data-ttu-id="f8ba4-106">Der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Browser-Dienst wird auf dem Computer, auf dem [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]ausgeführt wird, möglicherweise nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f8ba4-106">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Browser service might not be running on the computer running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="f8ba4-107">UDP-Port 1434 wird möglicherweise von einer Firewall blockiert.</span><span class="sxs-lookup"><span data-stu-id="f8ba4-107">UDP port 1434 might be blocked by a firewall.</span></span>  
  
-   <span data-ttu-id="f8ba4-108">Das **HideInstance** -Flag wurde möglicherweise festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f8ba4-108">The **HideInstance** flag might be set.</span></span>  
  
 <span data-ttu-id="f8ba4-109">Um eine Verbindung mit einer Instanz herzustellen, die nicht in der Liste angezeigt wird, geben Sie eine vollständige Verbindungszeichenfolge für die Instanz ein, einschließlich der TCP/IP-Portnummer oder des Pipenamens der Named Pipes.</span><span class="sxs-lookup"><span data-stu-id="f8ba4-109">To connect to an instance that does not appear in the list, type a full connection string for the instance, including the TCP/IP port number or the named pipes pipe name.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f8ba4-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f8ba4-110">Options</span></span>  
 <span data-ttu-id="f8ba4-111">**Wählen Sie für Ihre Verbindung eine SQL Server-Instanz im Netzwerk aus**</span><span class="sxs-lookup"><span data-stu-id="f8ba4-111">**Select a SQL Server instance in the network for your connection**</span></span>  
 <span data-ttu-id="f8ba4-112">Legen Sie den Server fest, zu dem eine Verbindung hergestellt werden soll, indem Sie auf die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Instanz klicken, die in der Baumstruktur angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f8ba4-112">Designate the server you want to connect to by clicking on the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] instance displayed in the tree.</span></span> <span data-ttu-id="f8ba4-113">Sie können Teile der Strukturansicht ein-oder ausblenden, indem Sie auf die Knoten klicken, die mit einem-oder-Symbol gekennzeichnet sind **+** **-** .</span><span class="sxs-lookup"><span data-stu-id="f8ba4-113">You can show or hide portions of the tree view by clicking on the nodes marked with a **+** or **-** symbol.</span></span>  
  
  
