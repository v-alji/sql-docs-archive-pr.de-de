---
title: Zuordnen eines Umgebungs Handles | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, environment handles
- ODBC applications, connections
- handles [SQL Server Native Client]
- environment handles [SQLNCLI]
ms.assetid: 15c1b428-ea6d-4672-894c-f0e289e2da3f
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c655b5e9a406c3e1881c9dd199a92666377918f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619102"
---
# <a name="allocating-an-environment-handle"></a><span data-ttu-id="676ba-102">Zuordnen eines Umgebungshandles</span><span class="sxs-lookup"><span data-stu-id="676ba-102">Allocating an Environment Handle</span></span>
  <span data-ttu-id="676ba-103">Bevor eine Anwendung eine ODBC-Funktion aufrufen kann, muss sie die ODBC-Umgebung initialisieren und ein Umgebungshandle zuordnen.</span><span class="sxs-lookup"><span data-stu-id="676ba-103">Before an application can call any ODBC function, it must initialize the ODBC environment and allocate an environment handle.</span></span> <span data-ttu-id="676ba-104">Dies ist das globale Kontexthandle und der Platzhalter für die anderen Handles in ODBC.</span><span class="sxs-lookup"><span data-stu-id="676ba-104">This is the global context handle and placeholder for the other handles in ODBC.</span></span> <span data-ttu-id="676ba-105">Dies geschieht durch Aufrufen von **sqlzuordchandle** , *wobei der Parameter* für den Parameter auf SQL_HANDLE_ENV und *InputHandle* auf SQL_NULL_HANDLE festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="676ba-105">You do this by calling **SQLAllocHandle** with the *HandleType* parameter set to SQL_HANDLE_ENV and *InputHandle* set to SQL_NULL_HANDLE.</span></span>  
  
 <span data-ttu-id="676ba-106">Nachdem das Umgebungshandle zugewiesen wurde, muss die Anwendung Umgebungsattribute festlegen, um anzugeben, welche Version der ODBC-Funktionsaufrufe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="676ba-106">After allocating the environment handle, the application must set environment attributes to indicate which version of ODBC function calls it will be using.</span></span> <span data-ttu-id="676ba-107">Zur Verwendung von ODBC 3. *x* -Funktionen, Aufrufen von [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) , wobei der- *Attribut* Parameter auf SQL_ATTR_ODBC_VERSION und *ValuePtr* auf SQL_OV_ODBC3 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="676ba-107">To use the ODBC 3.*x* functions, call [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) with the *Attribute* parameter set to SQL_ATTR_ODBC_VERSION and *ValuePtr* set to SQL_OV_ODBC3.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="676ba-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="676ba-108">See Also</span></span>  
 [<span data-ttu-id="676ba-109">Kommunikation mit SQL Server &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="676ba-109">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
