---
title: Imdembedded-Schnittstelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 9dba8c68-4bef-4c2b-815c-c286f1a1939b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 331f8c33f7748e6591acd6d6ecda7a03ef7d8137
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616232"
---
# <a name="imdembedded-interface"></a><span data-ttu-id="17b86-102">IMDEmbedded-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17b86-102">IMDEmbedded Interface</span></span>
  <span data-ttu-id="17b86-103">Die IMDEmbedded-Schnittstelle ist eine öffentliche Schnittstelle, die verwendet wurde, um eine eingebettete PowerPivot-Datenbank oder eine tabellarische Modelldatenbank zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="17b86-103">The IMDEmbedded interface is a public interface used to manage an embedded PowerPivot database or a tabular model database.</span></span> <span data-ttu-id="17b86-104">Die Schnittstelle erbt von der `IPersistStream`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="17b86-104">The interface inherits from the `IPersistStream` interface.</span></span> <span data-ttu-id="17b86-105">Die Schnittstelle lässt folgende Vorgänge zu:</span><span class="sxs-lookup"><span data-stu-id="17b86-105">The interface allows for the following operations:</span></span>  
  
-   <span data-ttu-id="17b86-106">Ruft einen Bezeichner in den eingebetteten Datenstrom im Containerdokument ab.</span><span class="sxs-lookup"><span data-stu-id="17b86-106">Get an identifier to the embedded stream in the container document.</span></span>  
  
-   <span data-ttu-id="17b86-107">Legt die URL des Containerdokuments fest.</span><span class="sxs-lookup"><span data-stu-id="17b86-107">Set the URL of the containing document.</span></span>  
  
-   <span data-ttu-id="17b86-108">Legt ein Flag fest, das angibt, ob sich die Einbettungsanwendung in einer gehosteten Umgebung befindet.</span><span class="sxs-lookup"><span data-stu-id="17b86-108">Set a flag to indicate if the embedding application is in a hosted environment.</span></span>  
  
-   <span data-ttu-id="17b86-109">Legt den Pfad zu den von der Einbettungsanwendung verwendeten temporären Dateien fest.</span><span class="sxs-lookup"><span data-stu-id="17b86-109">Set the path to temporary files used by the embedding application.</span></span>  
  
-   <span data-ttu-id="17b86-110">Bricht den aktuellen Einbettungsvorgang ab.</span><span class="sxs-lookup"><span data-stu-id="17b86-110">Cancel the current embedded operation.</span></span>  
  
-   <span data-ttu-id="17b86-111">Gibt die geschätzte Größe (in Bytes) des Datenstroms zum Speichern des eingebetteten Objekts an.</span><span class="sxs-lookup"><span data-stu-id="17b86-111">Get the estimated size (in bytes) of the stream to save the embedded object.</span></span> <span data-ttu-id="17b86-112">Wird von `IPersistStream` geerbt.</span><span class="sxs-lookup"><span data-stu-id="17b86-112">Inherited from `IPersistStream`.</span></span>  
  
-   <span data-ttu-id="17b86-113">Überprüfen Sie, ob die eingebettete Datenbank seit dem letzten Speichern geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="17b86-113">Verify if the embedded database has changed since it was last saved.</span></span> <span data-ttu-id="17b86-114">Wird von `IPersistStream` geerbt.</span><span class="sxs-lookup"><span data-stu-id="17b86-114">Inherited from `IPersistStream`.</span></span>  
  
-   <span data-ttu-id="17b86-115">Laden Sie die eingebettete Datenbank in die lokale oder Prozess interne Engine.</span><span class="sxs-lookup"><span data-stu-id="17b86-115">Load the embedded database to the local or in-process engine.</span></span> <span data-ttu-id="17b86-116">Wird von `IPersistStream` geerbt.</span><span class="sxs-lookup"><span data-stu-id="17b86-116">Inherited from `IPersistStream`.</span></span>  
  
