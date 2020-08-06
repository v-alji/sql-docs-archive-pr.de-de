---
title: Neuer Alias (Registerkarte Alias) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 785eb6fb-f67e-449d-b1c8-c38dfbb95ef6
author: stevestein
ms.author: sstein
ms.openlocfilehash: 90742e5de3da0cac83c8b18eebba242ddb9a865d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617335"
---
# <a name="new-alias-alias-tab"></a><span data-ttu-id="eed9e-102">Neuer Alias (Registerkarte Alias)</span><span class="sxs-lookup"><span data-stu-id="eed9e-102">New Alias (Alias Tab)</span></span>
  <span data-ttu-id="eed9e-103">Bei einem Alias handelt es sich um einen alternativen Namen, der zum Herstellen einer Verbindung verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="eed9e-103">An alias is an alternate name that can be used to make a connection.</span></span> <span data-ttu-id="eed9e-104">In dem Alias eingeschlossen werden erforderliche Elemente einer Verbindungszeichenfolge. Diese Elemente werden mit einem vom Benutzer ausgewählten Namen offen gelegt.</span><span class="sxs-lookup"><span data-stu-id="eed9e-104">The alias encapsulates the required elements of a connection string, and exposes them with a name chosen by the user.</span></span> <span data-ttu-id="eed9e-105">Verwenden Sie im Dialogfeld **Alias – Neu** die Seite **Alias** , um die Elemente der Verbindungszeichenfolge für einen Alias anzugeben.</span><span class="sxs-lookup"><span data-stu-id="eed9e-105">Use the **Alias** page on the **Alias - New** dialog box to specify the elements of the connection string for an alias.</span></span> <span data-ttu-id="eed9e-106">Informationen zum Ändern der Verbindungszeichenfolge eines vorhandenen Alias finden Sie unter [&#60;Alias&#62;-Eigenschaften &#40;Registerkarte „Alias“&#41;](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md).</span><span class="sxs-lookup"><span data-stu-id="eed9e-106">To change the connection string of an existing alias, see [&#60;Alias&#62; Properties &#40;Alias Tab&#41;](../../../2014/tools/configuration-manager/alias-properties-alias-tab.md).</span></span>  
  
 <span data-ttu-id="eed9e-107">Alle Werte im **Eigenschaften** -Raster müssen nicht vervollständigt werden.</span><span class="sxs-lookup"><span data-stu-id="eed9e-107">All values in the **Properties** grid do not have to be completed.</span></span> <span data-ttu-id="eed9e-108">Gültige Kombinationen variieren abhängig vom ausgewählten Protokoll.</span><span class="sxs-lookup"><span data-stu-id="eed9e-108">Valid combinations vary depending on the protocol selected.</span></span> <span data-ttu-id="eed9e-109">Beispiele für gültige Kombinationen finden Sie in der folgenden Liste.</span><span class="sxs-lookup"><span data-stu-id="eed9e-109">See the topics listed below for examples of valid combinations.</span></span>  
  
 <span data-ttu-id="eed9e-110">**Aliasname**</span><span class="sxs-lookup"><span data-stu-id="eed9e-110">**Alias Name**</span></span>  
 <span data-ttu-id="eed9e-111">Der Name (Alias), der als Referenz auf diese Verbindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="eed9e-111">The name (alias) that you want to use to refer to this connection.</span></span>  
  
 <span data-ttu-id="eed9e-112">**Pipename** / **Portnr.**</span><span class="sxs-lookup"><span data-stu-id="eed9e-112">**Pipe Name** / **Port No**</span></span>  
 <span data-ttu-id="eed9e-113">Zusätzliche Elemente der Verbindungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="eed9e-113">Additional elements of the connection string.</span></span> <span data-ttu-id="eed9e-114">Der Name dieses Dialogfelds unterscheidet sich je nach ausgewähltem Protokoll.</span><span class="sxs-lookup"><span data-stu-id="eed9e-114">The name of this box varies with the selected protocol.</span></span>  
  
 <span data-ttu-id="eed9e-115">**Protokoll**</span><span class="sxs-lookup"><span data-stu-id="eed9e-115">**Protocol**</span></span>  
 <span data-ttu-id="eed9e-116">Das für die Verbindung verwendete Protokoll.</span><span class="sxs-lookup"><span data-stu-id="eed9e-116">The protocol used for the connection.</span></span>  
  
 <span data-ttu-id="eed9e-117">**Server**</span><span class="sxs-lookup"><span data-stu-id="eed9e-117">**Server**</span></span>  
 <span data-ttu-id="eed9e-118">Der Name der Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mit der eine Verbindung hergestellt wird</span><span class="sxs-lookup"><span data-stu-id="eed9e-118">The name of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance being connected to.</span></span>  
  
## <a name="when-to-use-an-alias"></a><span data-ttu-id="eed9e-119">Wann ein Alias verwendet werden sollte</span><span class="sxs-lookup"><span data-stu-id="eed9e-119">When to Use an Alias</span></span>  
 <span data-ttu-id="eed9e-120">Standardmäßig wird von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] eine Verbindung mit einer lokalen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe des **Shared Memory** -Protokolls, sowie mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf einem anderen Computer mithilfe von **TCP/IP** oder **Named Pipes**hergestellt.</span><span class="sxs-lookup"><span data-stu-id="eed9e-120">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connects to a local instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the **Shared Memory** protocol, and to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on another computer using either **TCP/IP** or **Named Pipes**.</span></span> <span data-ttu-id="eed9e-121">Erstellen Sie einen Alias, wenn Sie TCP/IP oder Named Pipes verwenden und eine benutzerdefinierte Verbindungszeichenfolge zur Verfügung stellen oder einen anderen Namen als den Servernamen für die Verbindung verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="eed9e-121">Create an alias when you are using TCP/IP or named pipes, and you want to provide a customized connection string, or when you want to use a name other than the server name for the connection.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="eed9e-122">Beispiele</span><span class="sxs-lookup"><span data-stu-id="eed9e-122">Examples</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="eed9e-123">lauscht nicht wird am Standard-TCP/IP-Port 1433. Sie sollten deshalb eine Verbindungszeichenfolge mit einer anderen Portnummer zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="eed9e-123">is not listening on the default TCP/IP port of 1433 so you want to provide a connection string with a different port number.</span></span>  
  
