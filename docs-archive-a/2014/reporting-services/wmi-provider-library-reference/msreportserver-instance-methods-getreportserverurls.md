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
# <a name="getreportserverurls-method-wmi-msreportserver_instance"></a>GetReportServerUrls-Methode (WMI: MSReportServer_Instance)
  Gibt eine Liste von URLs zurück, über die Benutzer auf den Berichtsserver und den Berichts-Manager zugreifen können  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Public Sub GetReportServerUrls (ByRef ApplicationName() As String, ByRef URLs()_  
    As String, ByRef Length As Int32, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GetReportServerUrls(out string[] applicationName,   
    out string[] URLs, out int length, out int HRESULT);  
```  
  
## <a name="parameters"></a>Parameter  
 *ApplicationName[]*  
 Ein Array, das die installierten Anwendungen enthält. Werte sind entweder `ReportServerWebService` oder `ReportManager`.  
  
 *URLs[]*  
 Ein Array, das die erfolgreich registrierten URLs enthält  
  
 *Länge*  
 Ein Integer-Wert, der die Länge der zurückgegebenen Arrays enthält.  
  
 *HRESULT*  
 Ein Wert, der Erfolg oder einen Fehlercode angibt  
  
## <a name="return-values"></a>Rückgabewerte  
  
## <a name="remarks"></a>Bemerkungen  
 Von WMI-Verwaltungsobjekten verfügbar gemachte Methoden werden durch die InvokeMethod-Funktion aufgerufen. Weitere Informationen finden Sie in "Ausführen von Methoden für Verwaltungsobjekte" in der [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework WMI-Dokumentation.  
  
## <a name="requirements"></a>Requirements (Anforderungen)  
 **Namespace:** [!INCLUDE[ssRSWMInmspc](../../includes/ssrswminmspc-md.md)]  
  
## <a name="see-also"></a>Weitere Informationen  
 [MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)](msreportserver-configurationsetting-members.md)  
  
  
