---
title: ISSCommandWithParameters::SetParameterProperties (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSCommandWithParameters::SetParameterProperties (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- SetParameterProperties method
ms.assetid: 4cd0281a-a2a0-43df-8e46-eb478b64cb4b
author: rothja
ms.author: jroth
ms.openlocfilehash: 4bf8e5cde9885a5d9b55d84c6384b76aecf50b8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696794"
---
# <a name="isscommandwithparameterssetparameterproperties-ole-db"></a><span data-ttu-id="281b8-102">'ISSCommandWithParameters::SetParameterProperties' (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="281b8-102">ISSCommandWithParameters::SetParameterProperties (OLE DB)</span></span>
  <span data-ttu-id="281b8-103">Legt die Parametereigenschaften für einzelne Parameter nach Ordnungszahl fest oder legt Massenparametereigenschaften durch Angabe eines Arrays von SSPARAMPROPS-Strukturen fest.</span><span class="sxs-lookup"><span data-stu-id="281b8-103">Sets the parameter properties on a per parameter basis by ordinal, or sets bulk parameter properties by specifying an array of SSPARAMPROPS structures.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="281b8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="281b8-104">Syntax</span></span>  
  
```  
  
HRESULT SetParameterProperties(  
DB_UPARAMS cParams,   
SSPARAMPROPS rgParamProperties[]);  
```  
  
## <a name="arguments"></a><span data-ttu-id="281b8-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="281b8-105">Arguments</span></span>  
 <span data-ttu-id="281b8-106">*cParams*[in]</span><span class="sxs-lookup"><span data-stu-id="281b8-106">*cParams*[in]</span></span>  
 <span data-ttu-id="281b8-107">Die Anzahl der SSPARAMPROPS-Strukturen im *rgParamProperties*-Array.</span><span class="sxs-lookup"><span data-stu-id="281b8-107">The number of SSPARAMPROPS structures in the *rgParamProperties* array.</span></span> <span data-ttu-id="281b8-108">Wenn diese Zahl 0 (null) ist, `ISSCommandWithParameters::SetParameterProperties` werden alle Eigenschaften gelöscht, die möglicherweise für Parameter im Befehl angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="281b8-108">If this number is zero, `ISSCommandWithParameters::SetParameterProperties` will delete all properties that might have been specified for any parameters in the command.</span></span>  
  
 <span data-ttu-id="281b8-109">*rgParamProperties*[in]</span><span class="sxs-lookup"><span data-stu-id="281b8-109">*rgParamProperties*[in]</span></span>  
 <span data-ttu-id="281b8-110">Ein Array von SSPARAMPROPS-Strukturen, die festgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="281b8-110">An array of SSPARAMPROPS structures to be set.</span></span>  
  
## <a name="return-code-values"></a><span data-ttu-id="281b8-111">Rückgabecodewerte</span><span class="sxs-lookup"><span data-stu-id="281b8-111">Return Code Values</span></span>  
 <span data-ttu-id="281b8-112">Die- `ISSCommandWithParameters::SetParameterProperties` Methode gibt dieselben Fehlercodes zurück wie die Core-OLE DB **ICommandProperties:: SetProperties** -Methode.</span><span class="sxs-lookup"><span data-stu-id="281b8-112">The `ISSCommandWithParameters::SetParameterProperties` method returns the same error codes as the core OLE DB **ICommandProperties::SetProperties** method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="281b8-113">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="281b8-113">Remarks</span></span>  
 <span data-ttu-id="281b8-114">Das Festlegen von Parameter Eigenschaften mit dieser Methode ist für eine Parameter Basis nach Ordinalzahl oder mit einem einzelnen-Befehl zulässig, `ISSCommandWithParameters::SetParameterProperties` sobald ssparamproperties aus dem Eigenschafts Array erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="281b8-114">Setting parameter properties with this method is allowed on a per parameter basis by ordinal, or with a single `ISSCommandWithParameters::SetParameterProperties` call once the SSPARAMPROPS has been built from the property array.</span></span>  
  
 <span data-ttu-id="281b8-115">Die **SetParameterInfo** -Methode muss aufgerufen werden, bevor die-Methode aufgerufen wird `ISSCommandWithParameters::SetParameterProperties` .</span><span class="sxs-lookup"><span data-stu-id="281b8-115">The **SetParameterInfo** method must be called before calling the `ISSCommandWithParameters::SetParameterProperties` method.</span></span> <span data-ttu-id="281b8-116">Durch Aufrufen von `SetParameterProperties(0, NULL)` werden alle angegebenen Parametereigenschaften gelöscht, während der Aufruf von `SetParameterInfo(0,NULL,NULL)` alle Parameterinformationen löscht, einschließlich Eigenschaften, die einem Parameter zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="281b8-116">Calling `SetParameterProperties(0, NULL)` clears all specified parameter properties, while calling `SetParameterInfo(0,NULL,NULL)` clears all the parameter info including any properties that might be associated with a parameter.</span></span>  
  
 <span data-ttu-id="281b8-117">`ISSCommandWithParameters::SetParameterProperties`Der Aufruf von zum Angeben von Eigenschaften für einen Parameter, der nicht vom Typ DBTYPE_XML oder DBTYPE_UDT DB_E_ERRORSOCCURRED oder DB_S_ERRORSOCCURRED zurückgibt, und kennzeichnet das *dwStatus* -Feld aller dbproperties, die in ssparamproperties für diesen Parameter mit DBPROPSTATUS_NOTSET enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="281b8-117">Calling `ISSCommandWithParameters::SetParameterProperties` to specify properties for a parameter which is not of type DBTYPE_XML or DBTYPE_UDT returns DB_E_ERRORSOCCURRED or DB_S_ERRORSOCCURRED and marks the *dwStatus* field of all DBPROPs contained in SSPARAMPROPS for that parameter with DBPROPSTATUS_NOTSET.</span></span> <span data-ttu-id="281b8-118">Das DBPROP-Array jedes in SSPARAMPROPS enthaltenen DBPROPs sollte durchsucht werden, um zu ermitteln, auf welchen Parameter DB_E_ERRORSOCCURRED bzw. DB_S_ERRORSOCCURRED verweist.</span><span class="sxs-lookup"><span data-stu-id="281b8-118">The DBPROP array of each DBPROPSET contained in SSPARAMPROPS should be traversed to detect which parameter the DB_E_ERRORSOCCURRED or DB_S_ERRORSOCCURRED refers to.</span></span>  
  
 <span data-ttu-id="281b8-119">Wenn `ISSCommandWithParameters::SetParameterProperties` aufgerufen wird, um die Eigenschaften von Parametern anzugeben, deren Parameterinformationen noch nicht mit **SetParameterInfo**festgelegt wurden, gibt der Anbieter E_UNEXPECTED mit der folgenden Fehlermeldung zurück:</span><span class="sxs-lookup"><span data-stu-id="281b8-119">If `ISSCommandWithParameters::SetParameterProperties` is called to specify the properties of parameters whose parameter info have not been set yet with **SetParameterInfo**, the provider returns E_UNEXPECTED with the following error message:</span></span>  
  
 <span data-ttu-id="281b8-120">Die SetParameterProperties-Methode kann für die angegebenen Parameter nicht aufgerufen werden, ohne dass zunächst die SetParameterInfo-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="281b8-120">SetParameterProperties method cannot be called for the specified parameters without first calling SetParameterInfo method.</span></span> <span data-ttu-id="281b8-121">Die Parameterinformationen müssen vor dem Festlegen der Parametereigenschaften festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="281b8-121">The parameter information must be set before setting the parameter properties.</span></span>  
  
 <span data-ttu-id="281b8-122">Wenn der Aufrufen von `ISSCommandWithParameters::SetParameterProperties` einige Parameter enthält, bei denen die Parameterinformationen festgelegt wurden, und einige Parameter, bei denen die Parameterinformationen nicht festgelegt wurden, werden die dwStatus-Eigenschaften im DBPROPSET der ssparamproperties-Eigenschaft mit DBSTATUS_NOTSET zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="281b8-122">If the call to `ISSCommandWithParameters::SetParameterProperties` contains some parameters where the parameter info has been set, and some parameters where the parameter info has not been set, the dwStatus properties in the DBPROPSET of the SSPARAMPROPS property set will return with DBSTATUS_NOTSET.</span></span>  
  
 <span data-ttu-id="281b8-123">Die SSPARAMPROPS-Struktur ist folgendermaßen definiert:</span><span class="sxs-lookup"><span data-stu-id="281b8-123">The SSPARAMPROPS structure is defined as follows:</span></span>  
  
 `struct SSPARAMPROPS {`  
  
 `DBORDINAL iOrdinal;`  
  
 `ULONG cPropertySets;`  
  
 `DBPROPSET *rgPropertySets;`  
  
 `};`  
  
 <span data-ttu-id="281b8-124">Verbesserungen an der Datenbank-Engine ab [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] ermöglichen das Abrufen genauerer Beschreibungen der erwarteten Ergebnisse durch ISSCommandWithParameters::SetParameterProperties.</span><span class="sxs-lookup"><span data-stu-id="281b8-124">Improvements in the database engine starting with [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] allow ISSCommandWithParameters::SetParameterProperties to obtain more accurate descriptions of the expected results.</span></span> <span data-ttu-id="281b8-125">Diese genaueren Ergebnisse unterscheiden sich möglicherweise von den Werten, die in früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] von SSCommandWithParameters::SetParameterProperties zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="281b8-125">These more accurate results may differ from the values returned by ISSCommandWithParameters::SetParameterProperties in previous versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="281b8-126">Weitere Informationen finden Sie unter [Metadatenermittlung](../native-client/features/metadata-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="281b8-126">For more information, see [Metadata Discovery](../native-client/features/metadata-discovery.md).</span></span>  
  
|<span data-ttu-id="281b8-127">Member</span><span class="sxs-lookup"><span data-stu-id="281b8-127">Member</span></span>|<span data-ttu-id="281b8-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="281b8-128">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="281b8-129">*iOrdinal*</span><span class="sxs-lookup"><span data-stu-id="281b8-129">*iOrdinal*</span></span>|<span data-ttu-id="281b8-130">Die Ordnungszahl des übergebenen Parameters</span><span class="sxs-lookup"><span data-stu-id="281b8-130">The ordinal of the passed parameter.</span></span>|  
|<span data-ttu-id="281b8-131">*cPropertySets*</span><span class="sxs-lookup"><span data-stu-id="281b8-131">*cPropertySets*</span></span>|<span data-ttu-id="281b8-132">Die Anzahl von DBPROPSET-Strukturen in *rgPropertySets*</span><span class="sxs-lookup"><span data-stu-id="281b8-132">The number of DBPROPSET structures in *rgPropertySets*.</span></span>|  
|<span data-ttu-id="281b8-133">*rgPropertySets*</span><span class="sxs-lookup"><span data-stu-id="281b8-133">*rgPropertySets*</span></span>|<span data-ttu-id="281b8-134">Ein Zeiger auf den Speicher, in den ein Array aus DBPROPSET-Strukturen zurückgegeben werden soll</span><span class="sxs-lookup"><span data-stu-id="281b8-134">A pointer to memory in which to return an array of DBPROPSET structures.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="281b8-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="281b8-135">See Also</span></span>  
 [<span data-ttu-id="281b8-136">ISSCommandWithParameters &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="281b8-136">ISSCommandWithParameters &#40;OLE DB&#41;</span></span>](isscommandwithparameters-ole-db.md)  
  
  
