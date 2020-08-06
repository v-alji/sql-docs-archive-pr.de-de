---
title: Verwenden der Detail-Eigenschaft zur Handhabung bestimmter Fehler | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], Detail property
- Detail property
- InnerText property
ms.assetid: 4392633d-b46b-41e6-bc12-efb64e166704
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4f8ac62dc381d8f665a44fc0897ba1f4215aa8e5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719537"
---
# <a name="using-the-detail-property-to-handle-specific-errors"></a><span data-ttu-id="f9a13-102">Verwenden der Detail-Eigenschaft zur Handhabung bestimmter Fehler</span><span class="sxs-lookup"><span data-stu-id="f9a13-102">Using the Detail Property to Handle Specific Errors</span></span>
  <span data-ttu-id="f9a13-103">Zur weiteren Klassifizierung von Ausnahmen gibt [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] zusätzliche Fehlerinformationen in der **InnerText**-Eigenschaft der untergeordneten Elemente in der **Detail**-Eigenschaft der SOAP-Ausnahme zurück.</span><span class="sxs-lookup"><span data-stu-id="f9a13-103">To further classify exceptions, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] returns additional error information in the **InnerText** property of the child elements in the SOAP exception's **Detail** property.</span></span> <span data-ttu-id="f9a13-104">Da die **Detail**-Eigenschaft ein **XmlNode**-Objekt ist, können Sie mit folgendem Code auf den inneren Text des untergeordneten **Message**-Elements zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f9a13-104">Because the **Detail** property is an **XmlNode** object, you can access the inner text of the **Message** child element using the following code.</span></span>  
  
 <span data-ttu-id="f9a13-105">Eine Liste aller verfügbaren untergeordneten Elemente, die in der **Detail**-Eigenschaft enthalten sind, finden Sie unter [Detail-Eigenschaft](../soapexception-class/detail-property.md).</span><span class="sxs-lookup"><span data-stu-id="f9a13-105">For a list of all of the available child elements contained in the **Detail** property, see [Detail Property](../soapexception-class/detail-property.md).</span></span> <span data-ttu-id="f9a13-106">Weitere Informationen finden Sie unter "Detail Eigenschaft" in der [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="f9a13-106">For more information, see "Detail Property" in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] SDK documentation.</span></span>  
  
```vb  
Try  
' Code for accessing the report server  
Catch ex As SoapException  
   ' The exception is a SOAP exception, so use  
   ' the Detail property's Message element.  
   Console.WriteLine(ex.Detail("Message").InnerXml)  
End Try  
```  
  
```csharp  
try  
{  
   // Code for accessing the report server  
}  
catch (SoapException ex)  
{  
   // The exception is a SOAP exception, so use  
   // the Detail property's Message element.  
   Console.WriteLine(ex.Detail["Message"].InnerXml);  
}  
```  
  
```vb  
Try  
' Code for accessing the report server  
Catch ex As SoapException  
   If ex.Detail("ErrorCode").InnerXml = "rsInvalidItemName" Then  
   End If ' Perform an action based on the specific error code  
End Try  
```  
  
```csharp  
try  
{  
   // Code for accessing the report server  
}  
catch (SoapException ex)  
{  
   if (ex.Detail["ErrorCode"].InnerXml == "rsInvalidItemName")  
   {  
      // Perform an action based on the specific error code  
   }  
}  
```  
  
 <span data-ttu-id="f9a13-107">Folgende Codezeile gibt den spezifischen Fehlercode wieder, der in der SOAP-Ausnahme zur Konsole zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f9a13-107">The following line of code writes the specific error code being returned in the SOAP Exception to the console.</span></span> <span data-ttu-id="f9a13-108">Sie können den Fehlercode auch auswerten und bestimmte Aktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="f9a13-108">You could also evaluate the error code and perform specific actions.</span></span>  
  
```vb  
Console.WriteLine(ex.Detail("ErrorCode").InnerXml)  
```  
  
```csharp  
Console.WriteLine(ex.Detail["ErrorCode"].InnerXml);  
```  
  
## <a name="see-also"></a><span data-ttu-id="f9a13-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f9a13-109">See Also</span></span>  
 <span data-ttu-id="f9a13-110">[Einführung in die Ausnahmebehandlung in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="f9a13-110">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 <span data-ttu-id="f9a13-111">[Reporting Services SoapException-Klasse](../soapexception-class/reporting-services-soapexception-class.md) </span><span class="sxs-lookup"><span data-stu-id="f9a13-111">[Reporting Services SoapException Class](../soapexception-class/reporting-services-soapexception-class.md) </span></span>  
 [<span data-ttu-id="f9a13-112">Tabelle für SoapException-Fehler</span><span class="sxs-lookup"><span data-stu-id="f9a13-112">SoapException Errors Table</span></span>](../soapexception-class/soapexception-errors-table.md)  
  
  
