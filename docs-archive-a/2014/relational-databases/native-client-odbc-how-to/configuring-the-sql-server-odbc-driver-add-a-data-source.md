---
title: Hinzufügen einer Datenquelle (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data sources [ODBC]
ms.assetid: b4ac6f0e-8e6a-4b1a-9a7e-60e0a69b2180
author: rothja
ms.author: jroth
ms.openlocfilehash: 519990e9dd9d84f75c4efc6c76b910f0a359f52f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616045"
---
# <a name="add-a-data-source-odbc"></a><span data-ttu-id="c9022-102">Hinzufügen einer Datenquelle (ODBC)</span><span class="sxs-lookup"><span data-stu-id="c9022-102">Add a Data Source (ODBC)</span></span>
  <span data-ttu-id="c9022-103">Sie können eine Datenquelle auf folgende Arten hinzufügen: mithilfe des ODBC-Administrators, programmgesteuert (mit [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)) oder durch das Erstellen einer Datei.</span><span class="sxs-lookup"><span data-stu-id="c9022-103">You can add a data source by using ODBC Administrator, programmatically (by using [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md)), or by creating a file.</span></span>  
  
### <a name="to-add-a-data-source-by-using-odbc-administrator"></a><span data-ttu-id="c9022-104">So fügen Sie eine Datenquelle mit dem ODBC-Administrator hinzu</span><span class="sxs-lookup"><span data-stu-id="c9022-104">To add a data source by using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="c9022-105">Greifen Sie in der **Systemsteuerung**auf **Verwaltung** und dann auf **Datenquellen (ODBC)** zu.</span><span class="sxs-lookup"><span data-stu-id="c9022-105">From the **Control Panel**, access **Administrative Tools** and then **Data Sources (ODBC)**.</span></span> <span data-ttu-id="c9022-106">Alternativ können Sie odbcad32.exe aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c9022-106">Alternatively, you can invoke odbcad32.exe.</span></span>  
  
2.  <span data-ttu-id="c9022-107">Klicken Sie auf die Registerkarte **Benutzer-DSN**, **System-DSN**oder **Datei-DSN** , und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c9022-107">Click the **User DSN**, **System DSN**, or **File DSN** tab, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="c9022-108">Klicken Sie auf **SQL Server**und dann auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="c9022-108">Click **SQL Server**, and then click **Finish**.</span></span>  
  
4.  <span data-ttu-id="c9022-109">Führen Sie die Schritte im SQL Server-Assistenten zum Erstellen einer neuen Datenquelle aus.</span><span class="sxs-lookup"><span data-stu-id="c9022-109">Complete the Steps in the Create a New Data Source to SQL Server Wizard.</span></span>  
  
### <a name="to-add-a-data-source-programmatically"></a><span data-ttu-id="c9022-110">So fügen Sie eine Datenquellen programmgesteuert hinzu</span><span class="sxs-lookup"><span data-stu-id="c9022-110">To add a data source programmatically</span></span>  
  
1.  <span data-ttu-id="c9022-111">Rufen Sie [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) mit auf entweder ODBC_ADD_DSN oder ODBC_ADD_SYS_DSN festgelegtem zweiten Parameter auf.</span><span class="sxs-lookup"><span data-stu-id="c9022-111">Call [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md) with the second parameter set to either ODBC_ADD_DSN or ODBC_ADD_SYS_DSN.</span></span>  
  
### <a name="to-add-a-file-data-source"></a><span data-ttu-id="c9022-112">So fügen Sie eine Dateidatenquelle hinzu</span><span class="sxs-lookup"><span data-stu-id="c9022-112">To add a file data source</span></span>  
  
1.  <span data-ttu-id="c9022-113">Rufen Sie [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) mit einem SAVEFILE=file_name-Parameter in der Verbindungszeichenfolge auf.</span><span class="sxs-lookup"><span data-stu-id="c9022-113">Call [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) with a SAVEFILE=file_name parameter in the connect string.</span></span> <span data-ttu-id="c9022-114">Wenn die Verbindung erfolgreich ist, erstellt der ODBC-Treiber eine Dateidatenquelle mit den Verbindungsparametern an dem Speicherort, auf den der SAVEFILE-Parameter zeigt.</span><span class="sxs-lookup"><span data-stu-id="c9022-114">If the connect is successful, the ODBC driver creates a file data source with the connection parameters in the location pointed to by the SAVEFILE parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9022-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9022-115">See Also</span></span>  
 [<span data-ttu-id="c9022-116">Themen zur Vorgehensweise: Konfigurieren des SQL Server-ODBC-Treibers</span><span class="sxs-lookup"><span data-stu-id="c9022-116">Configuring the SQL Server ODBC Driver How-to Topics</span></span>](../../database-engine/dev-guide/configuring-the-sql-server-odbc-driver-how-to-topics.md)  
  
  
