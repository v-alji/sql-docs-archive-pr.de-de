---
title: 'GetReportServerUrls-Methode (WMI: MSReportServer_Instance) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- GetReportServerUrls method
ms.assetid: 4865e32c-0114-465a-be8c-be223a7bc09e
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: f36a5ba10c05276cffabc155e5289d675db8dae7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717320"
---
# <a name="getreportserverurls-method-wmi-msreportserver_instance"></a><span data-ttu-id="d6e7e-102">GetReportServerUrls-Methode (WMI: MSReportServer_Instance)</span><span class="sxs-lookup"><span data-stu-id="d6e7e-102">GetReportServerUrls Method (WMI MSReportServer_Instance)</span></span>
  <span data-ttu-id="d6e7e-103">Gibt eine Liste von URLs zurück, über die Benutzer auf den Berichtsserver und den Berichts-Manager zugreifen können</span><span class="sxs-lookup"><span data-stu-id="d6e7e-103">Returns a list of URLs users can use to access the report server and report manager.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6e7e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6e7e-104">Syntax</span></span>  
  
```vb  
Public Sub GetReportServerUrls (ByRef ApplicationName() As String, ByRef URLs()_  
    As String, ByRef Length As Int32, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GetReportServerUrls(out string[] applicationName,   
    out string[] URLs, out int length, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6e7e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d6e7e-105">Parameters</span></span>  
 <span data-ttu-id="d6e7e-106">*ApplicationName[]*</span><span class="sxs-lookup"><span data-stu-id="d6e7e-106">*ApplicationName[]*</span></span>  
 <span data-ttu-id="d6e7e-107">Ein Array, das die installierten Anwendungen enthält.</span><span class="sxs-lookup"><span data-stu-id="d6e7e-107">An array that contains the applications that are installed.</span></span> <span data-ttu-id="d6e7e-108">Werte sind entweder `ReportServerWebService` oder `ReportManager`.</span><span class="sxs-lookup"><span data-stu-id="d6e7e-108">Values are either `ReportServerWebService` or `ReportManager`.</span></span>  
  
 <span data-ttu-id="d6e7e-109">*URLs[]*</span><span class="sxs-lookup"><span data-stu-id="d6e7e-109">*URLs[]*</span></span>  
 <span data-ttu-id="d6e7e-110">Ein Array, das die erfolgreich registrierten URLs enthält</span><span class="sxs-lookup"><span data-stu-id="d6e7e-110">An array that contains the successfully registered Urls.</span></span>  
  
 <span data-ttu-id="d6e7e-111">*Länge*</span><span class="sxs-lookup"><span data-stu-id="d6e7e-111">*Length*</span></span>  
 <span data-ttu-id="d6e7e-112">Ein Integer-Wert, der die Länge der zurückgegebenen Arrays enthält.</span><span class="sxs-lookup"><span data-stu-id="d6e7e-112">An integer value that contains the length of the arrays returned.</span></span>  
  
 <span data-ttu-id="d6e7e-113">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="d6e7e-113">*HRESULT*</span></span>  
 <span data-ttu-id="d6e7e-114">Ein Wert, der Erfolg oder einen Fehlercode angibt</span><span class="sxs-lookup"><span data-stu-id="d6e7e-114">A value that indicates success or an error code.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="d6e7e-115">Rückgabewerte</span><span class="sxs-lookup"><span data-stu-id="d6e7e-115">Return Values</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6e7e-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d6e7e-116">Remarks</span></span>  
 <span data-ttu-id="d6e7e-117">Von WMI-Verwaltungsobjekten verfügbar gemachte Methoden werden durch die InvokeMethod-Funktion aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d6e7e-117">Methods exposed by WMI management objects are called through the InvokeMethod function.</span></span> <span data-ttu-id="d6e7e-118">Weitere Informationen finden Sie in "Ausführen von Methoden für Verwaltungsobjekte" in der [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework WMI-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="d6e7e-118">For more information, please see "Executing Methods on Management Objects" in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework WMI documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6e7e-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d6e7e-119">Requirements</span></span>  
 <span data-ttu-id="d6e7e-120">**Namespace:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6e7e-120">**Namespace:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6e7e-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d6e7e-121">See Also</span></span>  
 [<span data-ttu-id="d6e7e-122">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="d6e7e-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