-   [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="eed9e-124">wird an der standardmäßige Named Pipe nicht gelauscht. Sie möchten deshalb eine Verbindungszeichenfolge mit einem anderen Pipenamen zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="eed9e-124">is not listening on the default named pipe so you want to provide a connection string with a different pipe name.</span></span>  
  
-   <span data-ttu-id="eed9e-125">Eine Anwendung ist auf die Verbindung mit einer Datenbank auf dem Server `ACCT`festgelegt. Diese Datenbank wurde aber als Instanz `ACCT` auf einem Server mit dem Namen `CENTRAL`konsolidiert.</span><span class="sxs-lookup"><span data-stu-id="eed9e-125">An application expects to connect to a database on the server named `ACCT`, but that database has been consolidated as an instance named `ACCT` on a server named `CENTRAL`.</span></span> <span data-ttu-id="eed9e-126">Das Ändern der Anwendung ist nicht einfach.</span><span class="sxs-lookup"><span data-stu-id="eed9e-126">The application cannot easily be changed.</span></span> <span data-ttu-id="eed9e-127">Erstellen Sie einen Alias mit dem Namen `ACCT`mit einer Verbindungszeichenfolge, die auf `CENTRAL\ACCT`zeigt.</span><span class="sxs-lookup"><span data-stu-id="eed9e-127">Create an alias named `ACCT`, with a connection string pointing to `CENTRAL\ACCT`.</span></span>  
  
## <a name="creating-a-valid-connection-string"></a><span data-ttu-id="eed9e-128">Erstellen einer gültigen Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="eed9e-128">Creating a Valid Connection String</span></span>  
 <span data-ttu-id="eed9e-129">In den folgenden Themen finden Sie Beschreibungen und Beispiele für gültige Kombinationen von Aliaseigenschaften:</span><span class="sxs-lookup"><span data-stu-id="eed9e-129">See the following topics for a description and examples of valid combinations of alias properties:</span></span>  
  
-   [<span data-ttu-id="eed9e-130">Erstellen einer gültigen Verbindungszeichenfolge mithilfe des Shared Memory-Protokolls</span><span class="sxs-lookup"><span data-stu-id="eed9e-130">Creating a Valid Connection String Using Shared Memory Protocol</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-shared-memory-protocol.md)  
  
-   [<span data-ttu-id="eed9e-131">Erstellen einer gültigen Verbindungszeichenfolge mithilfe von TCP/IP</span><span class="sxs-lookup"><span data-stu-id="eed9e-131">Creating a Valid Connection String Using TCP IP</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-tcp-ip.md)  
  
-   [<span data-ttu-id="eed9e-132">Erstellen einer gültigen Verbindungszeichenfolge mithilfe von Named Pipes</span><span class="sxs-lookup"><span data-stu-id="eed9e-132">Creating a Valid Connection String Using Named Pipes</span></span>](../../../2014/tools/configuration-manager/creating-a-valid-connection-string-using-named-pipes.md)  
  
  