-   <span data-ttu-id="17b86-117">Speichert die lokale oder prozessinterne Datenbank im eingebetteten Datenstrom im Containerdokument.</span><span class="sxs-lookup"><span data-stu-id="17b86-117">Save the local or in-process database to the embedded stream in the container document.</span></span> <span data-ttu-id="17b86-118">Wird von `IPersistStream` geerbt.</span><span class="sxs-lookup"><span data-stu-id="17b86-118">Inherited from `IPersistStream`.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="17b86-119">Verweis</span><span class="sxs-lookup"><span data-stu-id="17b86-119">Reference</span></span>  
 <span data-ttu-id="17b86-120">Der folgende Verweis dokumentiert die- `IMDEmbedded` Schnittstelle, wie in der **Msmd. h** -Header Datei dargestellt.</span><span class="sxs-lookup"><span data-stu-id="17b86-120">The following reference documents the `IMDEmbedded` interface as presented in **msmd.h** header file.</span></span>  
  
### <a name="source-file-pxoembeddeddataidl"></a><span data-ttu-id="17b86-121">Quelldatei: PXOEmbeddedData.idl</span><span class="sxs-lookup"><span data-stu-id="17b86-121">Source file: PXOEmbeddedData.idl</span></span>  
  
```  
[  
  local,                            
  object,                           
  uuid(6B6691CF-5453-41c2-ADD9-4F320B7FD421),                       
  pointer_default(unique)           
]  
interface IMDEmbeddedData : IPersistStream  
{  
 [id(1), helpstring("Set flag indicating if the application is in a hosted environment")]   
 HRESULT SetHosted(  
  [in] BOOL in_fIsHosted);  
  
 [id(2), helpstring("Set the URL for the document containing the embedded stream")]   
 HRESULT SetContainerURL(  
  [in] BSTR in_bstrURL);  
  
 [id(3), helpstring("Get identifier used to look up embedded stream in container document")]   
 HRESULT GetStreamIdentifier(  
  [out, retval] BSTR* out_pbstrStreamId);  
  
 [id(4), helpstring("Set the path used by the embedding application for temporary files")]   
 HRESULT SetTempDirPath(  
  [in]  BSTR in_bstrPath);  
  
 [id(5), helpstring("Cancel the current operation")]   
 HRESULT Cancel();  
};  
```  
  
### <a name="imdembeddeddatagetstreamidentifier"></a><span data-ttu-id="17b86-122">IMDEmbeddedData::GetStreamIdentifier</span><span class="sxs-lookup"><span data-stu-id="17b86-122">IMDEmbeddedData::GetStreamIdentifier</span></span>  
  
