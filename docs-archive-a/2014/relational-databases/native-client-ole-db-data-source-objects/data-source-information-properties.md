---
title: Eigenschaften von Datenquelleninformationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, data source properties
- properties [OLE DB]
- data source properties [OLE DB]
- information properties [OLE DB]
- OLE DB data source properties [SQL Server Native Client]
ms.assetid: 7fd80e47-5bd9-41e2-a3d3-091a7c8c5f2b
author: rothja
ms.author: jroth
ms.openlocfilehash: c10a4e762bbe3421e720753941f5e0a5702832ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724558"
---
# <a name="data-source-information-properties"></a><span data-ttu-id="43b43-102">Eigenschaften für Datenquelleninformationen</span><span class="sxs-lookup"><span data-stu-id="43b43-102">Data Source Information Properties</span></span>
  <span data-ttu-id="43b43-103">Im anbieterspezifischen Eigenschaftensatz DBPROPSET_SQLSERVERDATASOURCEINFO definiert der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter die folgenden Eigenschaften für Datenquelleninformationen.</span><span class="sxs-lookup"><span data-stu-id="43b43-103">In the provider-specific property set DBPROPSET_SQLSERVERDATASOURCEINFO, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the following data source information properties.</span></span>  
  
|<span data-ttu-id="43b43-104">Eigenschafts-ID</span><span class="sxs-lookup"><span data-stu-id="43b43-104">Property ID</span></span>|<span data-ttu-id="43b43-105">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="43b43-105">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="43b43-106">SSPROP_COLUMNLEVELCOLLATION</span><span class="sxs-lookup"><span data-stu-id="43b43-106">SSPROP_COLUMNLEVELCOLLATION</span></span>|<span data-ttu-id="43b43-107">Typ: VT_BOOL</span><span class="sxs-lookup"><span data-stu-id="43b43-107">Type: VT_BOOL</span></span><br /><br /> <span data-ttu-id="43b43-108">R/W: Lesen</span><span class="sxs-lookup"><span data-stu-id="43b43-108">R/W: Read</span></span><br /><br /> <span data-ttu-id="43b43-109">Standard: VARIANT_TRUE</span><span class="sxs-lookup"><span data-stu-id="43b43-109">Default: VARIANT_TRUE</span></span><br /><br /> <span data-ttu-id="43b43-110">Beschreibung: Wird verwendet, um zu ermitteln, ob Spaltensortierung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="43b43-110">Description: Used to determine if column collation is supported.</span></span><br /><br /> <span data-ttu-id="43b43-111">VARIANT_TRUE: Spaltenebenensortierung wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="43b43-111">VARIANT_TRUE: Column level collation is supported.</span></span><br /><br /> <span data-ttu-id="43b43-112">VARIANT_FALSE: Spaltenebenensortierung wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="43b43-112">VARIANT_FALSE: Column level collation is not supported.</span></span>|  
|<span data-ttu-id="43b43-113">SSPROP_UNICODELCID</span><span class="sxs-lookup"><span data-stu-id="43b43-113">SSPROP_UNICODELCID</span></span>|<span data-ttu-id="43b43-114">Typ: VT_I4 R/W: Lesen</span><span class="sxs-lookup"><span data-stu-id="43b43-114">Type: VT_I4 R/W: Read</span></span><br /><br /> <span data-ttu-id="43b43-115">Beschreibung: Unicode-Gebietsschema-ID</span><span class="sxs-lookup"><span data-stu-id="43b43-115">Description: Unicode locale ID.</span></span><br /><br /> <span data-ttu-id="43b43-116">Dabei handelt es sich um das für die Unicode-Datensortierung verwendete Gebietsschema.</span><span class="sxs-lookup"><span data-stu-id="43b43-116">This is the locale used for Unicode data sorting.</span></span>|  
|<span data-ttu-id="43b43-117">SSPROP_UNICODECOMPARISONSTYLE</span><span class="sxs-lookup"><span data-stu-id="43b43-117">SSPROP_UNICODECOMPARISONSTYLE</span></span>|<span data-ttu-id="43b43-118">Typ: VT_I4 R/W: Lesen</span><span class="sxs-lookup"><span data-stu-id="43b43-118">Type: VT_I4 R/W: Read</span></span><br /><br /> <span data-ttu-id="43b43-119">Beschreibung: Unicode-Vergleichsart</span><span class="sxs-lookup"><span data-stu-id="43b43-119">Description: Unicode comparison style.</span></span><br /><br /> <span data-ttu-id="43b43-120">Dabei handelt es sich um die für die Unicode-Datensortierung verwendeten Sortieroptionen.</span><span class="sxs-lookup"><span data-stu-id="43b43-120">The sorting options used for Unicode data sorting.</span></span>|  
  
 <span data-ttu-id="43b43-121">Im anbieterspezifischen Eigenschaftensatz DBPROPSET_SQLSERVERSTREAM definiert der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter die folgende zusätzliche Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="43b43-121">In the provider-specific property set DBPROPSET_SQLSERVERSTREAM, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the following additional property.</span></span>  
  
|<span data-ttu-id="43b43-122">Eigenschafts-ID</span><span class="sxs-lookup"><span data-stu-id="43b43-122">Property ID</span></span>|<span data-ttu-id="43b43-123">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="43b43-123">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="43b43-124">SSPROP_STREAM_XMLROOT</span><span class="sxs-lookup"><span data-stu-id="43b43-124">SSPROP_STREAM_XMLROOT</span></span>|<span data-ttu-id="43b43-125">Typ: VT_BSTR R/W: Lesen/Schreiben</span><span class="sxs-lookup"><span data-stu-id="43b43-125">Type: VT_BSTR R/W: Read/Write</span></span><br /><br /> <span data-ttu-id="43b43-126">Beschreibung: Das Ergebnis einer FOR XML-Abfrage ist möglicherweise kein wohlgeformtes Dokument.</span><span class="sxs-lookup"><span data-stu-id="43b43-126">Description: The result of a FOR XML query may not be a well-formed document.</span></span> <span data-ttu-id="43b43-127">Wenn diese Eigenschaft angegeben ist, wird das Ergebnis einer „select … for XML“-Abfrage von einem Stammtag umschlossen, das von dieser Eigenschaft bereitgestellt wird, um ein wohlgeformtes XML-Dokument zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="43b43-127">When this property is specified, the result of a 'select ... for XML' query is wrapped in the root tag provided by this property to return a well formed XML document.</span></span> <span data-ttu-id="43b43-128">Wenn die Abfrage in einem Browser ausgeführt wird, führt das möglicherweise dazu, dass der Browser beim Laden des Ergebnisses Parserfehler anzeigt.</span><span class="sxs-lookup"><span data-stu-id="43b43-128">If the query is executed in the browser it may cause the browser to display parser errors when loading the result.</span></span> <span data-ttu-id="43b43-129">Um den Fehler zu vermeiden, unterstützt SQL ISAPI das Schlüsselwort ROOT.</span><span class="sxs-lookup"><span data-stu-id="43b43-129">To avoid the error, SQL ISAPI supports the keyword ROOT.</span></span> <span data-ttu-id="43b43-130">Dieses Schlüsselwort wird der SSPROP_STREAM_XMLROOT-Eigenschaft zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="43b43-130">This keyword maps to SSPROP_STREAM_XMLROOT property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="43b43-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="43b43-131">See Also</span></span>  
 [<span data-ttu-id="43b43-132">Datenquellenobjekte &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="43b43-132">Data Source Objects &#40;OLE DB&#41;</span></span>](data-source-objects-ole-db.md)  
  
  
