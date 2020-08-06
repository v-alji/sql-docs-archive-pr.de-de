---
title: Löschen einer Datenquelle (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [ODBC]
ms.assetid: 910e3e16-7b91-49d8-80bb-b4243926afaa
author: rothja
ms.author: jroth
ms.openlocfilehash: 6e8acd6414b39b317ff0fcfe1b7b9fbab38ae0a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616043"
---
# <a name="delete-a-data-source-odbc"></a><span data-ttu-id="072c1-102">Löschen einer Datenquelle (ODBC)</span><span class="sxs-lookup"><span data-stu-id="072c1-102">Delete a Data Source (ODBC)</span></span>
  <span data-ttu-id="072c1-103">Sie können eine Datenquelle auf folgende Arten löschen: mithilfe des ODBC-Administrators, programmgesteuert (mit [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)) oder durch Löschen einer Datei (bei einem Dateiquellennamen).</span><span class="sxs-lookup"><span data-stu-id="072c1-103">You can delete a data source by using ODBC Administrator, programmatically (by using [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)), or by deleting a file (if a file data source name).</span></span>  
  
### <a name="to-delete-a-data-source-by-using-odbc-administrator"></a><span data-ttu-id="072c1-104">So löschen Sie eine Datenquelle mit dem ODBC-Administrator</span><span class="sxs-lookup"><span data-stu-id="072c1-104">To delete a data source by using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="072c1-105">Öffnen Sie in der **Systemsteuerung**die Option **Verwaltung**, und doppelklicken Sie dann auf **Datenquellen (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="072c1-105">In **Control Panel**, open **Administrative Tools**, and then double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="072c1-106">Stattdessen können Sie auch odbcad32.exe über die Eingabeaufforderung ausführen:</span><span class="sxs-lookup"><span data-stu-id="072c1-106">Alternatively, you can run odbcad32.exe from the command prompt.</span></span>  
  
2.  <span data-ttu-id="072c1-107">Klicken Sie auf die Registerkarte **Benutzer-DSN**, **System-DSN**oder **Datei-DSN** .</span><span class="sxs-lookup"><span data-stu-id="072c1-107">Click the **User DSN**, **System DSN**, or **File DSN** tab.</span></span>  
  
3.  <span data-ttu-id="072c1-108">Klicken Sie auf die zu löschende Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="072c1-108">Click the data source to delete.</span></span>  
  
4.  <span data-ttu-id="072c1-109">Klicken Sie auf **Entfernen**, und bestätigen Sie dann das Löschen.</span><span class="sxs-lookup"><span data-stu-id="072c1-109">Click **Remove**, and then confirm the deletion.</span></span>  
  
## <a name="example"></a><span data-ttu-id="072c1-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="072c1-110">Example</span></span>  
 <span data-ttu-id="072c1-111">Rufen Sie [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) entweder mit ODBC_REMOVE_DSN oder mit ODBC_REMOVE_SYS_DSN als zweitem Parameter auf, um eine Datenquelle programmgesteuert zu löschen.</span><span class="sxs-lookup"><span data-stu-id="072c1-111">To programmatically delete a data source, call [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) using either ODBC_REMOVE_DSN or ODBC_REMOVE_SYS_DSN as the second parameter.</span></span>  
  
 <span data-ttu-id="072c1-112">Im folgenden Beispiel wird gezeigt, wie Sie eine Datenquelle programmgesteuert löschen können.</span><span class="sxs-lookup"><span data-stu-id="072c1-112">The following sample shows how you can programmatically delete a data source.</span></span>  
  
```  
// remove_odbc_data_source.cpp  
// compile with: ODBCCP32.lib user32.lib  
#include <iostream>  
#include <windows.h>  
#include <odbcinst.h>  
  
int main() {   
   LPCSTR provider = "SQL Server";   // Windows SQL Server Driver  
   LPCSTR provider = "SQL Server";   // Windows SQL Server driver  
   LPCSTR provider2 = "SQL Server Native Client 11.0";   // SQL Server 2012 Native Client driver  
   LPCSTR dsnname = "DSN=data2";  
   BOOL retval = SQLConfigDataSource(NULL, ODBC_REMOVE_DSN, provider, dsnname);  
   std::cout << retval;   // 1 if successful  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="072c1-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="072c1-113">See Also</span></span>  
 [<span data-ttu-id="072c1-114">Themen zur Vorgehensweise: Konfigurieren des SQL Server-ODBC-Treibers</span><span class="sxs-lookup"><span data-stu-id="072c1-114">Configuring the SQL Server ODBC Driver How-to Topics</span></span>](../../database-engine/dev-guide/configuring-the-sql-server-odbc-driver-how-to-topics.md)  
  
  