```  
HRESULT GetStreamIdentifier (  
    [out, retval] BSTR * out_pbstrStreamId  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="17b86-123">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="17b86-123">Description</span></span>  
 <span data-ttu-id="17b86-124">Ruft den von der Hostanwendung verwendeten Bezeichner in den eingebetteten Datenstrom im Containerdokument ab.</span><span class="sxs-lookup"><span data-stu-id="17b86-124">Gets the identifier used by the host application to the embedded stream in the container document.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="17b86-125">Parameter</span><span class="sxs-lookup"><span data-stu-id="17b86-125">Parameters</span></span>  
 <span data-ttu-id="17b86-126">*out_pbstrStreamId*</span><span class="sxs-lookup"><span data-stu-id="17b86-126">*out_pbstrStreamId*</span></span>  
 <span data-ttu-id="17b86-127">Gibt die Position des Datenstrombezeichners an.</span><span class="sxs-lookup"><span data-stu-id="17b86-127">Specifies the location of the stream identifier.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="17b86-128">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="17b86-128">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="17b86-129">Der Datenstrombezeichner wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="17b86-129">The stream identifier was successfully returned.</span></span>  
  
 `S_FALSE`  
 <span data-ttu-id="17b86-130">Es ist kein Datenstrombezeichner vorhanden.</span><span class="sxs-lookup"><span data-stu-id="17b86-130">There is no stream identifier.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="17b86-131">Beim Zugriff auf den Datenstrombezeichner ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="17b86-131">An error occurred accessing the stream identifier.</span></span>  
  
#### <a name="remarks"></a><span data-ttu-id="17b86-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="17b86-132">Remarks</span></span>  
 <span data-ttu-id="17b86-133">Um zu überprüfen, ob die aktuelle Verbindung eine eingebettete Datenbank enthält, sollte der Benutzer den Wert der DBPROP_MSMD_EMBEDDED_DATA-Eigenschaft in den OLE DB-Verbindungseigenschaften überprüfen.</span><span class="sxs-lookup"><span data-stu-id="17b86-133">To verify if the current connection contains an embedded database, the user should check the value of the DBPROP_MSMD_EMBEDDED_DATA property from the OLE DB connection properties.</span></span>  
  
 <span data-ttu-id="17b86-134">Die möglichen Werte für DBPROP_MSMD_EMBEDDED_DATA lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="17b86-134">The possible values for DBPROP_MSMD_EMBEDDED_DATA are:</span></span>  
  
|<span data-ttu-id="17b86-135">Name</span><span class="sxs-lookup"><span data-stu-id="17b86-135">Name</span></span>|<span data-ttu-id="17b86-136">Wert</span><span class="sxs-lookup"><span data-stu-id="17b86-136">Value</span></span>|<span data-ttu-id="17b86-137">Definition</span><span class="sxs-lookup"><span data-stu-id="17b86-137">Definition</span></span>|  
|----------|-----------|----------------|  
|<span data-ttu-id="17b86-138">DBPROPVAL_EMBED_NONE</span><span class="sxs-lookup"><span data-stu-id="17b86-138">DBPROPVAL_EMBED_NONE</span></span>|<span data-ttu-id="17b86-139">0x00</span><span class="sxs-lookup"><span data-stu-id="17b86-139">0x00</span></span>|<span data-ttu-id="17b86-140">Es ist keine eingebettete Datenbank verfügbar.</span><span class="sxs-lookup"><span data-stu-id="17b86-140">No embedded database available</span></span>|  
|<span data-ttu-id="17b86-141">DBPROPVAL_EMBED_EMBEDDED</span><span class="sxs-lookup"><span data-stu-id="17b86-141">DBPROPVAL_EMBED_EMBEDDED</span></span>|<span data-ttu-id="17b86-142">0x01</span><span class="sxs-lookup"><span data-stu-id="17b86-142">0x01</span></span>|<span data-ttu-id="17b86-143">Die aktuelle Anwendung enthält die eingebettete Datenbank.</span><span class="sxs-lookup"><span data-stu-id="17b86-143">The current application contains the embedded database</span></span>|  
|<span data-ttu-id="17b86-144">DBPROPVAL_EMBED_LINKED</span><span class="sxs-lookup"><span data-stu-id="17b86-144">DBPROPVAL_EMBED_LINKED</span></span>|<span data-ttu-id="17b86-145">0x02</span><span class="sxs-lookup"><span data-stu-id="17b86-145">0x02</span></span>|<span data-ttu-id="17b86-146">Die eingebettete Datenbank wird in einer Remote Anwendung (d. h. SharePoint Server) gehostet.</span><span class="sxs-lookup"><span data-stu-id="17b86-146">The embedded database is hosted in a remote application (i.e. SharePoint Server)</span></span>|  
  
#### <a name="source"></a><span data-ttu-id="17b86-147">`Source`</span><span class="sxs-lookup"><span data-stu-id="17b86-147">Source</span></span>  
  
```  
[id(1), helpstring("Get identifier used to look up embedded stream in container document")]   
 HRESULT GetStreamIdentifier(  
  [out, retval] BSTR* out_pbstrStreamId);  
