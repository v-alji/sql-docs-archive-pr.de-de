---
title: Einschränkungen für reguläre Verbindungen und Kontext Verbindungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- context connections [CLR integration]
- regular connections [CLR integration]
ms.assetid: 0c6fe4cb-d846-40b5-8884-35a9c770f5e8
author: rothja
ms.author: jroth
ms.openlocfilehash: 52f50347a27cdaffe83b252d86c56382b5ef4f31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619166"
---
# <a name="restrictions-on-regular-and-context-connections"></a><span data-ttu-id="5803a-102">Einschränkungen hinsichtlich regulärer Verbindungen und Kontextverbindungen</span><span class="sxs-lookup"><span data-stu-id="5803a-102">Restrictions on Regular and Context Connections</span></span>
  <span data-ttu-id="5803a-103">In diesem Thema werden die Einschränkungen besprochen, denen die Codeausführung im [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] -Prozess durch Kontextverbindungen und reguläre Verbindungen unterliegt.</span><span class="sxs-lookup"><span data-stu-id="5803a-103">This topic discusses the restrictions associated with code executing in the [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] process through context and regular connections.</span></span>  
  
## <a name="restrictions-on-context-connections"></a><span data-ttu-id="5803a-104">Einschränkungen für Kontextverbindungen</span><span class="sxs-lookup"><span data-stu-id="5803a-104">Restrictions on Context Connections</span></span>  
 <span data-ttu-id="5803a-105">Berücksichtigen Sie bei der Anwendungsentwicklung die folgenden Einschränkungen, die für Kontextverbindungen gelten:</span><span class="sxs-lookup"><span data-stu-id="5803a-105">When developing your application, take into account the following restrictions that apply to context connections:</span></span>  
  
-   <span data-ttu-id="5803a-106">Zu einem bestimmten Zeitpunkt kann in einer gegebenen Verbindung nur eine Kontextverbindung bestehen.</span><span class="sxs-lookup"><span data-stu-id="5803a-106">You can have only one context connection open at a given time for a given connection.</span></span> <span data-ttu-id="5803a-107">Wenn in verschiedenen Verbindungen mehrere Anweisungen gleichzeitig ausgeführt werden, kann jede dieser Verbindungen eine eigene Kontextverbindung erhalten.</span><span class="sxs-lookup"><span data-stu-id="5803a-107">If you have multiple statements running concurrently in separate connections, each one of them can get their own context connection.</span></span> <span data-ttu-id="5803a-108">Die Einschränkung wirkt sich nicht auf gleichzeitige Anforderungen verschiedener Verbindungen aus, sondern sie gilt nur für eine gegebene Anforderung für eine gegebene Verbindung.</span><span class="sxs-lookup"><span data-stu-id="5803a-108">The restriction does not affect concurrent requests from different connections; it only affects a given request on a given connection.</span></span>  
  
-   <span data-ttu-id="5803a-109">MARS (Multiple Active Result Set) wird in einer Kontextverbindung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5803a-109">Multiple Active Result Sets (MARS) is not supported in a context connection.</span></span>  
  
-   <span data-ttu-id="5803a-110">Die `SqlBulkCopy`-Klasse funktioniert in Kontextverbindungen nicht.</span><span class="sxs-lookup"><span data-stu-id="5803a-110">The `SqlBulkCopy` class does not operate in a context connection.</span></span>  
  
-   <span data-ttu-id="5803a-111">Die Batchverarbeitung von Updates wird in Kontextverbindungen nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="5803a-111">Update batching in a context connection is not supported</span></span>  
  
-   <span data-ttu-id="5803a-112">`SqlNotificationRequest` kann nicht mit Befehlen verwendet werden, die für eine Kontextverbindung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5803a-112">`SqlNotificationRequest` cannot be used with commands that execute against a context connection.</span></span>  
  
-   <span data-ttu-id="5803a-113">Befehle, die für die Kontextverbindung ausgeführt werden, können nicht abgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="5803a-113">Canceling commands that are running against the context connection is not supported.</span></span> <span data-ttu-id="5803a-114">Die `SqlCommand.Cancel`-Methode ignoriert die Anforderung stillschweigend.</span><span class="sxs-lookup"><span data-stu-id="5803a-114">The `SqlCommand.Cancel` method silently ignores the request.</span></span>  
  
-   <span data-ttu-id="5803a-115">Wenn "context connection=true" verwendet wird, können keine anderen Schlüsselwörter in Verbindungszeichenfolgen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5803a-115">No other connection string keywords can be used when you use "context connection=true".</span></span>  
  
-   <span data-ttu-id="5803a-116">Die `SqlConnection.DataSource`-Eigenschaft gibt NULL zurück, wenn in der Verbindungszeichenfolge für `SqlConnection` "context connection=true" statt des Namens der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Instanz angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5803a-116">The `SqlConnection.DataSource` property returns null if the connection string for the `SqlConnection` is "context connection=true", instead of the name of the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="5803a-117">Die Festlegung der `SqlCommand.CommandTimeout`-Eigenschaft hat keine Auswirkungen, wenn der Befehl für eine Kontextverbindung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5803a-117">Setting the `SqlCommand.CommandTimeout` property has no effect when the command is executed against a context connection.</span></span>  
  
## <a name="restrictions-on-regular-connections"></a><span data-ttu-id="5803a-118">Einschränkungen für reguläre Verbindungen</span><span class="sxs-lookup"><span data-stu-id="5803a-118">Restrictions on Regular Connections</span></span>  
 <span data-ttu-id="5803a-119">Berücksichtigen Sie bei der Anwendungsentwicklung die folgenden Einschränkungen, die für reguläre Verbindungen gelten:</span><span class="sxs-lookup"><span data-stu-id="5803a-119">When developing your application, take into account the following restrictions that apply to regular connections:</span></span>  
  
-   <span data-ttu-id="5803a-120">Die asynchrone Befehlsausführung mit internen Servern wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5803a-120">Asynchronous command execution against internal servers is not supported.</span></span> <span data-ttu-id="5803a-121">Wenn in der Verbindungszeichenfolge eines Befehls "async=true" angegeben wird, dann führt die Ausführung des Befehls dazu, dass die `System.NotSupportedException`-Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="5803a-121">Including "async=true" in the connection string of a command, and then executing the command, results in `System.NotSupportedException` being thrown.</span></span> <span data-ttu-id="5803a-122">Die folgende Meldung wird angezeigt: "Die asynchrone Verarbeitung wird bei einer Ausführung im Rahmen des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Prozesses nicht unterstützt".</span><span class="sxs-lookup"><span data-stu-id="5803a-122">This message appears: "Asynchronous processing is not supported when running inside the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] process."</span></span>  
  
-   <span data-ttu-id="5803a-123">Das `SqlDependency`-Objekt wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5803a-123">`SqlDependency` object is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5803a-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5803a-124">See Also</span></span>  
 [<span data-ttu-id="5803a-125">Kontextverbindung</span><span class="sxs-lookup"><span data-stu-id="5803a-125">Context Connection</span></span>](context-connection.md)  
  
  
