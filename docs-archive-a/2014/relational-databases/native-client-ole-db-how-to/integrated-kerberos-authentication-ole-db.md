---
title: Integrierte Kerberos-Authentifizierung (OLE DB) |Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 953ee253-a4be-4f47-bbad-d2f6600207b2
author: rothja
ms.author: jroth
ms.openlocfilehash: ca39889d37e995730738c91e69cf1fe8abd94584
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616978"
---
# <a name="integrated-kerberos-authentication-ole-db"></a><span data-ttu-id="254ea-102">Integrierte Kerberos-Authentifizierung (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="254ea-102">Integrated Kerberos Authentication (OLE DB)</span></span>
  <span data-ttu-id="254ea-103">Dieses Beispiel zeigt, wie gegenseitige Kerberos-Authentifizierung mithilfe von OLE DB in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Native Client eingerichtet wird.</span><span class="sxs-lookup"><span data-stu-id="254ea-103">This sample shows how to get mutual Kerberos authentication by using OLE DB in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span></span> <span data-ttu-id="254ea-104">Dieses Beispiel wird mit [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] oder höher ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="254ea-104">This sample works with [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] or later.</span></span>  
  
 <span data-ttu-id="254ea-105">Weitere Informationen zu SPNs und Kerberos-Authentifizierung finden Sie unter [Service Principal Name &#40;SPN&#41; Support in Client Connections (Unterstützung von Dienstprinzipalnamen in Clientverbindungen)](../native-client/features/service-principal-name-spn-support-in-client-connections.md).</span><span class="sxs-lookup"><span data-stu-id="254ea-105">For more information about SPNs and Kerberos authentication, see [Service Principal Name &#40;SPN&#41; Support in Client Connections](../native-client/features/service-principal-name-spn-support-in-client-connections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="254ea-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="254ea-106">Example</span></span>  
 <span data-ttu-id="254ea-107">Sie müssen einen Server angeben.</span><span class="sxs-lookup"><span data-stu-id="254ea-107">You must specify a server.</span></span> <span data-ttu-id="254ea-108">Ändern Sie in der CPP-Datei „MyServer“ in den Namen eines Computers, auf dem sich eine Instanz von [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (oder höher) befindet.</span><span class="sxs-lookup"><span data-stu-id="254ea-108">In the .cpp file, change "MyServer" to a machine name that has an instance of [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] (or later).</span></span>  
  
 <span data-ttu-id="254ea-109">Sie müssen auch einen vom Kunden bereitgestellten SPN angeben.</span><span class="sxs-lookup"><span data-stu-id="254ea-109">You will also have to specify a customer-provided SPN.</span></span> <span data-ttu-id="254ea-110">Ändern Sie in der CPP-Datei "CPSPN" in einen vom Kunden bereitgestellten SPN.</span><span class="sxs-lookup"><span data-stu-id="254ea-110">In the .cpp file, change "CPSPN" to a customer-provided SPN.</span></span>  
  
 <span data-ttu-id="254ea-111">Stellen Sie sicher, dass die INCLUDE-Umgebungsvariable das Verzeichnis einschließt, das sqlncli.h enthält.</span><span class="sxs-lookup"><span data-stu-id="254ea-111">Make sure your INCLUDE environment variable includes the directory that contains sqlncli.h.</span></span> <span data-ttu-id="254ea-112">Kompilieren Sie mit ole32.lib und oleaut32.lib.</span><span class="sxs-lookup"><span data-stu-id="254ea-112">Compile with ole32.lib oleaut32.lib.</span></span>  
  
```  
// compile with: ole32.lib oleaut32.lib  
#pragma once  
  
#define WIN32_LEAN_AND_MEAN   // Exclude rarely-used stuff from Windows headers  
#include <stdio.h>  
#include <tchar.h>  
#include <sqlncli.h>  
  
#define CHECKHR(stmt) \  
   do { \  
      hr = (stmt); \  
      if (FAILED(hr)) { \  
         printf("CHECK_HR " #stmt " failed at (%hs, %d), hr=0x%08X\r\n", __FILE__, __LINE__, hr); \  
         goto CleanUp; \  
      } \  
   } while(0)  
  
#define CHECKVB(stmt) \  
   do { \  
      if ((stmt)!= VARIANT_TRUE) { \  
         printf("CHECK_VB " #stmt " failed at (%hs, %d)\r\n", __FILE__, __LINE__); \  
         goto CleanUp; \  
      } \  
   } while(0)  
  
#define CHECKBOOL(stmt) \  
   do { \  
      if (!(stmt)) { \  
         printf("CHECK_BOOL " #stmt " failed at (%hs, %d)\r\n", __FILE__, __LINE__); \  
        goto CleanUp; \  
      } \  
   } while(0)  
  
#define CHECKNULL(stmt) \  
   do { \  
      if ((stmt) == NULL) { \  
         printf("CHECK_NULL " #stmt " failed at (%hs, %d)\r\n", __FILE__, __LINE__); \  
         goto CleanUp; \  
      } \  
   } while(0)  
  
#define SAFERELEASE(p) \  
   do { \  
      if ((p)!= NULL) { \  
         p->Release(); \  
         p = NULL; \  
      } \  
   } while(0)  
  
#define SAFE_SYSFREESTRING(p) \  
   do { \  
      if ((p)!= NULL) { \  
         ::SysFreeString(p); \  
         p = NULL; \  
      } \  
   } while(0)  
  
int _tmain(int argc, _TCHAR* argv[]) {  
   HRESULT hr = S_OK;  
   IDBInitialize* pInitialize = NULL;  
   IDBProperties* pProperties = NULL;  
   DBPROPSET PropertySet[1];  
   DBPROP rgdbprop[1];  
   LPCWSTR lpwszProviderString = L"Server=MyServer;"   // server with SQL Server 2008 (or later)  
      L"Trusted_Connection=Yes;"  
      L"ServerSPN=CP_SPN;";   // customer-provided SPN  
   DBPROPID rgdbPropID[2];  
   DBPROPIDSET rgdbPropIDSet[1];  
   ULONG cPropertySets;  
   DBPROPSET *prgPropertySets;  
  
   CHECKHR(CoInitialize(NULL));  
   CHECKHR(CoCreateInstance(CLSID_SQLNCLI11, NULL, CLSCTX_INPROC_SERVER, __uuidof(IDBProperties), reinterpret_cast<void **>(&pProperties)));  
  
   // set provider string  
   rgdbprop[0].dwPropertyID = DBPROP_INIT_PROVIDERSTRING;  
   rgdbprop[0].dwOptions = DBPROPOPTIONS_REQUIRED;  
   rgdbprop[0].colid = DB_NULLID;  
   VariantInit(&(rgdbprop[0].vValue));  
   V_VT(&(rgdbprop[0].vValue)) = VT_BSTR;  
   V_BSTR(&(rgdbprop[0].vValue)) = SysAllocString(lpwszProviderString);  
  
   // set the property to the property set  
   PropertySet[0].rgProperties = &rgdbprop[0];  
   PropertySet[0].cProperties = 1;  
   PropertySet[0].guidPropertySet = DBPROPSET_DBINIT;  
  
   // set properties and connect to server  
   CHECKHR(pProperties->SetProperties(1, PropertySet));  
   CHECKHR(pProperties->QueryInterface(__uuidof(pInitialize), (void **)&pInitialize));  
   CHECKHR(pInitialize->Initialize());  
  
   // get properties  
   rgdbPropID[0] = SSPROP_INTEGRATEDAUTHENTICATIONMETHOD;  
   rgdbPropID[1] = SSPROP_MUTUALLYAUTHENTICATED;  
   rgdbPropIDSet[0].rgPropertyIDs = &rgdbPropID[0];  
   rgdbPropIDSet[0].cPropertyIDs = 2;  
   rgdbPropIDSet[0].guidPropertySet = DBPROPSET_SQLSERVERDATASOURCEINFO;  
  
   CHECKHR(pProperties->GetProperties(1, rgdbPropIDSet, &cPropertySets, &prgPropertySets));  
   wprintf(L"Authentication method: %s\r\n", (LPWSTR)V_BSTR(&(prgPropertySets[0].rgProperties[0].vValue)));  
   wprintf(L"Mutually authenticated: %s\r\n", (VT_BOOL == V_VT(&(prgPropertySets[0].rgProperties[1].vValue)))?L"yes":L"no");  
  
CleanUp:  
   SAFERELEASE(pProperties);  
   SAFERELEASE(pInitialize);  
  
   VariantClear(&(rgdbprop[0].vValue));  
   CoUninitialize();  
}  
```  
  
  