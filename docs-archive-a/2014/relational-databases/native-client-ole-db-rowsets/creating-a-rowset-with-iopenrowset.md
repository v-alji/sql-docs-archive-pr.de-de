---
title: Erstellen eines Rowsets mit IOpenRowset | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- IOpenRowset interface
- rowsets [OLE DB], creating
- SQL Server Native Client OLE DB provider, rowsets
- OLE DB rowsets, creating
ms.assetid: e8bc3de7-4b97-4de9-8df8-e11947d24045
author: rothja
ms.author: jroth
ms.openlocfilehash: bf74466a698d39f74b9531adaa54c79c75e50ef2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723770"
---
# <a name="creating-a-rowset-with-iopenrowset"></a><span data-ttu-id="3e7f2-102">Erstellen eines Rowsets mit 'IopenRowset'</span><span class="sxs-lookup"><span data-stu-id="3e7f2-102">Creating a Rowset with IOpenRowset</span></span>
  <span data-ttu-id="3e7f2-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter unterstützt die **IOpenRowset:: OPENROWSET** -Methode mit den folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="3e7f2-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports the **IOpenRowset::OpenRowset** method with the following restrictions:</span></span>  
  
-   <span data-ttu-id="3e7f2-104">Eine Basistabelle oder -sicht muss in einer Datenbank-ID-Struktur angegeben sein, auf die der *pTableID*-Parameter zeigt.</span><span class="sxs-lookup"><span data-stu-id="3e7f2-104">A base table or view must be specified in a database ID (DBID) structure that the *pTableID* parameter points to.</span></span>  
  
-   <span data-ttu-id="3e7f2-105">Das DBID-Element *eKind* muss DBKIND_NAME anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3e7f2-105">The DBID *eKind* member must indicate DBKIND_NAME.</span></span>  
  
-   <span data-ttu-id="3e7f2-106">Das DBI-Element *uName* muss den Namen einer vorhandenen Basistabelle oder einer Ansicht als Unicode-Zeichenfolge angeben.</span><span class="sxs-lookup"><span data-stu-id="3e7f2-106">The DBID *uName* member must specify the name of an existing base table or a view as a Unicode character string.</span></span>  
  
-   <span data-ttu-id="3e7f2-107">Der *pIndexID*-Parameter von **OpenRowset** muss NULL sein.</span><span class="sxs-lookup"><span data-stu-id="3e7f2-107">The *pIndexID* parameter of **OpenRowset** must be NULL.</span></span>  
  
 <span data-ttu-id="3e7f2-108">Das Resultset von **IOpenRowset::OpenRowset** enthält ein einzelnes Rowset.</span><span class="sxs-lookup"><span data-stu-id="3e7f2-108">The result set of **IOpenRowset::OpenRowset** contains a single rowset.</span></span> <span data-ttu-id="3e7f2-109">Resultsets, die ein einzelnes Rowset enthalten, können von [!INCLUDE[msCoName](../../includes/msconame-md.md)] Cursorn unterstützt werden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3e7f2-109">Result sets that contain a single rowset can be supported by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cursors.</span></span> <span data-ttu-id="3e7f2-110">Die Cursorunterstützung ermöglicht dem Entwickler die Verwendung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Parallelitätsmechanismen.</span><span class="sxs-lookup"><span data-stu-id="3e7f2-110">Cursor support allows the developer to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] concurrency mechanisms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e7f2-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3e7f2-111">See Also</span></span>  
 [<span data-ttu-id="3e7f2-112">Rowsets</span><span class="sxs-lookup"><span data-stu-id="3e7f2-112">Rowsets</span></span>](rowsets.md)  
  
  
