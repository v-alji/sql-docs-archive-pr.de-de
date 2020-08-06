---
title: Hilfe zu SQL Server-Konfigurations-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Configuration Manager, help
ms.assetid: 6e909911-39a6-469b-b22a-3afdfd08a30b
author: stevestein
ms.author: sstein
ms.openlocfilehash: 10a6d6052fe109892f975774a1ed65b818ef0581
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722097"
---
# <a name="sql-server-configuration-manager-help"></a><span data-ttu-id="2ab6c-102">Hilfe zu SQL Server-Konfigurations-Manager</span><span class="sxs-lookup"><span data-stu-id="2ab6c-102">SQL Server Configuration Manager Help</span></span>
  <span data-ttu-id="2ab6c-103">Verwenden Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager zum Konfigurieren von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Diensten und Netzwerkkonnektivität.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-103">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager to configure [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services and configure network connectivity.</span></span> <span data-ttu-id="2ab6c-104">Zum Erstellen und Verwalten von Datenbankobjekten, dem Konfigurieren der Sicherheit und dem Erstellen von [!INCLUDE[tsql](../../includes/tsql-md.md)] -Abfragen verwenden Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ab6c-104">To create or manage database objects, configure security, and write [!INCLUDE[tsql](../../includes/tsql-md.md)] queries, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="2ab6c-105">Weitere Informationen über [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]finden Sie in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-105">For more information about [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], see [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
 <span data-ttu-id="2ab6c-106">Dieser Abschnitt enthält die F1-Hilfethemen für die Dialogfelder in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-106">This section contains the F1 Help topics for the dialogs in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2ab6c-107">Mit dem Konfigurations-Manager können keine Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vor [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-107">Configuration Manager cannot configure versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] earlier than [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
## <a name="services"></a><span data-ttu-id="2ab6c-108">Dienste</span><span class="sxs-lookup"><span data-stu-id="2ab6c-108">Services</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2ab6c-109">-Konfigurations-Manager werden Dienste im Zusammenhang mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2ab6c-109">Configuration Manager manages services that are related to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="2ab6c-110">Obwohl viele dieser Aufgaben mithilfe des Dialogfensters Windows-Dienst von [!INCLUDE[msCoName](../../includes/msconame-md.md)] abgeschlossen werden können, ist der folgende Hinweis wichtig: Von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager werden zusätzliche Vorgänge auf den Diensten ausgeführt, die vom Konfigurations-Manager verwaltet werden, beispielsweise das Anwenden der zutreffenden Berechtigungen beim Ändern des Dienstkontos.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-110">Although many of these tasks can be accomplished using the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows Services dialog, is important to note that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager performs additional operations on the services it manages, such as applying the correct permissions when the service account is changed.</span></span> <span data-ttu-id="2ab6c-111">Das Verwenden des normalen Dialogfensters Windows-Dienste zum Konfigurieren von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Diensten kann unter Umständen zu Fehlfunktionen des Diensts führen.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-111">Using the normal Windows Services dialog to configure any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services might cause the service to malfunction.</span></span>  
  
 <span data-ttu-id="2ab6c-112">Verwenden Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager für die folgenden Aufgaben für Dienste:</span><span class="sxs-lookup"><span data-stu-id="2ab6c-112">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager for the following tasks for services:</span></span>  
  
-   <span data-ttu-id="2ab6c-113">Starten, Beenden und Anhalten von Diensten</span><span class="sxs-lookup"><span data-stu-id="2ab6c-113">Start, stop, and pause services</span></span>  
  
-   <span data-ttu-id="2ab6c-114">Konfigurieren von Diensten zum automatischen oder manuellen Starten, Deaktivieren der Dienste oder Ändern anderer Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="2ab6c-114">Configure services to start automatically or manually, disable the services, or change other service settings</span></span>  
  
-   <span data-ttu-id="2ab6c-115">Ändern der Kennwörter für die von den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Diensten verwendeten Konten</span><span class="sxs-lookup"><span data-stu-id="2ab6c-115">Change the passwords for the accounts used by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services</span></span>  
  
-   <span data-ttu-id="2ab6c-116">Starten von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe von Ablaufverfolgungsflags (Befehlszeilenparameter)</span><span class="sxs-lookup"><span data-stu-id="2ab6c-116">Start [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using trace flags (command line parameters)</span></span>  
  
-   <span data-ttu-id="2ab6c-117">Anzeigen der Eigenschaften von Diensten</span><span class="sxs-lookup"><span data-stu-id="2ab6c-117">View the properties of services</span></span>  
  
## <a name="sql-server-network-configuration"></a><span data-ttu-id="2ab6c-118">SQL Server-Netzwerkkonfiguration</span><span class="sxs-lookup"><span data-stu-id="2ab6c-118">SQL Server Network Configuration</span></span>  
 <span data-ttu-id="2ab6c-119">Verwenden Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager für die folgenden Aufgaben im Zusammenhang mit den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Diensten auf diesem Computer:</span><span class="sxs-lookup"><span data-stu-id="2ab6c-119">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager for the following tasks related to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services on this computer:</span></span>  
  
-   <span data-ttu-id="2ab6c-120">Aktivieren oder Deaktivieren eines [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Netzwerkprotokolls</span><span class="sxs-lookup"><span data-stu-id="2ab6c-120">Enable or disable a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] network protocol</span></span>  
  
-   <span data-ttu-id="2ab6c-121">Konfigurieren eines [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Netzwerkprotokolls</span><span class="sxs-lookup"><span data-stu-id="2ab6c-121">Configure a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] network protocol</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2ab6c-122">Ein kurzes Lernprogramm zum Konfigurieren von Protokollen und zum Herstellen einer Verbindung mit [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]finden Sie unter [Tutorial: Erste Schritte mit der Datenbank-Engine](../../relational-databases/tutorial-getting-started-with-the-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="2ab6c-122">For a short tutorial about how to configure protocols and connect to the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], see [Tutorial: Getting Started with the Database Engine](../../relational-databases/tutorial-getting-started-with-the-database-engine.md).</span></span>  
  
## <a name="sql-server-native-client-configuration"></a><span data-ttu-id="2ab6c-123">SQL Server Native Client-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="2ab6c-123">SQL Server Native Client Configuration</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="2ab6c-124">-Clients werden Verbindungen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-Netzwerkbibliothek hergestellt.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-124">clients connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] by using the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client network library.</span></span> <span data-ttu-id="2ab6c-125">Verwenden Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager für die folgenden Aufgaben im Zusammenhang mit Clientanwendungen auf diesem Computer:</span><span class="sxs-lookup"><span data-stu-id="2ab6c-125">Use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager for the following tasks related to client applications on this computer:</span></span>  
  
-   <span data-ttu-id="2ab6c-126">Geben Sie bei der Verbindungsherstellung zu Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die Protokollreihenfolge für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Clientanwendungen auf diesem Computer an.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-126">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client applications on this computer, specify the protocol order, when connecting to instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="2ab6c-127">Konfigurieren Sie Clientverbindungsprotokolle.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-127">Configure client connection protocols.</span></span>  
  
-   <span data-ttu-id="2ab6c-128">Erstellen Sie für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Clientanwendungen Aliase für Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], sodass von Clients mithilfe einer benutzerdefinierten Verbindungszeichenfolge eine Verbindung hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-128">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client applications, create aliases for instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], so that clients can connect using a custom connection string.</span></span>  
  
 <span data-ttu-id="2ab6c-129">Weitere Informationen zu jeder dieser Aufgaben finden Sie in der F1-Hilfe.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-129">For more information about each of these tasks, see F1 help for each task.</span></span>  
  
#### <a name="to-open-sql-server-configuration-manager"></a><span data-ttu-id="2ab6c-130">So öffnen Sie SQL Server-Konfigurations-Manager</span><span class="sxs-lookup"><span data-stu-id="2ab6c-130">To open SQL Server Configuration Manager</span></span>  
  
-   <span data-ttu-id="2ab6c-131">Klicken Sie auf **Start** , zeigen Sie auf **Alle Programme**, zeigen Sie auf **Microsoft SQL Server** (Version), zeigen Sie auf **Konfigurationstools**, und klicken Sie anschließend auf **SQL Server-Konfigurations-Manager**.</span><span class="sxs-lookup"><span data-stu-id="2ab6c-131">On the **Start** menu, point to **All Programs**, point to **Microsoft SQL Server** (version), point to **Configuration Tools**, and then click **SQL Server Configuration Manager**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ab6c-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2ab6c-132">See Also</span></span>  
 <span data-ttu-id="2ab6c-133">[SQL Server Dienste](../../../2014/tools/configuration-manager/sql-server-services.md) </span><span class="sxs-lookup"><span data-stu-id="2ab6c-133">[SQL Server Services](../../../2014/tools/configuration-manager/sql-server-services.md) </span></span>  
 <span data-ttu-id="2ab6c-134">[Netzwerkkonfiguration SQL Server](sql-server-network-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="2ab6c-134">[SQL Server Network Configuration](sql-server-network-configuration.md) </span></span>  
 <span data-ttu-id="2ab6c-135">[Konfiguration von SQL Native Client 11,0](../../../2014/tools/configuration-manager/sql-native-client-11-0-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="2ab6c-135">[SQL Native Client 11.0 Configuration](../../../2014/tools/configuration-manager/sql-native-client-11-0-configuration.md) </span></span>  
 [<span data-ttu-id="2ab6c-136">Auswählen eines Netzwerkprotokolls</span><span class="sxs-lookup"><span data-stu-id="2ab6c-136">Choosing a Network Protocol</span></span>](../../../2014/tools/configuration-manager/choosing-a-network-protocol.md)  
  
  
