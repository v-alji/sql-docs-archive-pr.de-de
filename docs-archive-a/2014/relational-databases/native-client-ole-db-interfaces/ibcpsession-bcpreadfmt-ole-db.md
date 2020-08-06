---
title: IBCPSession::BCPReadFmt (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- IBCPSession::BCPReadFmt (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- BCPReadFmt method
ms.assetid: e2a12050-94e4-48a3-8a48-b780d646f116
author: rothja
ms.author: jroth
ms.openlocfilehash: ca811dceb8ab6771e3bdd6689a8e11eca6a0e3ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723766"
---
# <a name="ibcpsessionbcpreadfmt-ole-db"></a><span data-ttu-id="a161c-102">'IBCPSession::BCPReadFmt' (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="a161c-102">IBCPSession::BCPReadFmt (OLE DB)</span></span>
  <span data-ttu-id="a161c-103">Liest für jede Spalte Formatinformationen aus der Formatdatei.</span><span class="sxs-lookup"><span data-stu-id="a161c-103">Reads format information for each column from the format file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a161c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a161c-104">Syntax</span></span>  
  
```  
  
HRESULT BCPReadFmt(   
const wchar_t *pwszFormatFile);  
```  
  
## <a name="remarks"></a><span data-ttu-id="a161c-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a161c-105">Remarks</span></span>  
 <span data-ttu-id="a161c-106">Die **BCPReadFmt** -Methode wird verwendet, um Daten aus einer Formatdatei zu lesen, die das Format der Daten in der Datendatei angibt.</span><span class="sxs-lookup"><span data-stu-id="a161c-106">The **BCPReadFmt** method is used for reading data from a format file that specifies the format of data in the data file.</span></span> <span data-ttu-id="a161c-107">Diese Methode kann die korrekte Version der Formatdatei ermitteln.</span><span class="sxs-lookup"><span data-stu-id="a161c-107">This method is capable of detecting the correct version of the format file.</span></span> <span data-ttu-id="a161c-108">Sie kann automatisch erkennen, ob die Formatdatei im XML-Format oder dem alten Textformat abgefasst ist und sich entsprechend verhält.</span><span class="sxs-lookup"><span data-stu-id="a161c-108">It can automatically detect whether the format file is in xml or old style text format and behaves accordingly.</span></span> <span data-ttu-id="a161c-109">Der OLE DB-Anbieter BCP von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client unterstützt Formatdateien der Version 6.0 oder höher.</span><span class="sxs-lookup"><span data-stu-id="a161c-109">The format file versions supported by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider BCP are version 6.0 or newer.</span></span>  
  
 <span data-ttu-id="a161c-110">Nachdem die **BCPReadFmt**-Methode die Formatwerte gelesen hat, nimmt sie geeignete Aufrufe der Methoden [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) und [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) vor.</span><span class="sxs-lookup"><span data-stu-id="a161c-110">After the **BCPReadFmt** method reads the format values, it makes the appropriate calls to the [IBCPSession::BCPColumns](ibcpsession-bcpcolumns-ole-db.md) and [IBCPSession::BCPColFmt](ibcpsession-bcpcolfmt-ole-db.md) methods.</span></span> <span data-ttu-id="a161c-111">Der Benutzer muss eine Formatdatei nicht analysieren, um diese Aufrufe zu tätigen.</span><span class="sxs-lookup"><span data-stu-id="a161c-111">There is no need for the user to parse a format file and make these calls.</span></span>  
  
 <span data-ttu-id="a161c-112">Rufen Sie zum Speichern einer Formatdatei die [IBCPSession::BCPWriteFmt](ibcpsession-bcpwritefmt-ole-db.md)-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="a161c-112">To save a format file, call the [IBCPSession::BCPWriteFmt](ibcpsession-bcpwritefmt-ole-db.md) method.</span></span> <span data-ttu-id="a161c-113">Aufrufe der **BCPReadFmt** -Methode können auf gespeicherte Formate verweisen.</span><span class="sxs-lookup"><span data-stu-id="a161c-113">Calls to the **BCPReadFmt** method can reference saved formats.</span></span> <span data-ttu-id="a161c-114">Alternativ dazu kann das Hilfsprogramm zum Massenkopieren (**bcp**) benutzerdefinierte Datenformate in Dateien speichern, auf die mit der **BCPReadFmt** -Methode verwiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="a161c-114">Alternatively, the bulk-copy utility (**bcp**) can save user-defined data formats in files that can be referenced by the **BCPReadFmt** method.</span></span>  
  
 <span data-ttu-id="a161c-115">Der `BCP_OPTION_DELAYREADFMT` Wert des *eOption* -Parameters von [IBCPSession:: BCPControl](ibcpsession-bcpcontrol-ole-db.md) ändert das Verhalten von IBCPSession:: bcpreadf.</span><span class="sxs-lookup"><span data-stu-id="a161c-115">The `BCP_OPTION_DELAYREADFMT` value of the *eOption* parameter of [IBCPSession::BCPControl](ibcpsession-bcpcontrol-ole-db.md) modifies the behavior of IBCPSession::BCPReadFmt.</span></span>  
  
## <a name="arguments"></a><span data-ttu-id="a161c-116">Argumente</span><span class="sxs-lookup"><span data-stu-id="a161c-116">Arguments</span></span>  
 <span data-ttu-id="a161c-117">*pwszFormatFile*[in]</span><span class="sxs-lookup"><span data-stu-id="a161c-117">*pwszFormatFile*[in]</span></span>  
 <span data-ttu-id="a161c-118">Pfad und Dateiname der Datei, die die Formatwerte für die Datendatei enthält.</span><span class="sxs-lookup"><span data-stu-id="a161c-118">The path and file name of the file containing the format values for the data file.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="a161c-119">Rückgabecodewerte</span><span class="sxs-lookup"><span data-stu-id="a161c-119">Return Code Values</span></span>  
 <span data-ttu-id="a161c-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="a161c-120">S_OK</span></span>  
 <span data-ttu-id="a161c-121">Die Methode wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a161c-121">The method succeeded.</span></span>  
  
 <span data-ttu-id="a161c-122">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a161c-122">E_FAIL</span></span>  
 <span data-ttu-id="a161c-123">Ein anbieterspezifischer Fehler ist aufgetreten. Ausführliche Informationen erhalten Sie über die [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md)-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a161c-123">A provider-specific error occurred, for detailed information use the [ISQLServerErrorInfo](../../database-engine/dev-guide/isqlservererrorinfo-ole-db.md) interface.</span></span>  
  
 <span data-ttu-id="a161c-124">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="a161c-124">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="a161c-125">Fehler aufgrund von nicht genügend Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="a161c-125">Out of memory error.</span></span>  
  
 <span data-ttu-id="a161c-126">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="a161c-126">E_UNEXPECTED</span></span>  
 <span data-ttu-id="a161c-127">Die Methode wurde unerwartet aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a161c-127">The call to the method was unexpected.</span></span> <span data-ttu-id="a161c-128">Die [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md)-Methode wurde beispielsweise erst nach dem Aufruf dieser Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="a161c-128">For example, the [IBCPSession::BCPInit](ibcpsession-bcpinit-ole-db.md) method was not called before calling this method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a161c-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a161c-129">See Also</span></span>  
 <span data-ttu-id="a161c-130">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="a161c-130">[IBCPSession &#40;OLE DB&#41;](ibcpsession-ole-db.md) </span></span>  
 [<span data-ttu-id="a161c-131">Durchführen von Massenkopiervorgängen</span><span class="sxs-lookup"><span data-stu-id="a161c-131">Performing Bulk Copy Operations</span></span>](../native-client/features/performing-bulk-copy-operations.md)  
  
  
