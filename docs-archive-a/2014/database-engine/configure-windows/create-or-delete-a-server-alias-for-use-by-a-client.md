---
title: Erstellen oder Löschen eines Serveralias für die Verwendung durch einen Client (SQL Server-Konfigurations-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- server alias
helpviewer_keywords:
- aliases [SQL Server], deleting
- aliases [SQL Server], creating
ms.assetid: b687e376-ee33-470d-b65a-87246bfefe6f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: bead257b40c33e3640b18890a7d109d774131123
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618904"
---
# <a name="create-or-delete-a-server-alias-for-use-by-a-client-sql-server-configuration-manager"></a><span data-ttu-id="76d0e-102">Erstellen oder Löschen eines Serveralias für die Verwendung durch einen Client (SQL Server-Konfigurations-Manager)</span><span class="sxs-lookup"><span data-stu-id="76d0e-102">Create or Delete a Server Alias for Use by a Client (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="76d0e-103">In diesem Thema wird beschrieben, wie Sie einen Serveralias in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe des SQL Server-Konfigurations-Managers erstellen oder löschen können.</span><span class="sxs-lookup"><span data-stu-id="76d0e-103">This topic describes how to create or delete a server alias in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="76d0e-104">Bei einem Alias handelt es sich um einen alternativen Namen, der zum Herstellen einer Verbindung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="76d0e-104">An alias is an alternate name that can be used to make a connection.</span></span> <span data-ttu-id="76d0e-105">In dem Alias eingeschlossen werden erforderliche Elemente einer Verbindungszeichenfolge. Diese Elemente werden mit einem vom Benutzer ausgewählten Namen offen gelegt.</span><span class="sxs-lookup"><span data-stu-id="76d0e-105">The alias encapsulates the required elements of a connection string, and exposes them with a name chosen by the user.</span></span> <span data-ttu-id="76d0e-106">Aliase können mit jeder Clientanwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="76d0e-106">Aliases can be used with any client application.</span></span> <span data-ttu-id="76d0e-107">Mithilfe von Serveraliasnamen kann der Clientcomputer eine Verbindung mit mehreren Servern über verschiedene Netzwerkprotokolle herstellen, ohne jeweils das Protokoll und die Verbindungsdetails angeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="76d0e-107">By creating server aliases, your client computer can connect to multiple servers using different network protocols, without having to specify the protocol and connection details for each one.</span></span> <span data-ttu-id="76d0e-108">Des Weiteren können mehrere Netzwerkprotokolle gleichzeitig aktiviert sein, auch wenn Sie diese Protokolle nur sporadisch nutzen.</span><span class="sxs-lookup"><span data-stu-id="76d0e-108">In addition, you can also have different network protocols enabled all the time, even if you only need to use them occasionally.</span></span> <span data-ttu-id="76d0e-109">Wenn Sie den Server so konfiguriert haben, dass dieser an einer nicht standardmäßigen Portnummer oder Named Pipe lauscht und dabei der SQL Server-Browserdienst deaktiviert ist, erstellen Sie einen Alias, mit dem die neue Portnummer oder Named Pipe angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="76d0e-109">If you have configured the server to listen on a non-default port number or named pipe, and you have disabled the SQL Server Browser service, create an alias that specifies the new port number or named pipe.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="76d0e-110">Verwenden des SQL Server-Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="76d0e-110">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-create-an-alias"></a><span data-ttu-id="76d0e-111">So erstellen Sie einen Alias</span><span class="sxs-lookup"><span data-stu-id="76d0e-111">To create an alias</span></span>  
  
1.  <span data-ttu-id="76d0e-112">Erweitern Sie im SQL Server-Konfigurations-Manager den Eintrag **SQL Server Native Client-Konfiguration**, klicken Sie mit der rechten Maustaste auf **Aliase**, und klicken Sie auf **Neuer Alias**.</span><span class="sxs-lookup"><span data-stu-id="76d0e-112">In SQL Server Configuration Manager, expand **SQL Server Native Client Configuration**, right-click **Aliases**, and then click **New Alias**.</span></span>  
  
2.  <span data-ttu-id="76d0e-113">Geben Sie im Feld **Aliasname** den Namen des Alias ein.</span><span class="sxs-lookup"><span data-stu-id="76d0e-113">In the **Alias Name** box, type the name of the alias.</span></span> <span data-ttu-id="76d0e-114">Die Clientanwendungen verwenden diesen Namen, wenn eine Verbindung aufgebaut werden soll.</span><span class="sxs-lookup"><span data-stu-id="76d0e-114">Client applications use this name when they connect.</span></span>  
  
3.  <span data-ttu-id="76d0e-115">Geben Sie in das Feld **Server** den Namen oder die IP-Adresse eines Servers ein.</span><span class="sxs-lookup"><span data-stu-id="76d0e-115">In the **Server** box, type the name or IP address of a server.</span></span> <span data-ttu-id="76d0e-116">Bei einer benannten Instanz hängen Sie den Namen der Instanz an.</span><span class="sxs-lookup"><span data-stu-id="76d0e-116">For a named instance append the instance name.</span></span>  
  
4.  <span data-ttu-id="76d0e-117">Wählen Sie im Feld **Protokoll** das zu verwendende Protokoll für diesen Alias aus.</span><span class="sxs-lookup"><span data-stu-id="76d0e-117">In the **Protocol** box, select the protocol used for this alias.</span></span> <span data-ttu-id="76d0e-118">Sobald Sie ein Protokoll angegeben haben, erhält das optionale Eigenschaftsfeld die Bezeichnung "Portnummer", "Pipename" oder "Verbindungszeichenfolge".</span><span class="sxs-lookup"><span data-stu-id="76d0e-118">Selecting a protocol, changes the title of the optional properties box to Port No, Pipe Name, or Connection String.</span></span>  
  
 <span data-ttu-id="76d0e-119">Die in der Hilfe zum [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager beschriebenen Verbindungszeichenfolgen können für Programmierer hilfreich sein, die ihre eigenen Verbindungszeichenfolgen erstellen.</span><span class="sxs-lookup"><span data-stu-id="76d0e-119">The connection strings described in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager Help can be useful for programmers who create their own connection strings.</span></span> <span data-ttu-id="76d0e-120">Drücken Sie F1, oder rufen Sie die **Hilfe** auf, um auf diese Informationen, im Dialogfeld **Neuer Alias**, zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="76d0e-120">To access this information, in the **New Alias** dialog box, press F1, or click **Help**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="76d0e-121">Wenn ein konfigurierter Alias eine Verbindung mit dem falschen Server oder zur falschen Instanz herstellt, deaktivieren Sie das zugeordnete Netzwerkprotokoll, und aktivieren Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="76d0e-121">If a configured alias is connecting to the wrong server or instance, disable and then reenable the associated network protocol.</span></span> <span data-ttu-id="76d0e-122">Dadurch werden alle zwischengespeicherten Verbindungsinformationen gelöscht, und der Client kann die Verbindung ordnungsgemäß herstellen.</span><span class="sxs-lookup"><span data-stu-id="76d0e-122">Doing this clears any cached connection information and allows the client to connect correctly.</span></span>  
  
#### <a name="to-delete-an-alias"></a><span data-ttu-id="76d0e-123">So löschen Sie einen Alias</span><span class="sxs-lookup"><span data-stu-id="76d0e-123">To delete an alias</span></span>  
  
1.  <span data-ttu-id="76d0e-124">Erweitern Sie im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager **SQL Server Native Client-Konfiguration**, und klicken Sie dann auf **Aliase**.</span><span class="sxs-lookup"><span data-stu-id="76d0e-124">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager, expand **SQL Server Native Client Configuration**, and then click **Aliases**.</span></span>  
  
2.  <span data-ttu-id="76d0e-125">Klicken Sie im Detailbereich mit der rechten Maustaste auf den Alias, den Sie löschen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="76d0e-125">In the details pane, right-click the alias that you want to delete, and then click **Delete**.</span></span>  
  
  
