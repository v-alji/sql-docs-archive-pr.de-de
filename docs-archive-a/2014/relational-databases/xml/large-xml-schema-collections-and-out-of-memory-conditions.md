---
title: Große XML-Schemaauflistungen und Bedingungen des Typs „Nicht genügend Arbeitsspeicher“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- out-of-memory conditions
- XML schema collections [SQL Server], large
ms.assetid: 29b9d839-aaaf-48fb-be17-840c751f36f1
author: rothja
ms.author: jroth
ms.openlocfilehash: 8443207bbbdff5db7e54d61fcebabe70e34cc540
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726729"
---
# <a name="large-xml-schema-collections-and-out-of-memory-conditions"></a><span data-ttu-id="fecf6-102">Große XML-Schemaauflistungen und Bedingungen des Typs Nicht genügend Arbeitsspeicher</span><span class="sxs-lookup"><span data-stu-id="fecf6-102">Large XML Schema Collections and Out-of-Memory Conditions</span></span>
  <span data-ttu-id="fecf6-103">Während eines Aufrufs der integrierten XML_SCHEMA_NAMESPACE()-Funktion für eine große XML-Schemaauflistung oder beim Löschen großer XML-Schemaauflistungen kann eine Bedingung des Typs "Nicht genügend Arbeitsspeicher" auftreten.</span><span class="sxs-lookup"><span data-stu-id="fecf6-103">During a call to the built-in XML_SCHEMA_NAMESPACE() function on a large XML schema collection, or when you try to drop large XML schema collections, an out-of-memory condition may occur.</span></span> <span data-ttu-id="fecf6-104">Mit den folgenden Lösungen kann dieses Problem behoben werden:</span><span class="sxs-lookup"><span data-stu-id="fecf6-104">The following are solutions you can use to handle this:</span></span>  
  
-   <span data-ttu-id="fecf6-105">Wenn die Systemlast hoch ist, verwenden Sie den DROP_XML_SCHEMA_COLLECTION-Befehl.</span><span class="sxs-lookup"><span data-stu-id="fecf6-105">When the system load is light, use the DROP_XML_SCHEMA_COLLECTION command.</span></span> <span data-ttu-id="fecf6-106">Schlägt dies fehl, schalten Sie die Datenbank mithilfe der ALTER DATABASE-Anweisung in den Einzelbenutzermodus um und versuchen dann nochmals, DROP XML SCHEMA COLLECTION auszuführen.</span><span class="sxs-lookup"><span data-stu-id="fecf6-106">If this fails, put the database in single-user mode by using the ALTER DATABASE statement and trying DROP XML SCHEMA COLLECTION again.</span></span> <span data-ttu-id="fecf6-107">Wenn die XML-Schemaauflistung in **master**-, **model**- oder **tempdb**-Datenbanken vorhanden ist, ist ein Neustart des Servers für den Einzelbenutzermodus erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fecf6-107">If the XML schema collection exists in **master**, **model**, or **tempdb**, a server restart is required for single-user mode.</span></span>  
  
-   <span data-ttu-id="fecf6-108">Wenn Sie XML_SCHEMA_NAMESPACE aufrufen, können Sie versuchen, einen einzelnen XML-Schemanamespace abzurufen. Sie können den Aufruf auch zu einem Zeitpunkt durchführen, wenn die Systemlast geringer ist, oder den Aufruf im Einzelbenutzermodus versuchen.</span><span class="sxs-lookup"><span data-stu-id="fecf6-108">When you call the XML_SCHEMA_NAMESPACE, you can try to retrieve a single XML schema namespace, you can try the call when the system load is lighter, or you can try the call in single-user mode.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fecf6-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fecf6-109">See Also</span></span>  
 [<span data-ttu-id="fecf6-110">Anforderungen und Einschränkungen für XML-Schemaauflistungen auf dem Server</span><span class="sxs-lookup"><span data-stu-id="fecf6-110">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
