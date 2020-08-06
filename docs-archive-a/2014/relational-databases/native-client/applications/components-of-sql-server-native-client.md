---
title: Komponenten von SQL Server Native Client | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, about SQL Server Native Client ODBC driver
- data access [SQL Server Native Client], components
- components [SQL Server Native Client]
- SQLNCLI, about SQL Server Native Client
ms.assetid: 65f932d5-daa1-4eff-b6df-ee633fcf2a7c
author: rothja
ms.author: jroth
ms.openlocfilehash: 32438b9fb5473d9251acd0aceddb46db373f3548
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619078"
---
# <a name="components-of-sql-server-native-client"></a><span data-ttu-id="44431-102">Komponenten von SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="44431-102">Components of SQL Server Native Client</span></span>
  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="44431-103">Native Client enthält die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="44431-103">Native Client contains the following components:</span></span>  
  
|<span data-ttu-id="44431-104">Komponente</span><span class="sxs-lookup"><span data-stu-id="44431-104">Component</span></span>|<span data-ttu-id="44431-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="44431-105">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="44431-106">sqlncli11.dll</span><span class="sxs-lookup"><span data-stu-id="44431-106">sqlncli11.dll</span></span>|<span data-ttu-id="44431-107">Die DLL-Datei (Dynamic-Link Library, DLL), die die gesamte Funktionalität von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client enthält.</span><span class="sxs-lookup"><span data-stu-id="44431-107">The dynamic-link library (DLL) file that contains all of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client functionality.</span></span> <span data-ttu-id="44431-108">Dies umfasst auch den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter und den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC-Treiber.</span><span class="sxs-lookup"><span data-stu-id="44431-108">This includes the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider and the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>|  
|<span data-ttu-id="44431-109">sqlnclir11.rll</span><span class="sxs-lookup"><span data-stu-id="44431-109">sqlnclir11.rll</span></span>|<span data-ttu-id="44431-110">Die begleitende Ressourcendatei für die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="44431-110">The accompanying resource file for the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client library.</span></span>|  
|<span data-ttu-id="44431-111">s10ch_sqlncli.chm</span><span class="sxs-lookup"><span data-stu-id="44431-111">s10ch_sqlncli.chm</span></span>|<span data-ttu-id="44431-112">Die Hilfedatei des Datenquellen-Assistenten, in der dokumentiert wird, wie Sie eine [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Datenquelle unter Verwendung des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC-Treibers oder des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieters erstellen.</span><span class="sxs-lookup"><span data-stu-id="44431-112">The Data Source Wizard help file that documents how to create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data source using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver or the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>|  
|<span data-ttu-id="44431-113">sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="44431-113">sqlncli.h</span></span>|<span data-ttu-id="44431-114">Die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-Headerdatei, die alle neuen, zur Verwendung von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client erforderlichen Definitionen enthält.</span><span class="sxs-lookup"><span data-stu-id="44431-114">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client header file that contains all of the new definitions needed in order to use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="44431-115">Diese Headerdatei ersetzt die Headerdateien odbcss.h und sqloledb.h.</span><span class="sxs-lookup"><span data-stu-id="44431-115">This header file replaces both the odbcss.h and the sqloledb.h header files.</span></span> <span data-ttu-id="44431-116">**Hinweis:**  Sie können nicht im selben Programm auf sqlncli. h und odbcss. h verweisen. Sie können jedoch im selben Programm auf sqlncli. h und SQLOLEDB. h verweisen, solange SQLOLEDB. h zuerst definiert wird.</span><span class="sxs-lookup"><span data-stu-id="44431-116">**Note:**  You cannot reference sqlncli.h and odbcss.h in the same program, but you can reference sqlncli.h and sqloledb.h in same program as long as sqloledb.h is defined first.</span></span>|  
|<span data-ttu-id="44431-117">sqlncli11.lib</span><span class="sxs-lookup"><span data-stu-id="44431-117">sqlncli11.lib</span></span>|<span data-ttu-id="44431-118">Die Bibliotheksdatei, die zum direkten Abrufen der **bcp** -Hilfsprogrammfunktionen benötigt wird, die Teil des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-ODBC-Treibers sind.</span><span class="sxs-lookup"><span data-stu-id="44431-118">The library file needed to directly call the **bcp** utility functions that are part of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="44431-119">**Hinweis:**  Wenn Sie in Ihrem Programmiercode auf die Datei sqlncli11. lib verweisen, müssen Sie sicherstellen, dass sich die sqlncli11.dll Datei in Ihrem Systempfad und im Systempfad der Benutzer befindet, die Ihre Anwendung nutzen.</span><span class="sxs-lookup"><span data-stu-id="44431-119">**Note:**  If you do reference the sqlncli11.lib file in your programming code, you need to make sure that the sqlncli11.dll file is in your system path, and in the system path of the users that make use of your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="44431-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="44431-120">See Also</span></span>  
 [<span data-ttu-id="44431-121">Erstellen von Anwendungen mit SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="44431-121">Building Applications with SQL Server Native Client</span></span>](building-applications-with-sql-server-native-client.md)  
  
  
