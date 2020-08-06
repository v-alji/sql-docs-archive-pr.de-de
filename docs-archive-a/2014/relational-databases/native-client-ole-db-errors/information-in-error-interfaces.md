---
title: Informationen in Fehlerschnittstellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, errors
- IErrorRecords interface
- IErrorInfo interface
- OLE DB error handling, error interfaces
- ISQLErrorInfo interface
- errors [OLE DB], error interfaces
ms.assetid: 4620f03f-1193-43e7-ba19-ad022737d300
author: rothja
ms.author: jroth
ms.openlocfilehash: e9859ccbd804ba15685d84b98cbe74d4b096d98c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620843"
---
# <a name="information-in-error-interfaces"></a><span data-ttu-id="20376-102">Informationen in Fehlerschnittstellen</span><span class="sxs-lookup"><span data-stu-id="20376-102">Information in Error Interfaces</span></span>
  <span data-ttu-id="20376-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter meldet Fehler-und Statusinformationen in den OLE DB definierten Fehler Schnittstellen **IErrorInfo**, **IErrorRecords**und **ISQLErrorInfo**.</span><span class="sxs-lookup"><span data-stu-id="20376-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider reports some error and status information in the OLE DB-defined error interfaces **IErrorInfo**, **IErrorRecords**, and **ISQLErrorInfo**.</span></span>  
  
 <span data-ttu-id="20376-104">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter unterstützt **IErrorInfo** -Member-Funktionen wie folgt.</span><span class="sxs-lookup"><span data-stu-id="20376-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **IErrorInfo** member functions as follows.</span></span>  
  
|<span data-ttu-id="20376-105">Memberfunktion</span><span class="sxs-lookup"><span data-stu-id="20376-105">Member function</span></span>|<span data-ttu-id="20376-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="20376-106">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="20376-107">**GetDescription**</span><span class="sxs-lookup"><span data-stu-id="20376-107">**GetDescription**</span></span>|<span data-ttu-id="20376-108">Beschreibende Fehlermeldungs-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="20376-108">Descriptive error message string.</span></span>|  
|<span data-ttu-id="20376-109">**GetGUID**</span><span class="sxs-lookup"><span data-stu-id="20376-109">**GetGUID**</span></span>|<span data-ttu-id="20376-110">GUID der Schnittstelle, die den Fehler definiert hat.</span><span class="sxs-lookup"><span data-stu-id="20376-110">GUID of the interface that defined the error.</span></span>|  
|<span data-ttu-id="20376-111">**GetHelpContext**</span><span class="sxs-lookup"><span data-stu-id="20376-111">**GetHelpContext**</span></span>|<span data-ttu-id="20376-112">Wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="20376-112">Not supported.</span></span> <span data-ttu-id="20376-113">Es wird immer NULL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="20376-113">Always returns zero.</span></span>|  
|<span data-ttu-id="20376-114">**GetHelpFile**</span><span class="sxs-lookup"><span data-stu-id="20376-114">**GetHelpFile**</span></span>|<span data-ttu-id="20376-115">Wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="20376-115">Not supported.</span></span> <span data-ttu-id="20376-116">Gibt immer NULL zurück.</span><span class="sxs-lookup"><span data-stu-id="20376-116">Always returns NULL.</span></span>|  
|<span data-ttu-id="20376-117">**GetSource**</span><span class="sxs-lookup"><span data-stu-id="20376-117">**GetSource**</span></span>|<span data-ttu-id="20376-118">Zeichenfolge "Microsoft SQL Server Native Client".</span><span class="sxs-lookup"><span data-stu-id="20376-118">String "Microsoft SQL Server Native Client".</span></span>|  
  
 <span data-ttu-id="20376-119">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter unterstützt für Consumer verfügbare **IErrorRecords** -Member-Funktionen wie folgt.</span><span class="sxs-lookup"><span data-stu-id="20376-119">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports consumer-available **IErrorRecords** member functions as follows.</span></span>  
  
