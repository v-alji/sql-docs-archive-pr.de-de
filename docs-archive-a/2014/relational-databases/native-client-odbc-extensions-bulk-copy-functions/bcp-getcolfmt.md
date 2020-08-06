---
title: bcp_getcolfmt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_getcolfmt
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_getcolfmt function
ms.assetid: f8bdada5-7b2d-4475-8c98-f93e9d77b130
author: rothja
ms.author: jroth
ms.openlocfilehash: aabc811a5aa0babe5119c4ef0ed0e649586d73cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616060"
---
# <a name="bcp_getcolfmt"></a><span data-ttu-id="af6ae-102">bcp_getcolfmt</span><span class="sxs-lookup"><span data-stu-id="af6ae-102">bcp_getcolfmt</span></span>
  <span data-ttu-id="af6ae-103">Zum Suchen des Spaltenformat-Eigenschaftswerts.</span><span class="sxs-lookup"><span data-stu-id="af6ae-103">Used to find the column format property value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af6ae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="af6ae-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_getcolfmt (  
HDBC   
hdbc  
,  
INT   
field  
,  
INT   
property  
,  
void*   
pValue  
,  
INT   
cbvalue,  
INT*   
pcbLen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="af6ae-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="af6ae-105">Arguments</span></span>  
 <span data-ttu-id="af6ae-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="af6ae-106">*hdbc*</span></span>  
 <span data-ttu-id="af6ae-107">Das für den Massenkopiervorgang aktivierte ODBC-Verbindungshandle.</span><span class="sxs-lookup"><span data-stu-id="af6ae-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="af6ae-108">*Flächen*</span><span class="sxs-lookup"><span data-stu-id="af6ae-108">*field*</span></span>  
 <span data-ttu-id="af6ae-109">Die Spaltenzahl, für die die Eigenschaft abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="af6ae-109">Is the column number for which the property is retrieved.</span></span>  
  
 <span data-ttu-id="af6ae-110">*property*</span><span class="sxs-lookup"><span data-stu-id="af6ae-110">*property*</span></span>  
 <span data-ttu-id="af6ae-111">Eine der Eigenschaftskonstanten.</span><span class="sxs-lookup"><span data-stu-id="af6ae-111">Is one of the property constants.</span></span>  
  
 <span data-ttu-id="af6ae-112">*pValue*</span><span class="sxs-lookup"><span data-stu-id="af6ae-112">*pValue*</span></span>  
 <span data-ttu-id="af6ae-113">Der Verweis auf den Puffer, von dem der Eigenschaftswert abgerufen werden soll.</span><span class="sxs-lookup"><span data-stu-id="af6ae-113">Is the pointer to the buffer from which to retrieve the property value.</span></span>  
  
 <span data-ttu-id="af6ae-114">*cbValue*</span><span class="sxs-lookup"><span data-stu-id="af6ae-114">*cbValue*</span></span>  
 <span data-ttu-id="af6ae-115">Die Länge des Puffers der Eigenschaft in Bytes.</span><span class="sxs-lookup"><span data-stu-id="af6ae-115">Is the length of the property buffer in bytes.</span></span>  
  
 <span data-ttu-id="af6ae-116">*pcbLen*</span><span class="sxs-lookup"><span data-stu-id="af6ae-116">*pcbLen*</span></span>  
 <span data-ttu-id="af6ae-117">Verweis auf Länge der Daten, die im Eigenschaftspuffer zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="af6ae-117">Pointer to length of the data that is being returned in the property buffer.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="af6ae-118">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="af6ae-118">Returns</span></span>  
 <span data-ttu-id="af6ae-119">SUCCEED oder FAIL.</span><span class="sxs-lookup"><span data-stu-id="af6ae-119">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af6ae-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="af6ae-120">Remarks</span></span>  
 <span data-ttu-id="af6ae-121">Spalten Format-Eigenschaftswerte sind im Thema [bcp_setcolfmt](bcp-setcolfmt.md) aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="af6ae-121">Column format property values are listed in the [bcp_setcolfmt](bcp-setcolfmt.md) topic.</span></span> <span data-ttu-id="af6ae-122">Die Spalten Format-Eigenschaftswerte werden durch Aufrufen der **bcp_setcolfmt** -Funktion festgelegt, und die **bcp_getcolfmt** -Funktion wird verwendet, um den Eigenschafts Wert des Spalten Formats zu suchen.</span><span class="sxs-lookup"><span data-stu-id="af6ae-122">The column format property values are set by calling the **bcp_setcolfmt** function, and the **bcp_getcolfmt** function is used to find the column format property value.</span></span>  
  
 <span data-ttu-id="af6ae-123">Verhaltensänderungen werden möglicherweise beim Herstellen einer Verbindung mit einem [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] Server Computer (oder höher) im Vergleich zu früheren [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Versionen beobachtet.</span><span class="sxs-lookup"><span data-stu-id="af6ae-123">Behavior changes may be observed when connecting to a [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] (or later) server computer, compared to earlier [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versions.</span></span> <span data-ttu-id="af6ae-124">Weitere Informationen finden Sie unter [Metadatenermittlung](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="af6ae-124">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
## <a name="bcp_getcolfmt-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="af6ae-125">bcp_getcolfmt-Unterstützung für erweiterte Funktionen für Datum und Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="af6ae-125">bcp_getcolfmt Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="af6ae-126">Die Typen, die mit der- `BCP_FMT_TYPE` Eigenschaft für Datums-/Uhrzeittypen verwendet werden, sind wie in [Massen Kopier Änderungen für verbesserte Datums-und Uhrzeit Typen &#40;OLE DB und ODBC-&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md)angegeben.</span><span class="sxs-lookup"><span data-stu-id="af6ae-126">The types used with the `BCP_FMT_TYPE` property for date/time types are as specified in [Bulk Copy Changes for Enhanced Date and Time Types &#40;OLE DB and ODBC&#41;](../native-client-odbc-date-time/bulk-copy-changes-for-enhanced-date-and-time-types-ole-db-and-odbc.md).</span></span>  
  
 <span data-ttu-id="af6ae-127">Weitere Informationen finden Sie unter [Verbesserungen bei Datum und Uhrzeit &#40;ODBC-&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="af6ae-127">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af6ae-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="af6ae-128">See Also</span></span>  
 [<span data-ttu-id="af6ae-129">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="af6ae-129">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
