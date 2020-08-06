---
title: SQL Server Native Client von ODBC-Datenquellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC data sources, about data sources
- ODBC data sources, names
- data sources [SQL Server Native Client]
- names [ODBC]
- ODBC applications, data sources
- SQL Server Native Client ODBC driver, data sources
- ODBC data sources
ms.assetid: a6a50fd0-d439-43fd-b76f-16ec02f478c5
author: rothja
ms.author: jroth
ms.openlocfilehash: 6960118e13f0843640b18056bda655726cbbbd29
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617943"
---
# <a name="sql-server-native-client-odbc-data-sources"></a><span data-ttu-id="2defd-102">SQL Server Native Client ODBC-Datenquellen</span><span class="sxs-lookup"><span data-stu-id="2defd-102">SQL Server Native Client ODBC Data Sources</span></span>
  <span data-ttu-id="2defd-103">Ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenquellenname (DSN) identifiziert eine ODBC-Datenquelle, die alle Informationen enthält, die eine ODBC-Anwendung zur Verbindung mit einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbank auf einem bestimmten Server benötigt.</span><span class="sxs-lookup"><span data-stu-id="2defd-103">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source name (DSN) identifies an ODBC data source containing all of the information that an ODBC application needs to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database on a specific server.</span></span> <span data-ttu-id="2defd-104">Es gibt zwei Methoden, wie Sie einen ODBC-Datenquellennamen definieren können:</span><span class="sxs-lookup"><span data-stu-id="2defd-104">There are two ways you can define an ODBC data source name:</span></span>  
  
-   <span data-ttu-id="2defd-105">Öffnen Sie auf einem Client Computer in der Systemsteuerung die Option Verwaltung, und doppelklicken Sie auf **Datenquellen (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="2defd-105">On a client computer, open Administrative Tools in Control Panel, and double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="2defd-106">Daraufhin wird der ODBC-Datenquellen-Administrator geöffnet, mit dem Sie einen DSN erstellen können.</span><span class="sxs-lookup"><span data-stu-id="2defd-106">This will open the ODBC Data Source Administrator, which you can use to create a DSN.</span></span>  
  
-   <span data-ttu-id="2defd-107">Nennen Sie in einer ODBC-Anwendung [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span><span class="sxs-lookup"><span data-stu-id="2defd-107">In an ODBC application, call [SQLConfigDataSource](../native-client-odbc-api/sqlconfigdatasource.md).</span></span>  
  
 <span data-ttu-id="2defd-108">Eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenquelle enthält Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2defd-108">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source contains:</span></span>  
  
-   <span data-ttu-id="2defd-109">Den Namen der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="2defd-109">The name of the data source.</span></span>  
  
-   <span data-ttu-id="2defd-110">Informationen, die zur Verbindung mit einer bestimmten Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="2defd-110">Any information needed to connect to a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="2defd-111">Die Standarddatenbank, die auf einer bestimmten Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendet werden soll (optional).</span><span class="sxs-lookup"><span data-stu-id="2defd-111">The default database to use on a specific instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (optional).</span></span>  
  
-   <span data-ttu-id="2defd-112">Einstellungen, z. B. welche ANSI-Optionen verwendet werden, ob Leistungsstatistiken protokolliert werden (optional) usw.</span><span class="sxs-lookup"><span data-stu-id="2defd-112">Settings such as which ANSI options to use, whether to log performance statistics, and so on (optional).</span></span>  
  
 <span data-ttu-id="2defd-113">Eine ODBC-Anwendung muss nicht unbedingt über eine Datenquelle eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="2defd-113">An ODBC application is not required to connect through a data source.</span></span> <span data-ttu-id="2defd-114">Die Anwendung muss jedoch dieselben Verbindungsinformationen an die ODBC-Verbindungsfunktion liefern, die der Treiber andernfalls im DSN finden würde.</span><span class="sxs-lookup"><span data-stu-id="2defd-114">However, the application must provide the same connectivity information to an ODBC connect function that the driver would otherwise find in a DSN.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2defd-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2defd-115">See Also</span></span>  
 [<span data-ttu-id="2defd-116">Kommunikation mit SQL Server &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="2defd-116">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
