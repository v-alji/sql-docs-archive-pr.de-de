---
title: Architektur der Client seitigen und Server seitigen XML-Formatierung (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- providers [SQLXML], XML formatting architecture
- SQLOLEDB provider
- client-side XML formatting
- data providers [SQLXML], XML formatting architecture
- SQLNCLI, XML
- server-side XML formatting
- SQL Server Native Client, XML
- SQLXMLOLEDB Provider, XML formatting architecture
ms.assetid: 52440d9e-89fd-4c15-a008-a1ea99f41387
author: rothja
ms.author: jroth
ms.openlocfilehash: ae1a9c60a7a7966f4eff2a08b4557487f5aec58c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619715"
---
# <a name="architecture-of-client-side-and-server-side-xml-formatting-sqlxml-40"></a><span data-ttu-id="23785-102">Architektur clientseitiger und serverseitiger XML-Formatierung (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="23785-102">Architecture of Client-side and Server-side XML Formatting (SQLXML 4.0)</span></span>
  <span data-ttu-id="23785-103">Die folgende Abbildung zeigt die Architektur der XML-Formatierung auf Serverseite:</span><span class="sxs-lookup"><span data-stu-id="23785-103">The following illustration shows the architecture of XML formatting on the server side.</span></span>  
  
 <span data-ttu-id="23785-104">![Architektur serverseitiger XML-Formatierung](../../../database-engine/dev-guide/media/serversidexml.gif "Architektur serverseitiger XML-Formatierung")</span><span class="sxs-lookup"><span data-stu-id="23785-104">![Architecture of XML formatting on the server side.](../../../database-engine/dev-guide/media/serversidexml.gif "Architecture of XML formatting on the server side.")</span></span>  
  
 <span data-ttu-id="23785-105">In diesem Beispiel wird der Befehl, der auf dem Client angegeben wird, an den Server gesendet.</span><span class="sxs-lookup"><span data-stu-id="23785-105">In this example, the command that is specified on the client is sent to the server.</span></span> <span data-ttu-id="23785-106">Der Server erstellt ein XML-Dokument und sendet es an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="23785-106">The server produces an XML document and returns it to the client.</span></span> <span data-ttu-id="23785-107">In diesem Fall verfügt der Server über eine Instanz von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="23785-107">In this case, the server has an instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="23785-108">Bei der serverseitigen XML-Formatierung können Sie entweder den SQLXMLOLEDB-Anbieter oder den SQLOLEDB-Anbieter verwenden.</span><span class="sxs-lookup"><span data-stu-id="23785-108">With server-side XML formatting, you can use either the SQLXMLOLEDB provider or the SQLOLEDB provider.</span></span>  <span data-ttu-id="23785-109">Der SQLXMLOLEDB-Anbieter verwendet die Datei Sqlxml4.dll, die in SQLXML 4.0 enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="23785-109">The SQLXMLOLEDB provider uses Sqlxml4.dll, which is included in SQLXML 4.0.</span></span> <span data-ttu-id="23785-110">Bei der Verwendung des SQLOLEDB-Anbieters erhalten Sie die von Sqlxmlx.dll bereitgestellte SQLXML-Funktionalität standardmäßig. Diese Funktionalität wird in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows oder in Microsoft Data Access Components (MDAC) 2.6 oder höher angeboten.</span><span class="sxs-lookup"><span data-stu-id="23785-110">When you use the SQLOLEDB provider, by default you get the SQLXML functionality provided by Sqlxmlx.dll, which is included with [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Windows or in Microsoft Data Access Components (MDAC) 2.6 or later.</span></span> <span data-ttu-id="23785-111">Wenn Sie Sqlxml4.dll mit SQLOLEDB verwenden möchten, müssen Sie die SQLXML-Versions Eigenschaft für das SQLOLEDB-Verbindungs Objekt auf "SQLXML. 4.0" festlegen.</span><span class="sxs-lookup"><span data-stu-id="23785-111">To use Sqlxml4.dll with SQLOLEDB, you must set the SQLXML Version property to "SQLXML.4.0" on the SQLOLEDB Connection object.</span></span> <span data-ttu-id="23785-112">In beiden Fällen erzeugt der Server das XML-Dokument und sendet es an den Client.</span><span class="sxs-lookup"><span data-stu-id="23785-112">In either case, the server produces the XML document and sends it to the client.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="23785-113">XPath-Abfragen und Updategrams werden auf dem Client analysiert.</span><span class="sxs-lookup"><span data-stu-id="23785-113">XPath queries and updategrams are parsed on the client.</span></span> <span data-ttu-id="23785-114">Um die XPath-Vorlage oder Updategramfunktionalität in SQLXML 4.0 zu erhalten, verwenden Sie Sqlxml4.dll.</span><span class="sxs-lookup"><span data-stu-id="23785-114">To get the XPath template or updategram functionality in SQLXML 4.0, use Sqlxml4.dll.</span></span>  
  
 <span data-ttu-id="23785-115">Die folgende Abbildung zeigt die Architektur der XML-Formatierung auf Clientseite.</span><span class="sxs-lookup"><span data-stu-id="23785-115">The following illustration shows the architecture of XML formatting on the client side.</span></span>  
  
 <span data-ttu-id="23785-116">![Architektur der XML-Formatierung auf Clientseite](../../../database-engine/dev-guide/media/clientsidexml.gif "Architektur der XML-Formatierung auf Clientseite")</span><span class="sxs-lookup"><span data-stu-id="23785-116">![Architecture of XML formatting on the client side.](../../../database-engine/dev-guide/media/clientsidexml.gif "Architecture of XML formatting on the client side.")</span></span>  
  
 <span data-ttu-id="23785-117">In diesem Beispiel verwendet der Client den SQLXMLOLEDB-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="23785-117">In this example, the client uses the SQLXMLOLEDB provider.</span></span> <span data-ttu-id="23785-118">In der Verbindungs Zeichenfolge muss die Datenanbieter-Eigenschaft auf SQLOLEDB festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="23785-118">In the connection string, the Data Provider property must be set to SQLOLEDB.</span></span> <span data-ttu-id="23785-119">(Dies ist der einzige in SQLXML 4,0 akzeptierte Wert.) Der Befehl, der auf dem Client ausgeführt wird, wird an den Server gesendet.</span><span class="sxs-lookup"><span data-stu-id="23785-119">(This is the only value accepted in SQLXML 4.0.) The command that is executed on the client is sent to the server.</span></span> <span data-ttu-id="23785-120">Das auf dem Server generierte Rowset wird an den Client gesendet.</span><span class="sxs-lookup"><span data-stu-id="23785-120">The rowset that is generated on the server is sent to the client.</span></span> <span data-ttu-id="23785-121">Die Formatierung des XML-Dokuments aus dem Rowset wird auf dem Client ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="23785-121">The formatting of the XML document from the rowset is performed on the client.</span></span>  
  
 <span data-ttu-id="23785-122">In SQLXML 4.0 kann entweder der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) oder der SQLOLEDB-Anbieter als Datenanbieter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="23785-122">In SQLXML 4.0, either the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) or the SQLOLEDB provider can be used as the data provider.</span></span> <span data-ttu-id="23785-123">Sie können potenziell auf jede Datenquelle zugreifen.</span><span class="sxs-lookup"><span data-stu-id="23785-123">You can potentially access any data source.</span></span> <span data-ttu-id="23785-124">Vorausgesetzt, die Abfrage gibt ein einzelnes Rowset zurück, kann die XML-Transformation auf dem Client angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="23785-124">As long as the query returns a single rowset, the XML transformation can be applied on the client.</span></span>  
  
  
