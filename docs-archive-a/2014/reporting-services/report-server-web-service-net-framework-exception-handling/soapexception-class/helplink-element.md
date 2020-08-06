---
title: HelpLink-Element | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- HelpLink element
- SoapException class
ms.assetid: a4489103-a874-44c2-8f75-95cb238928ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 97d87e11174ae2b628b760f707ec2b1db49f9e75
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697513"
---
# <a name="helplink-element"></a>HelpLink-Element
  Das **HelpLink** -Element der **Detail** -Eigenschaft ist eine URL-Zeichenfolge, die vom Berichtsserver generiert wird. Die URL steuert eine Webseite an, die von [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Hilfe und Support verwaltet wird. Sie liefert zusätzliche Hilfestellungen und Artikel der Kowledge Base zu bestimmten Fehlern, die in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]auftreten. Die URL hat folgende Syntax:  
  
 **http://** www.Microsoft.com **/** Products **/** EE **/** Transform. aspx **? Evzrc**- = _Wert_ **&EvtID**-Wert = _value_ **&ProdName**-Wert = _value_ **&PRODVER** = _value_ -Wert  
  
 In der folgenden Tabelle sind die Argumente der **HelpLink** -URL aufgeführt.  
  
|Argument|Wert|  
|--------------|-----------|  
|**EvtSrc**|"Microsoft.ReportingServices.Diagnostics.ErrorStrings.resources.Strings"|  
|**EvtID**|Der Fehlercode für den Berichtsserver, z. B. rsReservedItem.|  
|**ProdName**|"Microsoft SQL%20Server%20Reporting%20Services". Der Wert des Produktnamens ist URL-codiert.|  
|**ProdVer**|Die Versionsnummer von [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]. Der Wert "8,00" zeigt an [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] .|  
  
 Im folgenden Beispiel wird die **HelpLink** -URL veranschaulicht, die für den Fehlercode zurückgegeben wird `rsReservedItem` . Dieser Fehler tritt auf, wenn ein Benutzer versucht, ein reserviertes Element in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]zu ändern oder zu löschen:  
  
```  
https://www.microsoft.com/products/ee/transform.aspx?  
EvtSrc=Microsoft.ReportingServices.Diagnostics.ErrorStrings.resources.Strings  
&EvtID=rsReservedItem&ProdName=Microsoft%20SQL%20Server%20Reporting%20Services&ProdVer=8.00  
```  
  
 Sie können auf das **HelpLink** -Element im Code zugreifen, indem Sie die **SoapException** -Klasse verwenden.  
  
```vb  
Try  
   rs.DeleteItem("/Report1")  
  
Catch e As SoapException  
   Console.WriteLine(e.Detail("HelpLink").InnerXml)  
End Try  
```  
  
```csharp  
try  
{  
   rs.DeleteItem("/Report1");  
}  
  
catch (SoapException e)  
{  
   Console.WriteLine(e.Detail["HelpLink"].InnerXml);  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen  
 [Einführung in die Ausnahmebehandlung in Reporting Services](../introducing-exception-handling-in-reporting-services.md)   
 [Reporting Services SoapException-Klasse](reporting-services-soapexception-class.md)   
 [Verwenden der Detail-Eigenschaft zur Handhabung bestimmter Fehler](../best-practices/using-the-detail-property-to-handle-specific-errors.md)  
  
  