```  
  
### <a name="imdembeddeddatasetcontainerurl"></a><span data-ttu-id="17b86-148">IMDEmbeddedData::SetContainerURL</span><span class="sxs-lookup"><span data-stu-id="17b86-148">IMDEmbeddedData::SetContainerURL</span></span>  
  
```  
HRESULT SetContainerURL (  
    [in] BSTR in_bstrURL  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="17b86-149">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="17b86-149">Description</span></span>  
 <span data-ttu-id="17b86-150">Legt die URL für die Datei fest, die den eingebetteten Datenstrom enthält.</span><span class="sxs-lookup"><span data-stu-id="17b86-150">Sets the URL for the file containing the embedded stream.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="17b86-151">Parameter</span><span class="sxs-lookup"><span data-stu-id="17b86-151">Parameters</span></span>  
 <span data-ttu-id="17b86-152">*in_bstrURL*</span><span class="sxs-lookup"><span data-stu-id="17b86-152">*in_bstrURL*</span></span>  
 <span data-ttu-id="17b86-153">Gibt die URL für das Containerdokument an.</span><span class="sxs-lookup"><span data-stu-id="17b86-153">Specifies the URL for the containing document.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="17b86-154">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="17b86-154">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="17b86-155">Die Container-URL wurde erfolgreich festgelegt.</span><span class="sxs-lookup"><span data-stu-id="17b86-155">The container URL was successfully set.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="17b86-156">Beim Festlegen der Container-URL ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="17b86-156">An error occurred while setting the container URL.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="17b86-157">`Source`</span><span class="sxs-lookup"><span data-stu-id="17b86-157">Source</span></span>  
  
```  
[id(2), helpstring("Set the URL for the document containing the embedded stream")]   
 HRESULT SetContainerURL(  
  [in] BSTR in_bstrURL);  
```  
  
### <a name="imdembeddeddatasethosted"></a><span data-ttu-id="17b86-158">IMDEmbeddedData::SetHosted</span><span class="sxs-lookup"><span data-stu-id="17b86-158">IMDEmbeddedData::SetHosted</span></span>  
  
```  
HRESULT SetHosted (  
    [in] BOOL in_fIsHosted  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="17b86-159">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="17b86-159">Description</span></span>  
 <span data-ttu-id="17b86-160">Legt ein Flag fest, das angibt, ob sich die Einbettungsanwendung in einer gehosteten Umgebung befindet.</span><span class="sxs-lookup"><span data-stu-id="17b86-160">Set a flag to indicate if the embedding application is in a hosted environment.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="17b86-161">Parameter</span><span class="sxs-lookup"><span data-stu-id="17b86-161">Parameters</span></span>  
 <span data-ttu-id="17b86-162">*in_ftHosted*</span><span class="sxs-lookup"><span data-stu-id="17b86-162">*in_ftHosted*</span></span>  
 <span data-ttu-id="17b86-163">TRUE für Aufrufer in einer gehosteten Dienstanwendung (wie IIS)</span><span class="sxs-lookup"><span data-stu-id="17b86-163">TRUE if caller is in a hosted in a service application (like IIS).</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="17b86-164">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="17b86-164">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="17b86-165">Das Flag wurde erfolgreich festgelegt.</span><span class="sxs-lookup"><span data-stu-id="17b86-165">The flag was successfully set.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="17b86-166">Beim Festlegen des Flags ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="17b86-166">An error occurred while setting the flag.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="17b86-167">`Source`</span><span class="sxs-lookup"><span data-stu-id="17b86-167">Source</span></span>  
  
```  
[id(5), helpstring("Set flag indicating if the application is in a hosted environment")]   
 HRESULT SetHosted(  
  [in]  BOOL in_fIsHosted);  
```  
  
### <a name="imdembeddeddatasettempdirpath"></a><span data-ttu-id="17b86-168">IMDEmbeddedData::SetTempDirPath</span><span class="sxs-lookup"><span data-stu-id="17b86-168">IMDEmbeddedData::SetTempDirPath</span></span>  
  
```  
HRESULT SetTempDirPath (  
    [in] BSTR in_bstrPath  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="17b86-169">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="17b86-169">Description</span></span>  
 <span data-ttu-id="17b86-170">Legt den Pfad zu den von der Einbettungsanwendung verwendeten temporären Dateien fest.</span><span class="sxs-lookup"><span data-stu-id="17b86-170">Set the path to temporary files used by the embedding application.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="17b86-171">Parameter</span><span class="sxs-lookup"><span data-stu-id="17b86-171">Parameters</span></span>  
 <span data-ttu-id="17b86-172">*in_bstrPath*</span><span class="sxs-lookup"><span data-stu-id="17b86-172">*in_bstrPath*</span></span>  
 <span data-ttu-id="17b86-173">Der Pfad, der von der Hostanwendung für temporäre Dateien verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="17b86-173">The path used by the host application for temporary files.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="17b86-174">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="17b86-174">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="17b86-175">Das Verzeichnis für temporäre Dateien wurde erfolgreich festgelegt.</span><span class="sxs-lookup"><span data-stu-id="17b86-175">The temporary file directory was successfully set.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="17b86-176">Beim Festlegen des Pfads ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="17b86-176">An error occurred while setting the path.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="17b86-177">`Source`</span><span class="sxs-lookup"><span data-stu-id="17b86-177">Source</span></span>  
  
```  
[id(4), helpstring("Set the path used by the host application for temporary files")]   
 HRESULT SetTempDirPath(  
  [in]  BSTR in_bstrPath);  
```  
  
### <a name="imdembeddeddatacancel"></a><span data-ttu-id="17b86-178">IMDEmbeddedData::Cancel</span><span class="sxs-lookup"><span data-stu-id="17b86-178">IMDEmbeddedData::Cancel</span></span>  
  
```  
HRESULT Cancel ( void )  
```  
  
#### <a name="description"></a><span data-ttu-id="17b86-179">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="17b86-179">Description</span></span>  
 <span data-ttu-id="17b86-180">Bricht den aktuellen Vorgang für die eingebettete Datenbank ab.</span><span class="sxs-lookup"><span data-stu-id="17b86-180">Cancels the current embedded database operation</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="17b86-181">Parameter</span><span class="sxs-lookup"><span data-stu-id="17b86-181">Parameters</span></span>  
 <span data-ttu-id="17b86-182">Keine.</span><span class="sxs-lookup"><span data-stu-id="17b86-182">None.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="17b86-183">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="17b86-183">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="17b86-184">Der Vorgang wurde erfolgreich abgebrochen.</span><span class="sxs-lookup"><span data-stu-id="17b86-184">The operation was successfully cancelled.</span></span>  
  
 `DB_E_CANTCANCEL`  
 <span data-ttu-id="17b86-185">Es wird aktuell kein abbrechbarer Vorgang ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="17b86-185">No cancellable operation is currently in progress.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="17b86-186">Beim Abbrechen des eingebetteten Vorgangs ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="17b86-186">An error occurred while cancelling the embedded operation.</span></span>  
  
#### <a name="source"></a><span data-ttu-id="17b86-187">`Source`</span><span class="sxs-lookup"><span data-stu-id="17b86-187">Source</span></span>  
  
```  
[id(5), helpstring("Cancel the current operation")]   
 HRESULT Cancel();  
```  
  
### <a name="imdembeddeddatagetsizemax-ipersiststreamgetsizemax"></a><span data-ttu-id="17b86-188">IMDEmbeddedData::GetSizeMax (IPersistStream::GetSizeMax)</span><span class="sxs-lookup"><span data-stu-id="17b86-188">IMDEmbeddedData::GetSizeMax (IPersistStream::GetSizeMax)</span></span>  
  
```  
HRESULT GetSizeMax (  
    [out] ULARGE_INTEGER * out_pcbSize  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="17b86-189">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="17b86-189">Description</span></span>  
 <span data-ttu-id="17b86-190">Ruft die geschätzte Größe des Datenstroms (in Byte) zum Speichern des eingebetteten Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="17b86-190">Gets the estimated size (in bytes) of the stream to save the embedded object.</span></span> <span data-ttu-id="17b86-191">Wird von `IPersistStream` geerbt.</span><span class="sxs-lookup"><span data-stu-id="17b86-191">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="17b86-192">Parameter</span><span class="sxs-lookup"><span data-stu-id="17b86-192">Parameters</span></span>  
 <span data-ttu-id="17b86-193">*in_bstrPath*</span><span class="sxs-lookup"><span data-stu-id="17b86-193">*in_bstrPath*</span></span>  
 <span data-ttu-id="17b86-194">Die geschätzte Größe des eingebetteten Datenbankbilds (in Byte).</span><span class="sxs-lookup"><span data-stu-id="17b86-194">The estimated size (in bytes) of the embedded database image.</span></span>  
  
#### <a name="return-value"></a><span data-ttu-id="17b86-195">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="17b86-195">Return Value</span></span>  
 `S_OK`  
 <span data-ttu-id="17b86-196">Die Größe wurde erfolgreich abgerufen.</span><span class="sxs-lookup"><span data-stu-id="17b86-196">The size was successfully obtained.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="17b86-197">Beim Abrufen der Größe ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="17b86-197">An error occurred while obtaining the size.</span></span>  
  
### <a name="imdembeddeddataisdirty-ipersiststreamisdirty"></a><span data-ttu-id="17b86-198">IMDEmbeddedData::IsDirty (IPersistStream::IsDirty)</span><span class="sxs-lookup"><span data-stu-id="17b86-198">IMDEmbeddedData::IsDirty (IPersistStream::IsDirty)</span></span>  
  
```  
HRESULT IsDirty ( void )  
```  
  
#### <a name="description"></a><span data-ttu-id="17b86-199">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="17b86-199">Description</span></span>  
 <span data-ttu-id="17b86-200">Überprüft, ob sich die eingebettete Datenbank seit der letzten Speicherung geändert hat.</span><span class="sxs-lookup"><span data-stu-id="17b86-200">Verifies if the embedded database has changed since it was last saved.</span></span> <span data-ttu-id="17b86-201">Wird von `IPersistStream` geerbt.</span><span class="sxs-lookup"><span data-stu-id="17b86-201">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="17b86-202">Parameter</span><span class="sxs-lookup"><span data-stu-id="17b86-202">Parameters</span></span>  
 <span data-ttu-id="17b86-203">none</span><span class="sxs-lookup"><span data-stu-id="17b86-203">none</span></span>  
  
#### <a name="return-values"></a><span data-ttu-id="17b86-204">Rückgabewert(e)</span><span class="sxs-lookup"><span data-stu-id="17b86-204">Return Value(s)</span></span>  
 `S_OK`  
 <span data-ttu-id="17b86-205">Die Datenbank wurde seit der letzten Speicherung geändert.</span><span class="sxs-lookup"><span data-stu-id="17b86-205">The database has changed since it was last saved.</span></span>  
  
 `S_FALSE`  
 <span data-ttu-id="17b86-206">Die Datenbank wurde seit der letzten Speicherung nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="17b86-206">The database has not changed since it was last saved.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="17b86-207">Beim Abrufen des Datenbankstatus ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="17b86-207">An error occurred while obtaining the database state.</span></span>  
  
### <a name="imdembeddeddataload-ipersiststreamload"></a><span data-ttu-id="17b86-208">IMDEmbeddedData::Load (IPersistStream::Load)</span><span class="sxs-lookup"><span data-stu-id="17b86-208">IMDEmbeddedData::Load (IPersistStream::Load)</span></span>  
  
```  
HRESULT Load (   
    [in] IStream * in_pStm   
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="17b86-209">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="17b86-209">Description</span></span>  
 <span data-ttu-id="17b86-210">Lädt die eingebettete Datenbank in die lokale oder prozessinterne Engine.</span><span class="sxs-lookup"><span data-stu-id="17b86-210">Loads the embedded database to the local or in-process engine.</span></span> <span data-ttu-id="17b86-211">Wird von `IPersistStream` geerbt.</span><span class="sxs-lookup"><span data-stu-id="17b86-211">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="17b86-212">Parameter</span><span class="sxs-lookup"><span data-stu-id="17b86-212">Parameters</span></span>  
 <span data-ttu-id="17b86-213">*in_pStm*</span><span class="sxs-lookup"><span data-stu-id="17b86-213">*in_pStm*</span></span>  
 <span data-ttu-id="17b86-214">Ein Zeiger auf eine Datenstromschnittstelle, von der die eingebettete Datenbank geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="17b86-214">A pointer to a stream interface from where to load the embedded database.</span></span>  
  
#### <a name="return-values"></a><span data-ttu-id="17b86-215">Rückgabewert(e)</span><span class="sxs-lookup"><span data-stu-id="17b86-215">Return Value(s)</span></span>  
 `S_OK`  
 <span data-ttu-id="17b86-216">Die Datenbank wurde erfolgreich geladen.</span><span class="sxs-lookup"><span data-stu-id="17b86-216">The database was successfully loaded.</span></span>  
  
 `E_OUTOFMEMORY`  
 <span data-ttu-id="17b86-217">Der Arbeitsspeicher reicht zum Laden der Datenbank nicht aus.</span><span class="sxs-lookup"><span data-stu-id="17b86-217">Not enough memory to load the database.</span></span>  
  
 `E_FAIL`  
 <span data-ttu-id="17b86-218">Beim Laden der Datenbank ist ein anderer Fehler als `E_OUTOFMEMORY` aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="17b86-218">An error occurred while loading the database, different than `E_OUTOFMEMORY`.</span></span>  
  
### <a name="imdembeddeddatasave-ipersiststreamsave"></a><span data-ttu-id="17b86-219">IMDEmbeddedData::Save (IPersistStream::Save)</span><span class="sxs-lookup"><span data-stu-id="17b86-219">IMDEmbeddedData::Save (IPersistStream::Save)</span></span>  
  
```  
HRESULT Save (   
    [in] IStream * in_pStm,  
    [in] BOOL in_fClearDirty  
    )  
```  
  
#### <a name="description"></a><span data-ttu-id="17b86-220">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="17b86-220">Description</span></span>  
 <span data-ttu-id="17b86-221">Speichert die lokale oder in-Process-Datenbank im eingebetteten Datenstrom im Container Dokument.</span><span class="sxs-lookup"><span data-stu-id="17b86-221">Saves the local or in-process database to the embedded stream in the container document.</span></span> <span data-ttu-id="17b86-222">Wird von `IPersistStream` geerbt.</span><span class="sxs-lookup"><span data-stu-id="17b86-222">Inherited from `IPersistStream`.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="17b86-223">Parameter</span><span class="sxs-lookup"><span data-stu-id="17b86-223">Parameters</span></span>  
 <span data-ttu-id="17b86-224">*in_pStm*</span><span class="sxs-lookup"><span data-stu-id="17b86-224">*in_pStm*</span></span>  
 <span data-ttu-id="17b86-225">Ein Zeiger auf eine Datenstromschnittstelle, in der die eingebettete Datenbank gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="17b86-225">A pointer to a stream interface to where to save the embedded database.</span></span>  
  
 <span data-ttu-id="17b86-226">*in_fClearDirty*</span><span class="sxs-lookup"><span data-stu-id="17b86-226">*in_fClearDirty*</span></span>  
 <span data-ttu-id="17b86-227">Ein Flag, das angibt, ob das modifizierte Flag nach diesem Vorgang gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="17b86-227">A flag that indicates whether the dirty flag should be cleared after this operation.</span></span>  
  
#### <a name="return-values"></a><span data-ttu-id="17b86-228">Rückgabewert(e)</span><span class="sxs-lookup"><span data-stu-id="17b86-228">Return Value(s)</span></span>  
 `S_OK`  
 <span data-ttu-id="17b86-229">Die Datenbank wurde erfolgreich gespeichert.</span><span class="sxs-lookup"><span data-stu-id="17b86-229">The database was successfully saved.</span></span>  
  
 `STG_E_CANTSAVE`  
 <span data-ttu-id="17b86-230">Beim Speichern der Datenbank ist ein anderer Fehler als `STG_E_MEDIUMFULL` aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="17b86-230">An error occurred while saving the database, different than `STG_E_MEDIUMFULL`.</span></span>  
  
 `STG_E_MEDIUMFULL`  
 <span data-ttu-id="17b86-231">Die Datenbank konnte nicht gespeichert werden, da auf dem Speichergerät kein Speicherplatz mehr verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="17b86-231">The database could not be saved because there is no space left on the storage device.</span></span>  
  
  
