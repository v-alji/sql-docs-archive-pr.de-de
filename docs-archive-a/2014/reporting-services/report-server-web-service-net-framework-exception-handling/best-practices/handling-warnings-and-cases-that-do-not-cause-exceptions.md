---
title: Behandeln von Warnungen und Fällen, die keine Ausnahmen verursachen | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], warnings that don't cause
- warnings [Reporting Services]
ms.assetid: 475c0713-6265-44e7-9ebc-ebdd1b89e0af
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 88d3daf63cf5f04975a2941d0634f357ce81456c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717380"
---
# <a name="handling-warnings-and-cases-that-do-not-cause-exceptions"></a><span data-ttu-id="68b97-102">Behandeln von Warnungen und Fällen, die keine Ausnahmen verursachen</span><span class="sxs-lookup"><span data-stu-id="68b97-102">Handling Warnings and Cases That Do Not Cause Exceptions</span></span>
  [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] <span data-ttu-id="68b97-103">löst keine Ausnahmen für Warnungen und bestimmte Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="68b97-103">does not throw exceptions for warnings and certain errors.</span></span> <span data-ttu-id="68b97-104">Wenn Sie z. B. die Methode <xref:ReportService2010.ReportingService2010.CreateCatalogItem%2A> verwenden, um einen neuen Bericht auf dem Berichtsserver zu veröffentlichen, werden alle auftretenden Warnungen als Array der <xref:ReportService2010.Warning>-Objekte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="68b97-104">For example, when you use the <xref:ReportService2010.ReportingService2010.CreateCatalogItem%2A> method to publish a new report to a report server, any warnings that occur are returned as an array of <xref:ReportService2010.Warning> objects.</span></span> <span data-ttu-id="68b97-105">Diese Warnungen sollten so behandelt und angezeigt werden, dass eine entsprechende Maßnahme getroffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="68b97-105">These warnings should be handled and displayed so that appropriate action can be taken.</span></span>  
  
```vb  
Try  
   rs.CreateCatalogItem(name, parentFolder, False, definition, Nothing, warnings)  
  
   If Not (warnings.Length = 0) Then  
      Dim warning As Warning  
      For Each warning In warnings  
         Console.WriteLine(warning.Message)  
      Next warning  
   Else  
      Console.WriteLine("Report {0} created successfully with no warnings", name)  
   End If  
  
Catch ex As SoapException  
   Console.WriteLine(ex.Detail("Message").InnerXml)  
End Try  
```  
  
```csharp  
try  
{  
   rs.CreateCatalogItem("Report", name, parentFolder, false, definition, null, out warnings);  
  
   if (warnings.Length != 0)  
   {  
      foreach (Warning warning in warnings)  
      {  
         Console.WriteLine(warning.Message);  
      }  
   }  
   else  
      Console.WriteLine("Report {0} created successfully with no warnings", name);  
}  
  
catch (SoapException ex)  
{  
   Console.WriteLine(ex.Detail["Message"].InnerXml);  
}  
```  
  
 <span data-ttu-id="68b97-106">Eine andere Möglichkeit der Fehlerbehandlung liegt in der Auswertung der Rückgabewerte bestimmter Methoden.</span><span class="sxs-lookup"><span data-stu-id="68b97-106">Another way to handle errors is to evaluate the return values of certain methods.</span></span> <span data-ttu-id="68b97-107">Beispiel: Mithilfe der Methode <xref:ReportService2010.ReportingService2010.FindItems%2A> können bestimmte Elemente in der Berichtsserver-Datenbank gesucht werden.</span><span class="sxs-lookup"><span data-stu-id="68b97-107">For example, the <xref:ReportService2010.ReportingService2010.FindItems%2A> method can be used to search for specific items in the report server database.</span></span> <span data-ttu-id="68b97-108">Wenn keine Elemente gefunden werden, die den Suchkriterien entsprechen, wird ein NULL-Array von <xref:ReportService2010.CatalogItem>-Objekten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="68b97-108">If no items are found that match the search criteria, a null array of <xref:ReportService2010.CatalogItem> objects is returned.</span></span> <span data-ttu-id="68b97-109">Sie sollten dieses Array auswerten, nach `null` suchen und den Benutzer wissen lassen, dass keine Elemente gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="68b97-109">You should evaluate the array, check for `null`, and let the user know if no items were found.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68b97-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="68b97-110">See Also</span></span>  
 <xref:ReportService2010.CatalogItem>   
 <span data-ttu-id="68b97-111">[Einführung in die Ausnahmebehandlung in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="68b97-111">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="68b97-112">Reporting Services-SoapException-Klasse</span><span class="sxs-lookup"><span data-stu-id="68b97-112">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