|<span data-ttu-id="20376-120">Memberfunktion</span><span class="sxs-lookup"><span data-stu-id="20376-120">Member function</span></span>|<span data-ttu-id="20376-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="20376-121">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="20376-122">**GetBasicErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="20376-122">**GetBasicErrorInfo**</span></span>|<span data-ttu-id="20376-123">Füllt eine ERRORINFO-Struktur mit grundlegenden Informationen über einen Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="20376-123">Fills an ERRORINFO structure with basic information about an error.</span></span> <span data-ttu-id="20376-124">Eine ERRORINFO-Struktur enthält Elemente, die den HRESULT-Rückgabewert für den Fehler sowie den Anbieter und die Schnittstelle, für die der Fehler gilt, identifizieren.</span><span class="sxs-lookup"><span data-stu-id="20376-124">An ERRORINFO structure contains members that identify the HRESULT return value for the error, and the provider and interface to which the error applies.</span></span>|  
|<span data-ttu-id="20376-125">**GetCustomErrorObject**</span><span class="sxs-lookup"><span data-stu-id="20376-125">**GetCustomErrorObject**</span></span>|<span data-ttu-id="20376-126">Gibt einen Verweis auf die Schnittstellen **ISQLErrorInfo,** und [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) zurück.</span><span class="sxs-lookup"><span data-stu-id="20376-126">Returns a reference on interfaces **ISQLErrorInfo,** and [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md).</span></span>|  
|<span data-ttu-id="20376-127">**GetErrorInfo**</span><span class="sxs-lookup"><span data-stu-id="20376-127">**GetErrorInfo**</span></span>|<span data-ttu-id="20376-128">Gibt einen Verweis auf eine **IErrorInfo**-Schnittstelle zurück.</span><span class="sxs-lookup"><span data-stu-id="20376-128">Returns a reference on an **IErrorInfo** interface.</span></span>|  
|<span data-ttu-id="20376-129">**GetErrorParameters**</span><span class="sxs-lookup"><span data-stu-id="20376-129">**GetErrorParameters**</span></span>|<span data-ttu-id="20376-130">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter gibt keine Parameter über **GetErrorParameters**an den Consumer zurück.</span><span class="sxs-lookup"><span data-stu-id="20376-130">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not return parameters to the consumer through **GetErrorParameters**.</span></span>|  
|<span data-ttu-id="20376-131">**GetRecordCount**</span><span class="sxs-lookup"><span data-stu-id="20376-131">**GetRecordCount**</span></span>|<span data-ttu-id="20376-132">Anzahl der verfügbaren Fehlerdatensätze.</span><span class="sxs-lookup"><span data-stu-id="20376-132">Count of error records available.</span></span>|  
  
 <span data-ttu-id="20376-133">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter unterstützt **ISQLErrorInfo:: gezqlinfo** -Parameter wie folgt.</span><span class="sxs-lookup"><span data-stu-id="20376-133">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports **ISQLErrorInfo::GetSQLInfo** parameters as follows.</span></span>  
  
|<span data-ttu-id="20376-134">Parameter</span><span class="sxs-lookup"><span data-stu-id="20376-134">Parameter</span></span>|<span data-ttu-id="20376-135">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="20376-135">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="20376-136">*pbstrSQLState*</span><span class="sxs-lookup"><span data-stu-id="20376-136">*pbstrSQLState*</span></span>|<span data-ttu-id="20376-137">Gibt einen SQLSTATE-Wert für den Fehler zurück.</span><span class="sxs-lookup"><span data-stu-id="20376-137">Returns a SQLSTATE value for the error.</span></span> <span data-ttu-id="20376-138">SQLSTATE-Werte werden in SQL-92, ODBC und ISO SQL sowie der API-Spezifikation definiert.</span><span class="sxs-lookup"><span data-stu-id="20376-138">SQLSTATE values are defined in the SQL-92, ODBC and ISO SQL, and API specifications.</span></span> <span data-ttu-id="20376-139">Weder [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] noch der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB Anbieter definierte Implementierungs spezifische SQLSTATE-Werte.</span><span class="sxs-lookup"><span data-stu-id="20376-139">Neither [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nor the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defined implementation-specific SQLSTATE values.</span></span>|  
|<span data-ttu-id="20376-140">*plNativeError*</span><span class="sxs-lookup"><span data-stu-id="20376-140">*plNativeError*</span></span>|<span data-ttu-id="20376-141">Gibt die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlernummer von **master.dbo.sysmessages** zurück, sofern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="20376-141">Returns the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error number from **master.dbo.sysmessages** when available.</span></span> <span data-ttu-id="20376-142">Systemeigene Fehler sind nach einem erfolgreichen Versuch verfügbar, eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter Datenquelle zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="20376-142">Native errors are available after a successful attempt to initialize a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider data source.</span></span> <span data-ttu-id="20376-143">Vor dem Versuch [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gibt der Native Client OLE DB-Anbieter immer 0 (null) zurück.</span><span class="sxs-lookup"><span data-stu-id="20376-143">Prior to the attempt, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider always returns zero.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="20376-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="20376-144">See Also</span></span>  
 [<span data-ttu-id="20376-145">Fehler</span><span class="sxs-lookup"><span data-stu-id="20376-145">Errors</span></span>](errors.md)  
  
  
