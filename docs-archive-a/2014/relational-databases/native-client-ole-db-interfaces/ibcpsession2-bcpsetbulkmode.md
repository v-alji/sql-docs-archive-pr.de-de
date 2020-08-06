---
title: IBCPSession2::BCPSetBulkMode | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- BCPSetBulkMode function
ms.assetid: babba19f-e67b-450c-b0e6-523a0f9d23ab
author: rothja
ms.author: jroth
ms.openlocfilehash: 9605ff9b8effde1b4a77ba0d8554c719a8a8d1e6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621498"
---
# <a name="ibcpsession2bcpsetbulkmode"></a><span data-ttu-id="03556-102">IBCPSession2::BCPSetBulkMode</span><span class="sxs-lookup"><span data-stu-id="03556-102">IBCPSession2::BCPSetBulkMode</span></span>
  <span data-ttu-id="03556-103">IBCPSession2::BCPSetBulkMode bietet eine Alternative zu [IBCPSession::BCPColFmt &#40;OLE DB&#41;](ibcpsession-bcpcolfmt-ole-db.md) zum Angeben des Spaltenformats.</span><span class="sxs-lookup"><span data-stu-id="03556-103">IBCPSession2::BCPSetBulkMode provides an alternative to [IBCPSession::BCPColFmt &#40;OLE DB&#41;](ibcpsession-bcpcolfmt-ole-db.md) for specifying the column format.</span></span> <span data-ttu-id="03556-104">Anders als bei IBCPSession::BCPColFmt, wo einzelne Spaltenformatattribute festgelegt werden, werden von IBCPSession2::BCPSetBulkMode alle Attribute festgelegt.</span><span class="sxs-lookup"><span data-stu-id="03556-104">Unlike IBCPSession::BCPColFmt, which sets individual column format attributes, IBCPSession2::BCPSetBulkMode sets all attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03556-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="03556-105">Syntax</span></span>  
  
```  
  
HRESULT BCPSetBulkMode (  
      int property,  
   void * pField,  
   int cbField,  
   void * pRow,  
   int cbRow  
);  
```  
  
## <a name="arguments"></a><span data-ttu-id="03556-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="03556-106">Arguments</span></span>  
 <span data-ttu-id="03556-107">*property*</span><span class="sxs-lookup"><span data-stu-id="03556-107">*property*</span></span>  
 <span data-ttu-id="03556-108">Eine Konstante vom Typ BYTE.</span><span class="sxs-lookup"><span data-stu-id="03556-108">A constant of type BYTE.</span></span> <span data-ttu-id="03556-109">Eine Liste der Konstanten finden Sie in der Tabelle im Abschnitt mit Hinweisen.</span><span class="sxs-lookup"><span data-stu-id="03556-109">See the table in the Remarks section for a list of the constants.</span></span>  
  
 <span data-ttu-id="03556-110">*pField*</span><span class="sxs-lookup"><span data-stu-id="03556-110">*pField*</span></span>  
 <span data-ttu-id="03556-111">Der Zeiger auf den Wert des Feldabschlusszeichens.</span><span class="sxs-lookup"><span data-stu-id="03556-111">The pointer to the field terminator value.</span></span>  
  
 <span data-ttu-id="03556-112">cbField</span><span class="sxs-lookup"><span data-stu-id="03556-112">cbField</span></span>  
 <span data-ttu-id="03556-113">Die Länge in Bytes des Feldabschlusszeichenwerts.</span><span class="sxs-lookup"><span data-stu-id="03556-113">The length in bytes of the field terminator value.</span></span>  
  
 <span data-ttu-id="03556-114">pRow</span><span class="sxs-lookup"><span data-stu-id="03556-114">pRow</span></span>  
 <span data-ttu-id="03556-115">Der Zeiger auf den Wert des Zeilenabschlusszeichens.</span><span class="sxs-lookup"><span data-stu-id="03556-115">The pointer to the row terminator value.</span></span>  
  
 <span data-ttu-id="03556-116">cbRow</span><span class="sxs-lookup"><span data-stu-id="03556-116">cbRow</span></span>  
 <span data-ttu-id="03556-117">Die Länge in Bytes des Zeilenabschlusszeichenwerts.</span><span class="sxs-lookup"><span data-stu-id="03556-117">The length in bytes of the row terminator value.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="03556-118">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="03556-118">Returns</span></span>  
 <span data-ttu-id="03556-119">IBCPSession2::BCPSetBulkMode kann einen der folgenden Werte zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="03556-119">IBCPSession2::BCPSetBulkMode can return one of the following:</span></span>  
  
|||  
|-|-|  
|`S_OK`|<span data-ttu-id="03556-120">Die Methode wurde erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="03556-120">The method succeeded.</span></span>|  
|`E_FAIL`|<span data-ttu-id="03556-121">Ein anbieterspezifischer Fehler ist aufgetreten. Ausführliche Informationen erhalten Sie über die ISQLServerErrorInfo-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="03556-121">A provider specific error occurred, for detailed information use the ISQLServerErrorInfo interface.</span></span>|  
|`E_UNEXPECTED`|<span data-ttu-id="03556-122">Die Methode wurde unerwartet aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="03556-122">The call to the method was unexpected.</span></span> <span data-ttu-id="03556-123">Beispielsweise wurde die- `IBCPSession2::BCPInit` Methode nicht aufgerufen, bevor IBCPSession2:: bcpsetbulkmode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="03556-123">For example, the `IBCPSession2::BCPInit` method was not called before calling IBCPSession2::BCPSetBulkMode.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="03556-124">Das Argument war ungültig.</span><span class="sxs-lookup"><span data-stu-id="03556-124">The argument was invalid.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="03556-125">Fehler aufgrund von nicht genügend Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="03556-125">Out of memory error.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="03556-126">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="03556-126">Remarks</span></span>  
 <span data-ttu-id="03556-127">IBCPSession2::BCPSetBulkMode kann für einen Massenkopiervorgang aus einer Abfrage oder Tabelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="03556-127">IBCPSession2::BCPSetBulkMode can be used to bulk copy out of either a query or a table.</span></span> <span data-ttu-id="03556-128">Wenn IBCPSession2::BCPSetBulkMode zum Massenkopieren aus einer Abfrageanweisung verwendet wird, muss es vor dem Aufruf von `IBCPSession::BCPControl(BCP_OPTIONS_HINTS, ...)` aufgerufen werden, um die Abfrageanweisung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="03556-128">When IBCPSession2::BCPSetBulkMode is used to bulk copy out of a query statement, it must be called before calling `IBCPSession::BCPControl(BCP_OPTIONS_HINTS, ...)` to specify the query statement.</span></span>  
  
 <span data-ttu-id="03556-129">Kombinieren Sie nicht in einem einzelnen Befehlstext die RPC-Aufrufsyntax mit der Batchabfragesyntax (z. B.`{rpc func};SELECT * from Tbl`).</span><span class="sxs-lookup"><span data-stu-id="03556-129">You should avoid combining RPC call syntax with batch query syntax (`{rpc func};SELECT * from Tbl`, for example) in a single command text.</span></span>  <span data-ttu-id="03556-130">Dies bewirkt, dass ICommandPrepare::Prepare einen Fehler zurückgibt, und verhindert das Abrufen von Metadaten.</span><span class="sxs-lookup"><span data-stu-id="03556-130">This will cause ICommandPrepare::Prepare to return an error and prevent you from retrieving metadata.</span></span> <span data-ttu-id="03556-131">Verwenden Sie ODBC CALL-Syntax (z. B.`{call func}; SELECT * from Tbl`), wenn Sie die Ausführung gespeicherter Prozeduren und die Batchabfrage in einem einzelnen Befehlstext kombinieren müssen.</span><span class="sxs-lookup"><span data-stu-id="03556-131">Use ODBC CALL syntax (`{call func}; SELECT * from Tbl`, for example) if you need to combine stored procedure execution and batch query in a single command text.</span></span>  
  
 <span data-ttu-id="03556-132">In der folgenden Tabelle sind die Konstanten für den *property* -Parameter aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="03556-132">The following table lists the constants for the *property* parameter.</span></span>  
  
|<span data-ttu-id="03556-133">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="03556-133">Property</span></span>|<span data-ttu-id="03556-134">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="03556-134">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="03556-135">BCP_OUT_CHARACTER_MODE</span><span class="sxs-lookup"><span data-stu-id="03556-135">BCP_OUT_CHARACTER_MODE</span></span>|<span data-ttu-id="03556-136">Gibt den Zeichenausgabemodus an.</span><span class="sxs-lookup"><span data-stu-id="03556-136">Specifies character output mode.</span></span><br /><br /> <span data-ttu-id="03556-137">Entspricht der Option-c in BCP.EXE und der IBCPSession:: BCPColFmt-Eigenschaft mit der *eUserDataType* -Eigenschaft, die auf festgelegt ist `BCP_TYPE_SQLCHARACTER` .</span><span class="sxs-lookup"><span data-stu-id="03556-137">Corresponds to the -c option in BCP.EXE, and to IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_SQLCHARACTER`.</span></span>|  
|<span data-ttu-id="03556-138">BCP_OUT_WIDE_CHARACTER_MODE</span><span class="sxs-lookup"><span data-stu-id="03556-138">BCP_OUT_WIDE_CHARACTER_MODE</span></span>|<span data-ttu-id="03556-139">Gibt den Unicode-Ausgabemodus an.</span><span class="sxs-lookup"><span data-stu-id="03556-139">Specifies Unicode output mode.</span></span><br /><br /> <span data-ttu-id="03556-140">Entspricht der Option-w in BCP.EXE und der IBCPSession:: BCPColFmt mit der *eUserDataType* -Eigenschaft ist auf festgelegt `BCP_TYPE_SQLNCHAR` .</span><span class="sxs-lookup"><span data-stu-id="03556-140">Corresponds to the -w option in BCP.EXE and IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_SQLNCHAR`.</span></span>|  
|<span data-ttu-id="03556-141">BCP_OUT_NATIVE_TEXT_MODE</span><span class="sxs-lookup"><span data-stu-id="03556-141">BCP_OUT_NATIVE_TEXT_MODE</span></span>|<span data-ttu-id="03556-142">Gibt systemeigene Typen für Nicht-Zeichen-Typen und Unicode für Zeichentypen an.</span><span class="sxs-lookup"><span data-stu-id="03556-142">Specifies native types for non-character types and Unicode for character types.</span></span><br /><br /> <span data-ttu-id="03556-143">Entspricht der Option-N in BCP.EXE und der IBCPSession:: BCPColFmt mit der *eUserDataType* -Eigenschaft, die auf festgelegt `BCP_TYPE_SQLNCHAR` ist, wenn der Spaltentyp eine Zeichenfolge oder `BCP_TYPE_DEFAULT` keine Zeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="03556-143">Corresponds to the -N option in BCP.EXE and IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_SQLNCHAR` if the column type is a string or `BCP_TYPE_DEFAULT` if not a string.</span></span>|  
|<span data-ttu-id="03556-144">BCP_OUT_NATIVE_MODE</span><span class="sxs-lookup"><span data-stu-id="03556-144">BCP_OUT_NATIVE_MODE</span></span>|<span data-ttu-id="03556-145">Gibt systemeigene Datenbanktypen an.</span><span class="sxs-lookup"><span data-stu-id="03556-145">Specifies native database types.</span></span><br /><br /> <span data-ttu-id="03556-146">Entspricht der Option-n in BCP.EXE und der IBCPSession:: BCPColFmt mit der *eUserDataType* -Eigenschaft ist auf festgelegt `BCP_TYPE_DEFAULT` .</span><span class="sxs-lookup"><span data-stu-id="03556-146">Corresponds to the -n option in BCP.EXE and IBCPSession::BCPColFmt with *eUserDataType* property set to `BCP_TYPE_DEFAULT`.</span></span>|  
  
 <span data-ttu-id="03556-147">Sie können IBCPSession::BCPControl und IBCPSession2::BCPSetBulkMode für IBCPSession::BCPControl-Optionen aufrufen, die nicht mit IBCPSession2::BCPSetBulkMode in Konflikt stehen.</span><span class="sxs-lookup"><span data-stu-id="03556-147">You can call IBCPSession::BCPControl and IBCPSession2::BCPSetBulkMode for IBCPSession::BCPControl options that do not conflict with IBCPSession2::BCPSetBulkMode.</span></span> <span data-ttu-id="03556-148">Beispielsweise können Sie IBCPSession:: BCPControl mit `BCP_OPTION_FIRST` und IBCPSession2:: bcpsetbulkmode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="03556-148">For example, you can call IBCPSession::BCPControl with `BCP_OPTION_FIRST` and IBCPSession2::BCPSetBulkMode.</span></span>  
  
 <span data-ttu-id="03556-149">Sie können IBCPSession:: BCPControl mit `BCP_OPTION_TEXTFILE` und IBCPSession2:: bcpsetbulkmode nicht aufrufen.</span><span class="sxs-lookup"><span data-stu-id="03556-149">You cannot call IBCPSession::BCPControl with `BCP_OPTION_TEXTFILE` and IBCPSession2::BCPSetBulkMode.</span></span>  
  
 <span data-ttu-id="03556-150">Wenn Sie versuchen, IBCPSession2::BCPSetBulkMode mit einer Sequenz von Funktionsaufrufen aufzurufen, die IBCPSession::BCPColFmt, IBCPSession::BCPControl und IBCPSession::BCPReadFmt umfasst, gibt einer der Funktionsaufrufe einen Sequenzfehler zurück.</span><span class="sxs-lookup"><span data-stu-id="03556-150">If you attempt to call IBCPSession2::BCPSetBulkMode with a sequence of function calls that includes IBCPSession::BCPColFmt, IBCPSession::BCPControl, and IBCPSession::BCPReadFmt, one of the function calls will return a sequence error failure.</span></span> <span data-ttu-id="03556-151">Wenn Sie den Fehler korrigieren möchten, rufen Sie IBCPSession::BCPInit auf, um die Einstellungen zurückzusetzen und den Vorgang neu zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="03556-151">If you choose to correct the failure, call IBCPSession::BCPInit to reset the settings and start over.</span></span>  
  
 <span data-ttu-id="03556-152">In der folgenden Tabelle werden einige Beispiele für Funktionsaufrufe dargestellt, die zu einem Funktionssequenzfehler führen:</span><span class="sxs-lookup"><span data-stu-id="03556-152">The following table presents some examples of function calls that result in a function sequence error:</span></span>  
  
 <span data-ttu-id="03556-153">Aufrufsequenz</span><span class="sxs-lookup"><span data-stu-id="03556-153">Call sequence</span></span>  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_IN);  
BCPSetBulkMode();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPSetBulkMode();  
BCPReadFmt();  
```  
  
```  
BCPInit(NULL, "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_HINTS, "select ...");  
BCPSetBulkMode();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPSetBulkMode();  
BCPColFmt();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPReadFmt();  
BCPColFmt();  
```  
  
```  
BCPInit(NULL, "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPSetBulkMode();  
BCPControl(BCP_OPTION_HINTS, "select ...");  
BCPReadFmt();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPColumns();  
```  
  
```  
BCPInit("table", "dataFile", "errorFile", BCP_DIRECTION_OUT);  
BCPControl(BCP_OPTION_DELAYREADFMT, true);  
BCPSetColFmt();  
```  
  
## <a name="example"></a><span data-ttu-id="03556-154">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03556-154">Example</span></span>  
 <span data-ttu-id="03556-155">Im folgenden Beispiel werden vier Dateien mit unterschiedlichen Einstellungen von IBCPSession2::BCPSetBulkMode erstellt.</span><span class="sxs-lookup"><span data-stu-id="03556-155">The following sample creates four files using different settings of IBCPSession2::BCPSetBulkMode.</span></span>  
  
```  
  
// compile with: sqlncli11.lib oleaut32.lib ole32.lib  
  
#include <stdio.h>  
#include "sqlncli.h"  
  
IDBInitialize*  g_pIDBInitialize = NULL;  
IBCPSession2 * g_pIBcpSession = NULL;  
class COLEDBPropSet : public DBPROPSET {  
public:  
   COLEDBPropSet() {  
      rgProperties = NULL;  
      cProperties = 0;  
   };  
   COLEDBPropSet(const GUID& guid) {  
      rgProperties = NULL;  
      cProperties = 0;  
      guidPropertySet = guid;  
   };  
   ~COLEDBPropSet() {  
      for ( ULONG i = 0 ; i < cProperties ; i++ )  
         VariantClear(&rgProperties[i].vValue);  
      CoTaskMemFree(rgProperties);  
   }  
   void SetGUID(const GUID& guid) {  
      guidPropertySet = guid;  
   };  
   bool AddProperty(DWORD dwPropertyID, bool bValue) {  
      if (!Add())  
         return false;  
      rgProperties[cProperties].dwPropertyID = dwPropertyID;  
      rgProperties[cProperties].vValue.vt = VT_BOOL;  
      rgProperties[cProperties].vValue.boolVal = (bValue) ? VARIANT_TRUE : VARIANT_FALSE;  
      cProperties++;  
      return true;  
   };  
   bool AddProperty(DWORD dwPropertyID, long nValue) {  
      if (!Add())  
         return false;  
      rgProperties[cProperties].dwPropertyID  = dwPropertyID;  
      rgProperties[cProperties].vValue.vt     = VT_I4;  
      rgProperties[cProperties].vValue.lVal   = nValue;  
      cProperties++;  
      return true;  
   };  
   bool AddProperty(DWORD dwPropertyID,LPCWSTR szValue) {  
      if (!Add())  
         return false;  
      rgProperties[cProperties].dwPropertyID = dwPropertyID;  
      rgProperties[cProperties].vValue.vt = VT_BSTR;  
      rgProperties[cProperties].vValue.bstrVal = SysAllocString(szValue);  
      cProperties++;  
      return true;  
   };  
   bool Add() {  
      DBPROP* p = (DBPROP*)CoTaskMemRealloc(rgProperties, (cProperties + 1) * sizeof(DBPROP));  
      if (p != NULL) {  
         rgProperties = p;  
         rgProperties[cProperties].dwOptions = DBPROPOPTIONS_REQUIRED;  
         rgProperties[cProperties].colid = DB_NULLID;  
         rgProperties[cProperties].vValue.vt = VT_EMPTY;  
         return true;  
      }  
      else  
         return false;  
   };  
};  
  
void OLEDBCleanUp() {  
   if (g_pIDBInitialize) {  
      g_pIDBInitialize->Release();  
      g_pIDBInitialize = NULL;  
   }  
   if (g_pIBcpSession) {  
      g_pIBcpSession->Release();  
      g_pIBcpSession = NULL;  
   }  
}  
  
BOOL MakeOLEDBConnect(LPWSTR  pServer) {  
   BOOL ret = true;  
   IDBProperties * pIDBProperties = NULL;  
   IDBCreateSession * pIDBCreateSession = NULL;  
   COLEDBPropSet PropSet(DBPROPSET_DBINIT);  
   COLEDBPropSet BcpProperty(DBPROPSET_SQLSERVERDATASOURCE);  
   try {  
      HRESULT hr = CoInitializeEx(NULL,COINIT_MULTITHREADED);   
      hr = CoCreateInstance(SQLNCLI_CLSID, NULL, CLSCTX_INPROC_SERVER, IID_IDBInitialize, (LPVOID *)&g_pIDBInitialize);  
      if (FAILED(hr)) {  
         printf("CoCreateInstance failed\n");  
         return false;  
      }  
      PropSet.AddProperty(DBPROP_INIT_DATASOURCE, (LPWSTR)pServer);  
      PropSet.AddProperty(DBPROP_AUTH_INTEGRATED, L"SSPI");  
      hr = g_pIDBInitialize->QueryInterface(IID_IDBProperties, (void**) &pIDBProperties);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->QueryInterface(IID_IDBProperties...) failed\n");  
         throw false;  
      }  
      hr = pIDBProperties->SetProperties(1, &PropSet);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->SetProperties(...) failed\n");  
         throw false;  
      }  
      hr = g_pIDBInitialize->Initialize();  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->Initialize() failed\n");  
         throw false;  
      }  
      BcpProperty.AddProperty(SSPROP_ENABLEFASTLOAD, true);  
      BcpProperty.AddProperty(SSPROP_ENABLEBULKCOPY, true);  
      hr = pIDBProperties->SetProperties(1, &BcpProperty);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->->SetProperties() for bcp failed\n");  
         throw false;  
      }  
      hr = g_pIDBInitialize->QueryInterface(IID_IDBCreateSession, (void**) &pIDBCreateSession);  
      if (FAILED(hr)) {  
         printf("g_pIDBInitialize->QueryInterface(IID_IDBCreateSession..) failed\n");  
         throw false;  
      }  
  
      hr = pIDBCreateSession->CreateSession(NULL, IID_IBCPSession2, (IUnknown**) &g_pIBcpSession);  
      if (FAILED(hr)) {  
         printf("g_pIDBCreateSession->CreateSession() failed\n");  
         throw false;  
      }  
   }  
   catch(...) {  
      ret = false;  
   }  
   if (pIDBProperties)  
      pIDBProperties->Release();  
   if (pIDBCreateSession)  
      pIDBCreateSession->Release();  
   return ret;  
}  
  
BOOL BCPSetBulkMode(LPWSTR pszServer, LPTSTR pszQureryOut, char BCPType, LPWSTR pszDataFile) {  
   HRESULThr;  
   if (!MakeOLEDBConnect(pszServer))  
      return false;  
   hr = g_pIBcpSession->BCPInit(NULL, pszDataFile, NULL, BCP_DIRECTION_OUT );   // bcp init for queryout  
   if (FAILED(hr)) {  
      printf("BCP init failed\n");  
      OLEDBCleanUp();  
      return false;  
   }  
   // setbulkmode  
   char ColTerm[] = "\t";  
   char RowTerm[] = "\r\n";  
   wchar_t wColTerm[] = L"\t";  
   wchar_t wRowTerm[] = L"\r\n";  
   BYTE * pColTerm = NULL;  
   int cbColTerm = NULL;  
   BYTE * pRowTerm = 0;  
   int cbRowTerm = 0;  
   int bulkmode = -1;  
  
   if(BCPType == 'c') {   // bcp -c  
      pColTerm = (BYTE*)ColTerm;  
      pRowTerm = (BYTE*)RowTerm;  
      cbColTerm = 1;  
      cbRowTerm = 2;  
      bulkmode = BCP_OUT_CHARACTER_MODE;  
   }  
   else  
      if(BCPType == 'w') {   // bcp -w  
         pColTerm = (BYTE*)wColTerm;  
         pRowTerm = (BYTE*)wRowTerm;  
         cbColTerm = 2;  
         cbRowTerm = 4;  
         bulkmode = BCP_OUT_WIDE_CHARACTER_MODE;  
      }  
      else  
         if (BCPType == 'n')   // bcp -n  
            bulkmode = BCP_OUT_NATIVE_MODE;  
         else  
            if (BCPType == 'N')   // bcp -n  
               bulkmode = BCP_OUT_NATIVE_TEXT_MODE;  
            else {  
               printf("unknown bcp mode\n");  
               OLEDBCleanUp();  
               return false;  
            }  
            hr = g_pIBcpSession->BCPSetBulkMode(bulkmode, pColTerm, cbColTerm, pRowTerm, cbRowTerm);  
            if (FAILED(hr)) {  
               printf("BCPSetBulkMode failed\n");  
               OLEDBCleanUp();  
               return false;  
            }  
  
            // set queryout TSQL statement  
            hr = g_pIBcpSession->BCPControl(BCP_OPTION_HINTS, pszQureryOut);  
            if (FAILED(hr)) {  
               printf("BCPControl failed\n");  
               OLEDBCleanUp();  
               return false;  
            }  
            // bcp copy  
            DBROWCOUNT nRowsInserted = 0;  
            hr = g_pIBcpSession->BCPExec(&nRowsInserted);  
            if (FAILED(hr)) {  
               printf("BCPExec failed\n");  
               OLEDBCleanUp();  
               return false;  
            }  
            printf("bcp done\n");  
            OLEDBCleanUp();  
            return true;  
}  
  
int main() {  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -c test', 1,2") , 'c', L"bcpc.dat");  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -w test', 1,2") , 'w', L"bcpw.dat");  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -c test', 1,2") , 'n', L"bcpn.dat");  
   BCPSetBulkMode(L"localhost", TEXT("SELECT 'this is a bcp -w test', 1,2") , 'N', L"bcp_N.dat");  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="03556-156">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="03556-156">See Also</span></span>  
 [<span data-ttu-id="03556-157">IBCPSession2 &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="03556-157">IBCPSession2 &#40;OLE DB&#41;</span></span>](ibcpsession2-ole-db.md)  
  
  
