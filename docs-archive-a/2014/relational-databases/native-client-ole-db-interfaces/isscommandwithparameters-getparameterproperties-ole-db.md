---
title: ISSCommandWithParameters::GetParameterProperties (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSCommandWithParameters::GetParameterProperties (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- GetParameterProperties method
ms.assetid: 7f4cc5ea-d028-4fe5-9192-bd153ab3c26c
author: rothja
ms.author: jroth
ms.openlocfilehash: 2160c93748375a4aa3bee3d530d441182204134a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616037"
---
# <a name="isscommandwithparametersgetparameterproperties-ole-db"></a><span data-ttu-id="b6bbc-102">'ISSCommandWithParameters::GetParameterProperties' (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="b6bbc-102">ISSCommandWithParameters::GetParameterProperties (OLE DB)</span></span>
  <span data-ttu-id="b6bbc-103">Gibt ein Array aus SSPARAMPROPS-Eigenschaftensatzstrukturen zurück – einen SSPARAMPROPS-Eigenschaftensatz für jeden UDT- oder XML-Parameter.</span><span class="sxs-lookup"><span data-stu-id="b6bbc-103">Returns an array of SSPARAMPROPS property set structures, one SSPARAMPROPS property set for each UDT or XML parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6bbc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6bbc-104">Syntax</span></span>  
  
```  
  
HRESULT GetParameterProperties(  
DB_UPARAMS *pcParams,  
SSPARAMPROPS **prgParamProperties);  
```  
  
## <a name="arguments"></a><span data-ttu-id="b6bbc-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="b6bbc-105">Arguments</span></span>  
 <span data-ttu-id="b6bbc-106">*pcParams*[out] [in]</span><span class="sxs-lookup"><span data-stu-id="b6bbc-106">*pcParams*[out][in]</span></span>  
 <span data-ttu-id="b6bbc-107">Ein Zeiger auf den Arbeitsspeicher, der die Anzahl von SSPARAMPROPS-Strukturen enthält, die in *prgParamProperties*zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b6bbc-107">A pointer to memory that contains the number of SSPARAMPROPS structures returned in *prgParamProperties*.</span></span>  
  
 <span data-ttu-id="b6bbc-108">*prgParamProperties*[out]</span><span class="sxs-lookup"><span data-stu-id="b6bbc-108">*prgParamProperties*[out]</span></span>  
 <span data-ttu-id="b6bbc-109">Ein Zeiger auf den Arbeitsspeicher, in den ein Array aus SSPARAMPROPS-Strukturen zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b6bbc-109">A pointer to memory in which an array of SSPARAMPROPS structures is returned.</span></span> <span data-ttu-id="b6bbc-110">Der Anbieter ordnet Speicher für die Strukturen zu und gibt die Adresse zu diesem Arbeitsspeicher zurück. der Consumer gibt diesen Speicher mit **imbelegc:: Free** frei, wenn er die Strukturen nicht mehr benötigt.</span><span class="sxs-lookup"><span data-stu-id="b6bbc-110">The provider allocates memory for the structures and returns the address to this memory; the consumer releases this memory with **IMalloc::Free** when it no longer needs the structures.</span></span> <span data-ttu-id="b6bbc-111">Vor dem Aufrufen von **imbelegc:: Free** für *prgParamProperties*muss der Consumer auch **VariantClear** für die *vValue* -Eigenschaft jeder DBPROP-Struktur aufrufen, um einen Speicher Verlust zu verhindern, wenn die Variante einen Verweistyp (z. b. BSTR) enthält. Wenn *pcparameams* bei der Ausgabe 0 (null) ist oder ein anderer Fehler als DB_E_ERRORSOCCURRED auftritt, weist der Anbieter keinen Speicher zu und stellt sicher, dass *prgParamProperties* bei der Ausgabe ein NULL-Zeiger ist.</span><span class="sxs-lookup"><span data-stu-id="b6bbc-111">Before calling **IMalloc::Free** for *prgParamProperties*, the consumer must also call **VariantClear** for the *vValue* property of each DBPROP structure in order to prevent a memory leak in cases where the variant contains a reference type (such as a BSTR.) If *pcParams* is zero on output or an error other than DB_E_ERRORSOCCURRED occurs, the provider does not allocate any memory and ensures that *prgParamProperties* is a null pointer on output.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="b6bbc-112">Rückgabecodewerte</span><span class="sxs-lookup"><span data-stu-id="b6bbc-112">Return Code Values</span></span>  
 <span data-ttu-id="b6bbc-113">Die **GetParameterProperties** -Methode gibt dieselben Fehlercodes zurück wie die OLE DB **ICommandProperties::GetProperties** -Methode, allerdings können DB_S_ERRORSOCCURRED und DB_E_ERRORSOCCURED nicht ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="b6bbc-113">The **GetParameterProperties** method returns the same error codes as the core OLE DB **ICommandProperties::GetProperties** method, except that DB_S_ERRORSOCCURRED and DB_E_ERRORSOCCURED cannot be raised.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6bbc-114">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b6bbc-114">Remarks</span></span>  
 <span data-ttu-id="b6bbc-115">**ISSCommandWithParameters::GetParameterProperties** verhält sich in Bezug auf **GetParameterInfo**konsistent.</span><span class="sxs-lookup"><span data-stu-id="b6bbc-115">**ISSCommandWithParameters::GetParameterProperties** behaves consistently with respect to **GetParameterInfo**.</span></span> <span data-ttu-id="b6bbc-116">Wenn [ISSCommandWithParameters::SetParameterProperties](isscommandwithparameters-setparameterproperties-ole-db.md) und **SetParameterInfo** nicht aufgerufen wurden oder mit einem Wert von 0 (null) für **cParams** aufgerufen wurden, leitet GetParameterInfo Parameterinformationen ab und gibt diese zurück.</span><span class="sxs-lookup"><span data-stu-id="b6bbc-116">If [ISSCommandWithParameters::SetParameterProperties](isscommandwithparameters-setparameterproperties-ole-db.md) or **SetParameterInfo** have not been called or have been called with cParams equal to zero, **GetParameterInfo** derives parameter information and returns this.</span></span> <span data-ttu-id="b6bbc-117">Wenn **ISSCommandWithParameters::SetParameterProperties** oder **SetParameterInfo** für mindestens einen Parameter aufgerufen wurde, gibt **ISSCommandWithParameters::GetParameterProperties** Eigenschaften nur für die Parameter zurück, für die **ISSCommandWithParameters::SetParameterProperties** aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="b6bbc-117">If **ISSCommandWithParameters::SetParameterProperties** or **SetParameterInfo** have been called for at least one parameter, **ISSCommandWithParameters::GetParameterProperties** returns properties only for those parameters for which **ISSCommandWithParameters::SetParameterProperties** has been called.</span></span> <span data-ttu-id="b6bbc-118">Wenn **ISSCommandWithParameters::SetParameterProperties** nach **ISSCommandWithParameters::GetParameterProperties** oder **GetParameterInfo**aufgerufen wird, geben nachfolgende Aufrufe von **ISSCommandWithParameters::GetParameterProperties** die überschriebenen Werte für jene Parameter zurück, für die **ISSCommandWithParameters::SetParameterProperties** aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="b6bbc-118">If **ISSCommandWithParameters::SetParameterProperties** is called after **ISSCommandWithParameters::GetParameterProperties** or **GetParameterInfo**, subsequent calls to **ISSCommandWithParameters::GetParameterProperties** return the overridden values for those parameters for which **ISSCommandWithParameters::SetParameterProperties** has been called.</span></span>  
  
 <span data-ttu-id="b6bbc-119">Die SSPARAMPROPS-Struktur ist folgendermaßen definiert:</span><span class="sxs-lookup"><span data-stu-id="b6bbc-119">The SSPARAMPROPS structure is defined as follows:</span></span>  
  
 `struct SSPARAMPROPS {`  
  
 `DBORDINAL iOrdinal;`  
  
 `ULONG cPropertySets;`  
  
 `DBPROPSET *rgPropertySets;`  
  
 `};`  
  
|<span data-ttu-id="b6bbc-120">Member</span><span class="sxs-lookup"><span data-stu-id="b6bbc-120">Member</span></span>|<span data-ttu-id="b6bbc-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b6bbc-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="b6bbc-122">*iOrdinal*</span><span class="sxs-lookup"><span data-stu-id="b6bbc-122">*iOrdinal*</span></span>|<span data-ttu-id="b6bbc-123">Die Ordnungszahl des übergebenen Parameters</span><span class="sxs-lookup"><span data-stu-id="b6bbc-123">The ordinal of the passed parameter.</span></span>|  
|<span data-ttu-id="b6bbc-124">*cPropertySets*</span><span class="sxs-lookup"><span data-stu-id="b6bbc-124">*cPropertySets*</span></span>|<span data-ttu-id="b6bbc-125">Die Anzahl von DBPROPSET-Strukturen in *rgPropertySets*</span><span class="sxs-lookup"><span data-stu-id="b6bbc-125">The number of DBPROPSET structures in *rgPropertySets*.</span></span>|  
|<span data-ttu-id="b6bbc-126">*rgPropertySets*</span><span class="sxs-lookup"><span data-stu-id="b6bbc-126">*rgPropertySets*</span></span>|<span data-ttu-id="b6bbc-127">Ein Zeiger auf den Speicher, in den ein Array aus DBPROPSET-Strukturen zurückgegeben werden soll</span><span class="sxs-lookup"><span data-stu-id="b6bbc-127">A pointer to memory in which to return an array of DBPROPSET structures.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b6bbc-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6bbc-128">See Also</span></span>  
 [<span data-ttu-id="b6bbc-129">ISSCommandWithParameters &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="b6bbc-129">ISSCommandWithParameters &#40;OLE DB&#41;</span></span>](isscommandwithparameters-ole-db.md)  
  
  
