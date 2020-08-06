---
title: Gespeicherte XML-Systemprozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- system stored procedures [SQL Server], XML
- sp_xml_removedocument
- OPENXML statement, system stored procedures
- sp_xml_preparedocument
- XML [SQL Server], system stored procedures
ms.assetid: e60c7f85-6823-4d28-93d6-b053d08cc830
author: rothja
ms.author: jroth
ms.openlocfilehash: 2008294fe5bc532dfb6883656420b4189e4da7b0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619671"
---
# <a name="xml-system-stored-procedures"></a><span data-ttu-id="28479-102">Gespeicherte XML-Systemprozeduren</span><span class="sxs-lookup"><span data-stu-id="28479-102">XML System Stored Procedures</span></span>
  <span data-ttu-id="28479-103">SQL Server stellt die folgenden gespeicherten Systemprozeduren zum Verwenden mit OPENXML bereit:</span><span class="sxs-lookup"><span data-stu-id="28479-103">SQL Server provides the following system stored procedures that are used together with OPENXML:</span></span>  
  
-   [<span data-ttu-id="28479-104">sp_xml_preparedocument &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="28479-104">sp_xml_preparedocument &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-xml-preparedocument-transact-sql)  
  
-   [<span data-ttu-id="28479-105">sp_xml_removedocument &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="28479-105">sp_xml_removedocument &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-xml-removedocument-transact-sql)  
  
 <span data-ttu-id="28479-106">Um Abfragen mithilfe von OPENXML zu schreiben, müssen Sie zunächst eine interne Darstellung des XML-Dokuments erstellen, indem Sie **sp_xml_preparedocument**aufrufen.</span><span class="sxs-lookup"><span data-stu-id="28479-106">To write queries by using OPENXML, you must first create an internal representation of the XML document by calling **sp_xml_preparedocument**.</span></span> <span data-ttu-id="28479-107">Die gespeicherte Prozedur gibt ein Handle für die interne Darstellung des XML-Dokuments zurück.</span><span class="sxs-lookup"><span data-stu-id="28479-107">The stored procedure returns a handle to the internal representation of the XML document.</span></span> <span data-ttu-id="28479-108">Dieses Handle wird dann an OPENXML übergeben.</span><span class="sxs-lookup"><span data-stu-id="28479-108">This handle is then passed to OPENXML.</span></span> <span data-ttu-id="28479-109">OPENXML stellt auf XPaths basierende Rowsetansichten des Dokuments bereit.</span><span class="sxs-lookup"><span data-stu-id="28479-109">OPENXML provides rowset views of the document based on XPaths.</span></span> <span data-ttu-id="28479-110">Dabei handelt es sich um ein Zeilenmuster und mindestens ein Spaltenmuster.</span><span class="sxs-lookup"><span data-stu-id="28479-110">Specifically, this is one row pattern and one or more column patterns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="28479-111">Das von der **sp_xml_preparedocument** -Prozedur zurückgegebene Dokumenthandle ist für die Dauer der Sitzung gültig.</span><span class="sxs-lookup"><span data-stu-id="28479-111">The document handle that is returned by **sp_xml_preparedocument** is valid for the duration of the session.</span></span>  
  
 <span data-ttu-id="28479-112">Die interne Darstellung eines XML-Dokuments kann durch Aufrufen der gespeicherten Systemprozedur **sp_xml_removedocument** aus dem Arbeitsspeicher gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="28479-112">The internal representation of an XML document can be removed from memory by calling the **sp_xml_removedocument** system stored procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28479-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28479-113">See Also</span></span>  
 <span data-ttu-id="28479-114">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="28479-114">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span></span>  
 [<span data-ttu-id="28479-115">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="28479-115">OPENXML &#40;SQL Server&#41;</span></span>](../xml/openxml-sql-server.md)  
  
  
