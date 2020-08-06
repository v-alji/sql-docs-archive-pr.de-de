---
title: Sqlfremdnkeys | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLForeignKeys function
ms.assetid: 6c01ce0d-30d7-4c86-8705-3ab254d8a845
author: rothja
ms.author: jroth
ms.openlocfilehash: a61e80867abb8ecb4d2628b74dc9956051c8e4ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616078"
---
# <a name="sqlforeignkeys"></a><span data-ttu-id="f3380-102">SQLForeignKeys</span><span class="sxs-lookup"><span data-stu-id="f3380-102">SQLForeignKeys</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f3380-103">unterstützt Updateweitergaben und Löschungen über den Fremdschlüsseleinschränkungsmechanismus.</span><span class="sxs-lookup"><span data-stu-id="f3380-103">supports cascading updates and deletes through the foreign key constraint mechanism.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f3380-104">gibt SQL_CASCADE für UPDATE_RULE- und/oder DELETE_RULE-Spalten zurück, wenn die CASCADE-Option in der ON UPDATE-Klausel und/oder der ON DELETE-Klausel der FOREIGN KEY-Einschränkungen angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f3380-104">returns SQL_CASCADE for UPDATE_RULE and/or DELETE_RULE columns if CASCADE option is specified on the ON UPDATE and/or ON DELETE clause of the FOREIGN KEY constraints.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f3380-105">gibt SQL_NO_ACTION für UPDATE_RULE- und/oder DELETE_RULE-Spalten zurück, wenn die NO ACTION-Option in der ON UPDATE-Klausel und/oder der ON DELETE-Klausel der FOREIGN KEY-Einschränkungen angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f3380-105">returns SQL_NO_ACTION for UPDATE_RULE and/or DELETE_RULE columns if NO ACTION option is specified on the ON UPDATE and/or ON DELETE clause of the FOREIGN KEY constraints.</span></span>  
  
 <span data-ttu-id="f3380-106">Wenn in einem beliebigen **SQLForeignKeys** -Parameter ungültige Werte vorhanden sind, gibt **SQLForeignKeys** bei der Ausführung SQL_SUCCESS zurück.</span><span class="sxs-lookup"><span data-stu-id="f3380-106">When invalid values are present in any **SQLForeignKeys** parameter, **SQLForeignKeys** returns SQL_SUCCESS on execution.</span></span> <span data-ttu-id="f3380-107">**SQLFetch** gibt SQL_NO_DATA zurück, wenn in diesen Parametern ungültige Werte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f3380-107">**SQLFetch** returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="f3380-108">**SQLForeignKeys** kann in einem statischen Servercursor ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f3380-108">**SQLForeignKeys** can be executed on a static server cursor.</span></span> <span data-ttu-id="f3380-109">Wenn **SQLForeignKeys** in einem aktualisierbaren Cursor (dynamischer Cursor oder Keysetcursor) ausgeführt wird, wird SQL_SUCCESS_WITH_INFO zurückgegeben. Das bedeutet, dass der Cursortyp geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="f3380-109">An attempt to execute **SQLForeignKeys** on an updatable (dynamic or keyset) cursor returns SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="f3380-110">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber unterstützt die Meldung von Informationen für Tabellen auf Verbindungsservern, indem er einen zweiteiligen Namen für die Parameter *FKCatalogName* und *PKCatalogName* akzeptiert: *Linked_Server_Name.Catalog_Name*.</span><span class="sxs-lookup"><span data-stu-id="f3380-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *FKCatalogName* and *PKCatalogName* parameters: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3380-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f3380-111">See Also</span></span>  
 <span data-ttu-id="f3380-112">[Sqlfremdnkeys-Funktion](https://go.microsoft.com/fwlink/?LinkId=59344) </span><span class="sxs-lookup"><span data-stu-id="f3380-112">[SQLForeignKeys Function](https://go.microsoft.com/fwlink/?LinkId=59344) </span></span>  
 [<span data-ttu-id="f3380-113">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="f3380-113">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
