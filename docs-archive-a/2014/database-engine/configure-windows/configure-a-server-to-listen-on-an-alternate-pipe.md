---
title: Konfigurieren eines Servers für das lauschen an einer alternativen Pipe (SQL Server-Konfigurations-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Named Pipes [SQL Server], configuring
- listening [SQL Server], pipes
- pipes [SQL Server], alternate
- alternate pipes [SQL Server]
ms.assetid: 914f7491-e2be-4b0d-b3aa-fe5409cdbafa
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 57d70cf4cd1d7474b895aeb8cb144c885e8a0f99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608848"
---
# <a name="configure-a-server-to-listen-on-an-alternate-pipe-sql-server-configuration-manager"></a><span data-ttu-id="b8272-102">Konfigurieren eines Servers für die Überwachung einer alternativen Pipe (SQL Server-Konfigurations-Manager)</span><span class="sxs-lookup"><span data-stu-id="b8272-102">Configure a Server to Listen on an Alternate Pipe (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="b8272-103">In diesem Thema wird beschrieben, wie Sie einen Server konfigurieren können, um eine alternative Pipe in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe des SQL Server-Konfigurations-Managers überwachen zu können.</span><span class="sxs-lookup"><span data-stu-id="b8272-103">This topic describes how to configure a server to listen on an alternate pipe in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="b8272-104">Standardmäßig lauscht die Standardinstanz von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] an der Named Pipe \\\\.\pipe\sql\query.</span><span class="sxs-lookup"><span data-stu-id="b8272-104">By default, the default instance of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] listens on named pipe \\\\.\pipe\sql\query.</span></span> <span data-ttu-id="b8272-105">Benannte Instanzen von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] und [!INCLUDE[ssEW](../../includes/ssew-md.md)] überwachen andere Pipes.</span><span class="sxs-lookup"><span data-stu-id="b8272-105">Named instances of [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] and [!INCLUDE[ssEW](../../includes/ssew-md.md)] listen on other pipes.</span></span>  
  
 <span data-ttu-id="b8272-106">Es gibt drei Möglichkeiten, mit einer Clientanwendung eine Verbindung mit einer bestimmten benannten Pipe herzustellen:</span><span class="sxs-lookup"><span data-stu-id="b8272-106">There are three ways to connect to a specific named pipe with a client application:</span></span>  
  
-   <span data-ttu-id="b8272-107">Ausführen des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browser-Dienstes auf dem Server</span><span class="sxs-lookup"><span data-stu-id="b8272-107">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service on the server.</span></span>  
  
-   <span data-ttu-id="b8272-108">Erstellen eines Alias auf dem Client unter Angabe der benannten Pipe</span><span class="sxs-lookup"><span data-stu-id="b8272-108">Create an alias on the client, specifying the named pipe.</span></span>  
  
-   <span data-ttu-id="b8272-109">Programmieren Sie den Client so, dass die Verbindung mithilfe einer benutzerdefinierten Verbindungszeichenfolge hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b8272-109">Program the client to connect using a custom connection string.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="b8272-110">Verwenden des SQL Server-Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="b8272-110">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-configure-the-named-pipe-used-by-the-sql-server-database-engine"></a><span data-ttu-id="b8272-111">So konfigurieren Sie die von der SQL Server-Datenbank-Engine verwendete Named Pipe</span><span class="sxs-lookup"><span data-stu-id="b8272-111">To configure the named pipe used by the SQL Server Database Engine</span></span>  
  
1.  <span data-ttu-id="b8272-112">Erweitern Sie im SQL Server-Konfigurations-Manager im Konsolenbereich **SQL Server-Netzwerkkonfiguration**, und klicken Sie dann auf **Protokolle für** *\<instance name>* .</span><span class="sxs-lookup"><span data-stu-id="b8272-112">In SQL Server Configuration Manager, in the console pane, expand **SQL Server Network Configuration**, and then click expand **Protocols for** *\<instance name>*.</span></span>  
  
2.  <span data-ttu-id="b8272-113">Klicken Sie im Detailbereich mit der rechten Maustaste auf **Named Pipes**, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b8272-113">In the details pane, right-click **Named Pipes**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="b8272-114">Geben Sie auf der Registerkarte **Protokoll** im Feld **Pipename** die Pipe ein, an der [!INCLUDE[ssDE](../../includes/ssde-md.md)] gelauscht werden soll, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b8272-114">On the **Protocol** tab, in the **Pipe Name** box, type the pipe you want the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to listen on, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="b8272-115">Klicken Sie im linken Bereich auf **SQL Server-Dienste**.</span><span class="sxs-lookup"><span data-stu-id="b8272-115">In the console pane, click **SQL Server Services**.</span></span>  
  
5.  <span data-ttu-id="b8272-116">Klicken Sie im Detailbereich mit der rechten Maustaste auf **SQL Server (** \<instance name> **)** , und klicken Sie dann auf **Neu starten**, um den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienst zu beenden und neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="b8272-116">In the details pane, right-click **SQL Server (**\<instance name>**)** and then click **Restart**, to stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="b8272-117">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine alternative Pipe überwacht, können Sie auf drei Arten mit einer Clientanwendung eine Verbindung zu einer bestimmten benannten Pipe herstellen:</span><span class="sxs-lookup"><span data-stu-id="b8272-117">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is listening on an alternate pipe, there are three ways to connect to a specific named pipe with a client application:</span></span>  
  
-   <span data-ttu-id="b8272-118">Ausführen des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browser-Dienstes auf dem Server</span><span class="sxs-lookup"><span data-stu-id="b8272-118">Run the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser service on the server.</span></span>  
  
-   <span data-ttu-id="b8272-119">Erstellen eines Alias auf dem Client unter Angabe der benannten Pipe</span><span class="sxs-lookup"><span data-stu-id="b8272-119">Create an alias on the client, specifying the named pipe.</span></span>  
  
-   <span data-ttu-id="b8272-120">Programmieren Sie den Client so, dass die Verbindung mithilfe einer benutzerdefinierten Verbindungszeichenfolge hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b8272-120">Program the client to connect using a custom connection string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8272-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b8272-121">See Also</span></span>  
 <span data-ttu-id="b8272-122">[Erstellen oder Löschen eines Serveralias für die Verwendung durch einen Client &#40;SQL Server-Konfigurations-Manager&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md) </span><span class="sxs-lookup"><span data-stu-id="b8272-122">[Create or Delete a Server Alias for Use by a Client &#40;SQL Server Configuration Manager&#41;](create-or-delete-a-server-alias-for-use-by-a-client.md) </span></span>  
 [<span data-ttu-id="b8272-123">Server-Netzwerkkonfiguration</span><span class="sxs-lookup"><span data-stu-id="b8272-123">Server Network Configuration</span></span>](server-network-configuration.md)  
  
  
