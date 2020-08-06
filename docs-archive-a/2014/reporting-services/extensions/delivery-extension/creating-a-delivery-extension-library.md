---
title: Erstellen einer Bibliothek für Übermittlungserweiterungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery extensions [Reporting Services], namespace assignments
- library [Reporting Services]
- assigning namespaces to extensions
ms.assetid: 63b32f93-4bab-4b07-bd72-39a47aca1cda
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c9891c2b0c1bb9c7d495b3ab1f8f2267ce04b79f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725250"
---
# <a name="creating-a-delivery-extension-library"></a><span data-ttu-id="4c04b-102">Erstellen einer Bibliothek für Übermittlungserweiterungen</span><span class="sxs-lookup"><span data-stu-id="4c04b-102">Creating a Delivery Extension Library</span></span>
  <span data-ttu-id="4c04b-103">Jede von Ihnen erstellte [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Übermittlungserweiterung sollte einen eindeutigen Namespace erhalten und in eine Bibliothek oder Assemblydatei integriert werden.</span><span class="sxs-lookup"><span data-stu-id="4c04b-103">Each [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension you create should be assigned to a unique namespace and built into a library or assembly file.</span></span> <span data-ttu-id="4c04b-104">Der exakte Name des Namespace ist unerheblich, er muss jedoch eindeutig sein und darf nicht zusammen mit einer anderen Erweiterung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4c04b-104">The exact name of the namespace is not important, but it must be unique and not shared with any other extension.</span></span> <span data-ttu-id="4c04b-105">Sie sollten eigene eindeutige Namespaces für die Übermittlungserweiterungen Ihres Unternehmens erstellen.</span><span class="sxs-lookup"><span data-stu-id="4c04b-105">You should create your own unique namespaces for your company's delivery extensions.</span></span>  
  
 <span data-ttu-id="4c04b-106">Folgendes Beispiel zeigt den Code, mit dem Sie eine [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Übermittlungserweiterung beginnen sollten. Der Code verwendet die Namespaces, welche die Übermittlungsschnittstellen und jegliche Hilfsprogrammklassen enthalten.</span><span class="sxs-lookup"><span data-stu-id="4c04b-106">The following example shows the code to begin a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, which uses the namespaces that contain the delivery interfaces and any utility classes.</span></span>  
  
```vb  
Imports System  
Imports Microsoft.ReportingServices.Interfaces  
  
Namespace CompanyName.ExtensionName  
   ...  
```  
  
```csharp  
using System;  
using Microsoft.ReportingServices.Interfaces;  
  
namespace CompanyName.ExtensionName  
{  
   ...  
```  
  
 <span data-ttu-id="4c04b-107">Wenn Sie eine [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Übermittlungserweiterung kompilieren, müssen Sie für den Compiler einen Verweis auf Microsoft.ReportingServices.Interfaces.dll angeben, da sich die Schnittstellen der Übermittlungserweiterungen und -klassen dort befinden.</span><span class="sxs-lookup"><span data-stu-id="4c04b-107">When compiling a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, you must supply to the compiler a reference to Microsoft.ReportingServices.Interfaces.dll, because the delivery extension interfaces and classes are contained there.</span></span> <span data-ttu-id="4c04b-108">Der <xref:Microsoft.ReportingServices.Interfaces>-Namespace wird benötigt, um die <xref:Microsoft.ReportingServices.Interfaces.IExtension>-Schnittstelle, die <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension>-Schnittstelle und mehr zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="4c04b-108">The <xref:Microsoft.ReportingServices.Interfaces> namespace is needed to implement the <xref:Microsoft.ReportingServices.Interfaces.IExtension> interface, the <xref:Microsoft.ReportingServices.Interfaces.IDeliveryExtension> interface, and more.</span></span> <span data-ttu-id="4c04b-109">Beispiel: Wenn sich alle Dateien, die den Code für die Implementierung einer in C# geschriebenen [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Übermittlungserweiterung enthalten, in einem Verzeichnis mit der Erweiterung .cs befinden, würde folgender Befehl von diesem Verzeichnis ausgegeben, um die in „CompanyName.ExtensionName.dll“ gespeicherten Dateien zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="4c04b-109">For example, if all the files containing the code to implement a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension written in C# were in a single directory with the extension .cs, the following command would be issued from that directory to compile the files stored in CompanyName.ExtensionName.dll.</span></span>  
  
```csharp  
csc /t:library /out:CompanyName.ExtensionName.dll *.cs /r:System.dll   
/r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
 <span data-ttu-id="4c04b-110">Im folgenden Codebeispiel wird der Befehl angezeigt, der für [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]-Dateien mit der Erweiterung „.vb“ verwendet werden würde.</span><span class="sxs-lookup"><span data-stu-id="4c04b-110">The following code example shows the command that would be used for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] files with the extension .vb.</span></span>  
  
```vb  
vbc /t:library /out:CompanyName.ExtensionName.dll *.vb /r:System.dll   
/r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
> [!NOTE]  
>  <span data-ttu-id="4c04b-111">Sie können die Übermittlungserweiterung auch mit [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] entwerfen, entwickeln und erstellen.</span><span class="sxs-lookup"><span data-stu-id="4c04b-111">You can also design, develop, and build your delivery extension using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="4c04b-112">Weitere Informationen zum Entwickeln von Assemblys in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] finden Sie in der Dokumentation zu [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c04b-112">For more information about developing assemblies in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c04b-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4c04b-113">See Also</span></span>  
 <span data-ttu-id="4c04b-114">[Erweiterungen für Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="4c04b-114">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="4c04b-115">[Implementieren von Übermittlungserweiterungen](implementing-a-delivery-extension.md) </span><span class="sxs-lookup"><span data-stu-id="4c04b-115">[Implementing a Delivery Extension](implementing-a-delivery-extension.md) </span></span>  
 [<span data-ttu-id="4c04b-116">Reporting Services Extension Library (Reporting Services-Erweiterungsbibliothek)</span><span class="sxs-lookup"><span data-stu-id="4c04b-116">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
