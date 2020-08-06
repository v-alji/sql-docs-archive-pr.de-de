---
title: Registrieren von verbundenen Servern
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- sql12.swb.registerserver.f1
helpviewer_keywords:
- Registered Servers [SQL Server], register connected servers
- connected server registrations [SQL Server]
ms.assetid: 77deb5f5-0f80-484f-8b8b-29afa67ec18f
author: markingmyname
ms.author: maghan
ms.openlocfilehash: 1d337d2da7d305165307745fb02526e37b53bbd3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616314"
---
# <a name="register-a-connected-server-sql-server-management-studio"></a><span data-ttu-id="45f1f-102">Registrieren eines verbundenen Servers (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="45f1f-102">Register a Connected Server (SQL Server Management Studio)</span></span>
  <span data-ttu-id="45f1f-103">In diesem Thema wird beschrieben, wie Sie in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]Server registrieren.</span><span class="sxs-lookup"><span data-stu-id="45f1f-103">This topic describes how to register servers in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="45f1f-104">Indem Sie den Server registrieren, können Sie die Verbindungsinformationen für Server, auf die Sie häufig zugreifen, speichern.</span><span class="sxs-lookup"><span data-stu-id="45f1f-104">By registering the server, you can save the connection information for servers that you access frequently.</span></span> <span data-ttu-id="45f1f-105">Ein Server kann vor dem Verbinden oder bei der Verbindung im Objekt-Explorer registriert werden.</span><span class="sxs-lookup"><span data-stu-id="45f1f-105">A server can be registered before connecting, or at the time of connection from Object Explorer.</span></span>  
  
 <span data-ttu-id="45f1f-106">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="45f1f-106">**In This Topic**</span></span>  
  
-   <span data-ttu-id="45f1f-107">**So registrieren Sie einen Server mit**</span><span class="sxs-lookup"><span data-stu-id="45f1f-107">**To register a server, using:**</span></span>  
  
     [<span data-ttu-id="45f1f-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="45f1f-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="45f1f-109">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="45f1f-109">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-register-a-connected-server"></a><span data-ttu-id="45f1f-110">So registrieren Sie einen Server</span><span class="sxs-lookup"><span data-stu-id="45f1f-110">To register a connected server</span></span>  
  
1.  <span data-ttu-id="45f1f-111">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf einen Server, zu dem Sie bereits eine Verbindung hergestellt haben, und klicken Sie dann auf **Registrieren**.</span><span class="sxs-lookup"><span data-stu-id="45f1f-111">In Object Explorer, right-click a server to which you already are connected, and then click **Register**.</span></span>  
  
     <span data-ttu-id="45f1f-112">**Servername**</span><span class="sxs-lookup"><span data-stu-id="45f1f-112">**Server name**</span></span>  
     <span data-ttu-id="45f1f-113">Geben Sie den Namen ein, der für den registrierten Server verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="45f1f-113">Enter the name you want to use for the registered server.</span></span> <span data-ttu-id="45f1f-114">Mit dem Registrieren eines lokalen oder eines Remoteservers mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] können Sie die Serververbindungsinformationen für spätere Verbindungen speichern.</span><span class="sxs-lookup"><span data-stu-id="45f1f-114">Registering a local or remote server using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] lets you store the server connection information for future connections.</span></span> <span data-ttu-id="45f1f-115">Als Standardwert wird in diesem Feld der Servername verwendet, den Sie bei der Verbindung zum Server eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="45f1f-115">This field defaults to the server name entered when you were connecting to the server.</span></span> <span data-ttu-id="45f1f-116">Sie können diesen Servernamen beibehalten oder einen anderen leicht verwendbaren Namen für den Server eingeben.</span><span class="sxs-lookup"><span data-stu-id="45f1f-116">You can retain this server name or enter another easy-to-use name for the server.</span></span>  
  
     <span data-ttu-id="45f1f-117">**Serverbeschreibung**</span><span class="sxs-lookup"><span data-stu-id="45f1f-117">**Server description**</span></span>  
     <span data-ttu-id="45f1f-118">Geben Sie eine optionale Beschreibung des Servers ein.</span><span class="sxs-lookup"><span data-stu-id="45f1f-118">Enter an optional description of the server.</span></span> <span data-ttu-id="45f1f-119">Es können maximal 250 Zeichen eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="45f1f-119">The maximum number of characters allowed is 250.</span></span>  
  
     <span data-ttu-id="45f1f-120">**Wählen Sie eine Servergruppe aus**</span><span class="sxs-lookup"><span data-stu-id="45f1f-120">**Select a server group**</span></span>  
     <span data-ttu-id="45f1f-121">Wählen Sie die Servergruppe aus, in der die Serverregistrierung gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="45f1f-121">Select the server group where you want to save the server registration.</span></span>  
  
     <span data-ttu-id="45f1f-122">**Neue Gruppe**</span><span class="sxs-lookup"><span data-stu-id="45f1f-122">**New Group**</span></span>  
     <span data-ttu-id="45f1f-123">Klicken Sie auf diese Option, um das Dialogfeld **Neue Gruppe** zu öffnen, mit dem Sie eine neue Servergruppe für den registrierten Server erstellen können.</span><span class="sxs-lookup"><span data-stu-id="45f1f-123">Click to launch the **New Group** dialog box, where you can create a new server group for the registered server.</span></span>  
  
     <span data-ttu-id="45f1f-124">**Speichern**</span><span class="sxs-lookup"><span data-stu-id="45f1f-124">**Save**</span></span>  
     <span data-ttu-id="45f1f-125">Speichert die von Ihnen eingegebenen Informationen und erstellt einen registrierten Server.</span><span class="sxs-lookup"><span data-stu-id="45f1f-125">Click to save the information you have entered and create a registered server.</span></span>  
  
  
