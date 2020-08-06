---
title: Bewährte Methoden für die Ausnahmebehandlung in Reporting Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- exceptions [Reporting Services], best practices
ms.assetid: 72fecf28-f02e-4338-b50f-0b21f520302d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e0561c19fbd3e709a0440a55f023f938eabf692
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616935"
---
# <a name="best-practices-for-reporting-services-exception-handling"></a><span data-ttu-id="e58b3-102">Bewährte Methoden für die Ausnahmebehandlung in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="e58b3-102">Best Practices for Reporting Services Exception Handling</span></span>
  <span data-ttu-id="e58b3-103">Wenn Sie [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Anwendungen entwickeln, können Sie verschiedene Methoden verwenden, um das Auftreten von Ausnahmezuständen zu verhindern oder zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="e58b3-103">When developing [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] applications, there are several methodologies you can use to eliminate or reduce the occurrence of exceptions.</span></span> <span data-ttu-id="e58b3-104">Wenn Ausnahmen auftreten, sorgen Sie für klare und prägnante Fehlermeldungen, und fügen Sie eine adäquate Behandlung der Ausnahme hinzu, um unerwartete Abbrüche Ihrer Anwendungen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="e58b3-104">When exceptions do occur, provide clear and concise error messages to the user, and add adequate exception handling to prevent your applications from ending unexpectedly.</span></span>  
  
 <span data-ttu-id="e58b3-105">Eine Anwendung, die Anforderungen an den Berichtsserver-Webdienst sendet, sollte wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="e58b3-105">An application that sends requests to the Report Server Web service should do the following:</span></span>  
  
-   <span data-ttu-id="e58b3-106">Keine Ausnahmen verursachen, indem möglichst viele ungültige Anforderungen verhindert werden.</span><span class="sxs-lookup"><span data-stu-id="e58b3-106">Avoid causing exceptions by preventing as many invalid requests as possible.</span></span>  
  
-   <span data-ttu-id="e58b3-107">Abfangen von Ausnahmen und Angabe eines spezifischen Fehlerbehandlungscodes, wenn möglich.</span><span class="sxs-lookup"><span data-stu-id="e58b3-107">Catch exceptions and provide specific error-handling code whenever possible.</span></span>  
  
-   <span data-ttu-id="e58b3-108">Behandlung von Fehlerfällen, die keine Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="e58b3-108">Deal with error cases that do not throw exceptions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e58b3-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e58b3-109">In This Section</span></span>  
  
|<span data-ttu-id="e58b3-110">Thema</span><span class="sxs-lookup"><span data-stu-id="e58b3-110">Topic</span></span>|<span data-ttu-id="e58b3-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e58b3-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="e58b3-112">Verhindern von ungültigen Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e58b3-112">Preventing Invalid Requests</span></span>](preventing-invalid-requests.md)|<span data-ttu-id="e58b3-113">Beschreibt Techniken, mit denen verhindert wird, dass ungültige Anforderungen zum Berichtsserver gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="e58b3-113">Describes techniques for preventing requests that are not valid from being sent to the report server.</span></span>|  
|[<span data-ttu-id="e58b3-114">Verwenden von „Try und Catch“-Blöcken</span><span class="sxs-lookup"><span data-stu-id="e58b3-114">Using Try and Catch Blocks</span></span>](using-try-and-catch-blocks.md)|<span data-ttu-id="e58b3-115">Beschreibt, wie die Zuverlässigkeit Ihrer Anwendung mithilfe von try/catch-Blöcken weiter verbessert wird.</span><span class="sxs-lookup"><span data-stu-id="e58b3-115">Describes how to further enhance the reliability of your application with try/catch blocks.</span></span>|  
|[<span data-ttu-id="e58b3-116">Behandeln von Warnungen und Fällen, die keine Ausnahmen verursachen</span><span class="sxs-lookup"><span data-stu-id="e58b3-116">Handling Warnings and Cases That Do Not Cause Exceptions</span></span>](handling-warnings-and-cases-that-do-not-cause-exceptions.md)|<span data-ttu-id="e58b3-117">Erklärt, wie Fehler behandelt werden, die nicht zu einer Ausnahme führen, die von [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="e58b3-117">Explains how to handle errors that do not result in an exception being thrown by [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>|  
|[<span data-ttu-id="e58b3-118">Verwenden der Detail-Eigenschaft zur Handhabung bestimmter Fehler</span><span class="sxs-lookup"><span data-stu-id="e58b3-118">Using the Detail Property to Handle Specific Errors</span></span>](using-the-detail-property-to-handle-specific-errors.md)|<span data-ttu-id="e58b3-119">Erklärt, wie bestimmte Fehler programmgesteuert mit der **Detail**-Eigenschaft des **SoapException**-Objekts behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="e58b3-119">Explains how to programmatically handle specific errors by using the **Detail** property of the **SoapException** object.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e58b3-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e58b3-120">See Also</span></span>  
 <span data-ttu-id="e58b3-121">[Detail Eigenschaft](../soapexception-class/detail-property.md) </span><span class="sxs-lookup"><span data-stu-id="e58b3-121">[Detail Property](../soapexception-class/detail-property.md) </span></span>  
 <span data-ttu-id="e58b3-122">[Einführung in die Ausnahmebehandlung in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="e58b3-122">[Introducing Exception Handling in Reporting Services](../introducing-exception-handling-in-reporting-services.md) </span></span>  
 [<span data-ttu-id="e58b3-123">Reporting Services-SoapException-Klasse</span><span class="sxs-lookup"><span data-stu-id="e58b3-123">Reporting Services SoapException Class</span></span>](../soapexception-class/reporting-services-soapexception-class.md)  
  
  
