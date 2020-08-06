---
title: IBCPSession::BCPColumns (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPColumns (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPColumns method
ms.assetid: c338abe8-9e30-4853-a7c6-b1a6c00095e1
author: rothja
ms.author: jroth
ms.openlocfilehash: c842b2a815074c0db7e6ab21e0a85eac68a986a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723777"
---
# <a name="ibcpsessionbcpcolumns-ole-db"></a><span data-ttu-id="f57ec-102">IBCPSession::BCPColumns (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="f57ec-102">IBCPSession::BCPColumns (OLE DB)</span></span>
  <span data-ttu-id="f57ec-103">Legt die Anzahl von Feldern fest, die an die Spalten einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tabelle gebunden werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f57ec-103">Sets the number of fields that are to be bound to the columns in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f57ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f57ec-104">Syntax</span></span>  
  
```  
  
HRESULT BCPColumns(   
DBCOUNTITEMnColumns);  
```  
  
## <a name="remarks"></a><span data-ttu-id="f57ec-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f57ec-105">Remarks</span></span>  
 <span data-ttu-id="f57ec-106">Intern wird [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) aufgerufen, um die Standardwerte für Felddaten festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f57ec-106">Internally it calls [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) to set the default values for field data.</span></span> <span data-ttu-id="f57ec-107">Diese Standardwerte werden aus den SQL Server-Spalteninformationen abgerufen, die der Anbieter intern abruft, wenn der Tabellenname über [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f57ec-107">These default values are obtained from the SQL Server column information that the provider internally retrieves when the table name is specified through [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f57ec-108"> Diese Methode kann erst nach dem Aufruf von **BCPInit** mit einem gültigen Dateinamen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f57ec-108">This method can be called only after **BCPInit** has been called with a valid file name.</span></span>  
  
 <span data-ttu-id="f57ec-109">Sie sollten diese Methode nur aufrufen, wenn Sie ein Benutzerdateiformat verwenden möchten, das sich vom Standardformat unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="f57ec-109">You should call this method only if you intend to use a user-file format that differs from the default.</span></span> <span data-ttu-id="f57ec-110">Weitere Informationen mit einer Beschreibung des Standardformats für Benutzerdateien finden Sie unter der **BCPInit** -Methode.</span><span class="sxs-lookup"><span data-stu-id="f57ec-110">For more information about a description of the default user-file format, see the **BCPInit** method.</span></span>  
  
 <span data-ttu-id="f57ec-111">Nach dem Aufruf der **BCPColumns** -Methode müssen Sie für alle Spalten in der Benutzerdatei die **BCPColFmt** -Methode aufrufen, um das benutzerdefinierte Dateiformat vollständig zu definieren.</span><span class="sxs-lookup"><span data-stu-id="f57ec-111">After calling the **BCPColumns** method, you must call the **BCPColFmt** method for each column in the user file to completely define a custom file format.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="f57ec-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="f57ec-112">Arguments</span></span>  
 <span data-ttu-id="f57ec-113">*nColumns*[in]</span><span class="sxs-lookup"><span data-stu-id="f57ec-113">*nColumns*[in]</span></span>  
 <span data-ttu-id="f57ec-114">Die Gesamtzahl der Felder in der Benutzerdatei.</span><span class="sxs-lookup"><span data-stu-id="f57ec-114">The total number of fields in the user file.</span></span> <span data-ttu-id="f57ec-115">Auch wenn Sie das Massenkopieren von Daten aus der Benutzerdatei in eine SQL Server-Tabelle vorbereiten und nicht alle Felder in der Benutzerdatei kopieren möchten, müssen Sie das *nColumns* -Argument auf die Gesamtzahl der Benutzerdateifelder festlegen.</span><span class="sxs-lookup"><span data-stu-id="f57ec-115">Even if you are preparing to bulk copy data from the user file to a SQL Server table and do not intend to copy all fields in the user file, you must still set the *nColumns* argument to the total number of user-file fields.</span></span> <span data-ttu-id="f57ec-116">Die übersprungenen Felder können dann durch **BCPColFmt**angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f57ec-116">The skipped fields can then be specified through **BCPColFmt**.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="f57ec-117">Rückgabecodewerte</span><span class="sxs-lookup"><span data-stu-id="f57ec-117">Return Code Values</span></span>  
 <span data-ttu-id="f57ec-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="f57ec-118">S_OK</span></span>  
 <span data-ttu-id="f57ec-119">Die Methode wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f57ec-119">The method succeeded.</span></span>  
  
 <span data-ttu-id="f57ec-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f57ec-120">E_FAIL</span></span>  
 <span data-ttu-id="f57ec-121">Ein Anbieter spezifischer Fehler ist aufgetreten. Ausführliche Informationen erhalten Sie, wenn Sie die [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) -Schnittstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="f57ec-121">A provider-specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="f57ec-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="f57ec-122">E_UNEXPECTED</span></span>  
 <span data-ttu-id="f57ec-123">Die Methode wurde unerwartet aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f57ec-123">The call to the method was unexpected.</span></span> <span data-ttu-id="f57ec-124">Die **BCPInit** -Methode wurde beispielsweise erst nach dem Aufruf dieser Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="f57ec-124">For example, the **BCPInit** method was not called before calling this method.</span></span> <span data-ttu-id="f57ec-125">Tritt auch auf, wenn diese Methode mehr als einmal für einen Massenkopiervorgang aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f57ec-125">Also occurs when this method is called more than once for a bulk copy operation.</span></span>  
  
 <span data-ttu-id="f57ec-126">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="f57ec-126">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="f57ec-127">Fehler aufgrund nicht genügenden Arbeitsspeichers</span><span class="sxs-lookup"><span data-stu-id="f57ec-127">Out-of-memory error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f57ec-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f57ec-128">See Also</span></span>  
 <span data-ttu-id="f57ec-129">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="f57ec-129">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="f57ec-130">Durchführen von Massenkopiervorgängen</span><span class="sxs-lookup"><span data-stu-id="f57ec-130">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
