---
title: IBCPSession::BCPWriteFmt (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPWriteFmt (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPWriteFmt method
ms.assetid: add50425-2ed6-411a-a391-4ce63c364892
author: rothja
ms.author: jroth
ms.openlocfilehash: ee4dcb5809c0f0fbb6d3f7aba6f4af5f6991e0e8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621499"
---
# <a name="ibcpsessionbcpwritefmt-ole-db"></a><span data-ttu-id="d9950-102">IBCPSession::BCPWriteFmt (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="d9950-102">IBCPSession::BCPWriteFmt (OLE DB)</span></span>
  <span data-ttu-id="d9950-103">Schreibt für jede Spalte Formatinformationen in die Formatdatei.</span><span class="sxs-lookup"><span data-stu-id="d9950-103">Writes format information for each column to the format file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9950-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9950-104">Syntax</span></span>  
  
```  
  
HRESULT BCPWriteFmt(   
const wchar_t *pwszFormatFile);  
```  
  
## <a name="remarks"></a><span data-ttu-id="d9950-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d9950-105">Remarks</span></span>  
 <span data-ttu-id="d9950-106">Die Formatdatei gibt das Datenformat einer durch Massenkopieren erstellten Datendatei an.</span><span class="sxs-lookup"><span data-stu-id="d9950-106">The format file specifies the data format of a data file created by bulk copy.</span></span> <span data-ttu-id="d9950-107">Durch Aufrufe der Methoden [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) und [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) wird das Format der Datendatei definiert.</span><span class="sxs-lookup"><span data-stu-id="d9950-107">Calls to the [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) and [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) methods define the format of the data file.</span></span> <span data-ttu-id="d9950-108">Die Methode **BCPWriteFmt** speichert diese Definition in der im Argument pwszFormatFile angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="d9950-108">The **BCPWriteFmt** method saves this definition in the file referenced by the pwszFormatFile argument.</span></span>  
  
 <span data-ttu-id="d9950-109">Die **BCPWriteFmt** -Methode kann die Formatdateien in XML- oder Textformat speichern.</span><span class="sxs-lookup"><span data-stu-id="d9950-109">The **BCPWriteFmt** method can save the format files in either xml or text format.</span></span> <span data-ttu-id="d9950-110">Dies muss mithilfe der BCP_OPTION_XML-Steuerungsoption und der [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md)-Methode angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d9950-110">This must be indicated by using the BCP_OPTION_XML control option with the [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md) method.</span></span>  
  
 <span data-ttu-id="d9950-111">Verwenden Sie die [IBCPSession::BCPReadFmt](ibcpsession-bcpreadfmt-ole-db.md)-Methode, um eine gespeicherte Formatdatei zu laden.</span><span class="sxs-lookup"><span data-stu-id="d9950-111">To load a saved format file, use the [IBCPSession::BCPReadFmt](ibcpsession-bcpreadfmt-ole-db.md) method.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="d9950-112">Argumente</span><span class="sxs-lookup"><span data-stu-id="d9950-112">Arguments</span></span>  
 <span data-ttu-id="d9950-113">*pwszFormatFile*[in]</span><span class="sxs-lookup"><span data-stu-id="d9950-113">*pwszFormatFile*[in]</span></span>  
 <span data-ttu-id="d9950-114">Pfad und Dateiname der Datei, die die Formatwerte für die Datendatei enthält.</span><span class="sxs-lookup"><span data-stu-id="d9950-114">The path and file name of the file containing the format values for the data file.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="d9950-115">Rückgabecodewerte</span><span class="sxs-lookup"><span data-stu-id="d9950-115">Return Code Values</span></span>  
 <span data-ttu-id="d9950-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9950-116">S_OK</span></span>  
 <span data-ttu-id="d9950-117">Die Methode wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d9950-117">The method succeeded.</span></span>  
  
 <span data-ttu-id="d9950-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d9950-118">E_FAIL</span></span>  
 <span data-ttu-id="d9950-119">Ein Anbieter spezifischer Fehler ist aufgetreten. Ausführliche Informationen erhalten Sie, wenn Sie die [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) -Schnittstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="d9950-119">A provider-specific error occurred; for detailed information, use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="d9950-120">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="d9950-120">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="d9950-121">Fehler aufgrund nicht genügenden Arbeitsspeichers</span><span class="sxs-lookup"><span data-stu-id="d9950-121">Out-of-memory error.</span></span>  
  
 <span data-ttu-id="d9950-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="d9950-122">E_UNEXPECTED</span></span>  
 <span data-ttu-id="d9950-123">Die Methode wurde unerwartet aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d9950-123">The call to the method was unexpected.</span></span> <span data-ttu-id="d9950-124">Die [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md)-Methode wurde beispielsweise erst nach dem Aufruf dieser Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d9950-124">For example, the [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) method was not called before calling this method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9950-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9950-125">See Also</span></span>  
 <span data-ttu-id="d9950-126">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="d9950-126">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="d9950-127">Durchführen von Massenkopiervorgängen</span><span class="sxs-lookup"><span data-stu-id="d9950-127">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
