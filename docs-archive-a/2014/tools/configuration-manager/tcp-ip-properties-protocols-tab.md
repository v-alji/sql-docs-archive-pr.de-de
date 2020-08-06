---
title: TCP/IP-Eigenschaften (Registerkarte Protokolle) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- TCP/IP [SQL Server], configuration options
ms.assetid: 007638fc-3a24-4460-adbe-545ded5d6f88
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1d5bc28faddae9a86a6636b56b907b57a2d8711a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608996"
---
# <a name="tcp---ip-properties-protocols-tab"></a><span data-ttu-id="c5e4d-102">TCP/IP-Eigenschaften (Registerkarte Protokolle)</span><span class="sxs-lookup"><span data-stu-id="c5e4d-102">TCP - IP Properties (Protocols Tab)</span></span>
  <span data-ttu-id="c5e4d-103">Verwenden Sie das Dialogfeld **TCP/IP-Eigenschaften** zum Konfigurieren der Optionen für das TCP/IP-Protokoll.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-103">Use the **TCP/IP Properties** dialog box to configure the options for the TCP/IP protocol.</span></span> <span data-ttu-id="c5e4d-104">Klicken Sie im linken Bereich auf **TCP/IP** , um die einzelnen IP-Adresskonfigurationen im Detailbereich anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-104">Click **TCP/IP** in the left pane, to show individual IP address configurations in the details pane.</span></span>  
  
 <span data-ttu-id="c5e4d-105">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] muss neu gestartet werden, damit die Änderungen in Kraft treten.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-105">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be restarted before the changes take effect.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c5e4d-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c5e4d-106">Options</span></span>  
 <span data-ttu-id="c5e4d-107">**Aktiviert**</span><span class="sxs-lookup"><span data-stu-id="c5e4d-107">**Enabled**</span></span>  
 <span data-ttu-id="c5e4d-108">Mögliche Werte sind **Yes** und **No**.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-108">Possible values are **Yes** and **No**.</span></span>  
  
 <span data-ttu-id="c5e4d-109">**Keep Alive**</span><span class="sxs-lookup"><span data-stu-id="c5e4d-109">**Keep Alive**</span></span>  
 <span data-ttu-id="c5e4d-110">Geben Sie das Intervall (in Millisekunden) an, in dem Erhaltungspakete übertragen werden, die die Verfügbarkeit des Computers an der Remoteseite der Verbindung sicherstellen.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-110">Specify the interval (milliseconds) in which keep-alive packets are transmitted to verify that the computer at the remote end of a connection is still available.</span></span>  
  
 <span data-ttu-id="c5e4d-111">**Listen All**</span><span class="sxs-lookup"><span data-stu-id="c5e4d-111">**Listen All**</span></span>  
 <span data-ttu-id="c5e4d-112">Specify whether SQL Server will listen on all the IP addresses that are bound to network cards on the computer.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-112">Specify whether SQL Server will listen on all the IP addresses that are bound to network cards on the computer.</span></span> <span data-ttu-id="c5e4d-113">Wenn für diese Option **Nein**festgelegt ist, müssen Sie jede IP-Adresse einzeln mithilfe des Dialogfeldes „Eigenschaften“ für jede IP-Adresse konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-113">If set to **No**, configure each IP address separately using the properties dialog box for each IP address.</span></span> <span data-ttu-id="c5e4d-114">Wenn für diese Option **Ja**festgelegt ist, gelten die Einstellungen des Eigenschaftenfeldes **IPAll** für alle IP-Adressen.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-114">If set to **Yes**, the settings of the **IPAll** properties box will apply to all IP addresses.</span></span> <span data-ttu-id="c5e4d-115">Der Standardwert ist **Ja**.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-115">Default value is **Yes**.</span></span>  
  
 <span data-ttu-id="c5e4d-116">**No Delay**</span><span class="sxs-lookup"><span data-stu-id="c5e4d-116">**No Delay**</span></span>  
 <span data-ttu-id="c5e4d-117">Von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] werden keine Änderungen an dieser Eigenschaft implementiert.</span><span class="sxs-lookup"><span data-stu-id="c5e4d-117">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not implement changes to this property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5e4d-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c5e4d-118">See Also</span></span>  
 <span data-ttu-id="c5e4d-119">[Auswählen eines Netzwerkprotokolls](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span><span class="sxs-lookup"><span data-stu-id="c5e4d-119">[Choosing a Network Protocol](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md) </span></span>  
 [<span data-ttu-id="c5e4d-120">Erstellen einer gültigen Verbindungszeichenfolge mithilfe von TCP/IP</span><span class="sxs-lookup"><span data-stu-id="c5e4d-120">Creating a Valid Connection String Using TCP IP</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
  
