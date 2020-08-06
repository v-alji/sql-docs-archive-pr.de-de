---
title: Erstellen einer Bibliothek für Datenverarbeitungserweiterungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- data processing extensions [Reporting Services], namespace assignments
- library [Reporting Services]
- assigning namespaces to extensions
ms.assetid: 82f4b71b-dd39-467d-8d8c-6771eb2b12de
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: a3c14ed699e94c7d8ed0f6f3d727e9ba6e355b7e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726710"
---
# <a name="creating-a-data-processing-extension-library"></a><span data-ttu-id="821d2-102">Erstellen einer Bibliothek für Datenverarbeitungserweiterungen</span><span class="sxs-lookup"><span data-stu-id="821d2-102">Creating a Data Processing Extension Library</span></span>
  <span data-ttu-id="821d2-103">Jede von Ihnen erstellte [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Datenverarbeitungserweiterung sollte einen eindeutigen Namespace erhalten und in eine Bibliothek oder Assemblydatei integriert werden.</span><span class="sxs-lookup"><span data-stu-id="821d2-103">Each [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension you create should be assigned to a unique namespace and built into a library or assembly file.</span></span> <span data-ttu-id="821d2-104">Der exakte Name des Namespace ist unerheblich, er muss jedoch eindeutig sein und darf nicht zusammen mit einer anderen Erweiterung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="821d2-104">The exact name of the namespace is not important, but it must be unique and not shared with any other extension.</span></span> [!INCLUDE[msCoName](../../../includes/msconame-md.md)] <span data-ttu-id="821d2-105">verwendet den Namespace <xref:Microsoft.ReportingServices.DataProcessing> für die Datenverarbeitungserweiterungen, die mit [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] geliefert werden.</span><span class="sxs-lookup"><span data-stu-id="821d2-105">uses the namespace <xref:Microsoft.ReportingServices.DataProcessing> for the data processing extensions that ship with [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span> <span data-ttu-id="821d2-106">Sie sollten eigene eindeutige Namespaces für die Datenverarbeitungserweiterungen Ihres Unternehmens erstellen.</span><span class="sxs-lookup"><span data-stu-id="821d2-106">You should create your own unique namespaces for your company's data processing extensions.</span></span>  
  
 <span data-ttu-id="821d2-107">Folgendes Beispiel zeigt den Code, mit dem Sie eine [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Datenverarbeitungserweiterung beginnen sollten, die Namespaces verwendet, welche die Datenverarbeitungsschnittstellen und jegliche Hilfsprogrammklassen enthalten.</span><span class="sxs-lookup"><span data-stu-id="821d2-107">The following example shows the code to begin a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension, which uses the namespaces that contain the data processing interfaces and any utility classes.</span></span>  
  
```vb  
Imports System  
Imports Microsoft.ReportingServices.DataProcessing  
Imports Microsoft.ReportingServices.Interfaces  
  
Namespace CompanyName.ExtensionName  
   ...  
```  
  
```csharp  
using System;  
using Microsoft.ReportingServices.DataProcessing;  
using Microsoft.ReportingServices.Interfaces;  
  
namespace CompanyName.ExtensionName  
{  
   ...  
```  
  
 <span data-ttu-id="821d2-108">Wenn Sie eine [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Datenverarbeitungserweiterung kompilieren, müssen Sie für den Compiler einen Verweis auf Microsoft.ReportingServices.Interfaces.dll angeben, da die Schnittstellen der Datenverarbeitungserweiterungen sich dort befinden.</span><span class="sxs-lookup"><span data-stu-id="821d2-108">When compiling a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension, you must supply to the compiler a reference to Microsoft.ReportingServices.Interfaces.dll, because the data processing extension interfaces are contained there.</span></span> <span data-ttu-id="821d2-109">Der <xref:Microsoft.ReportingServices.DataProcessing>-Namespace wird für die Implementierung der Datenverarbeitungsschnittstellen benötigt, und der <xref:Microsoft.ReportingServices.Interfaces>-Namespace wird für die Implementierung der <xref:Microsoft.ReportingServices.Interfaces.IExtension>-Schnittstelle benötigt.</span><span class="sxs-lookup"><span data-stu-id="821d2-109">The <xref:Microsoft.ReportingServices.DataProcessing> namespace is needed to implement the data processing extension interfaces, and the <xref:Microsoft.ReportingServices.Interfaces> namespace is needed to implement the <xref:Microsoft.ReportingServices.Interfaces.IExtension> interface.</span></span> <span data-ttu-id="821d2-110">Beispiel: Wenn alle Dateien, die den Code für die Implementierung einer in C# geschriebenen [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Datenverarbeitungserweiterung enthalten, sich in einem Verzeichnis mit der Erweiterung .cs befänden, würde folgender Befehl von diesem Verzeichnis ausgegeben, um die in CompanyName.ExtensionName.dll gespeicherten Dateien zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="821d2-110">For example, if all the files containing the code to implement a [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension written in C# were in a single directory with the extension .cs, the following command would be issued from that directory to compile the files stored in CompanyName.ExtensionName.dll.</span></span>  
  
```csharp  
csc /t:library /out:CompanyName.ExtensionName.dll *.cs /r:System.dll /r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
 <span data-ttu-id="821d2-111">Im folgenden Codebeispiel wird der Befehl angezeigt, der für [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]-Dateien mit der Erweiterung „.vb“ verwendet werden würde.</span><span class="sxs-lookup"><span data-stu-id="821d2-111">The following code example shows the command that would be used for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] files with the extension .vb.</span></span>  
  
```vb  
vbc /t:library /out:CompanyName.ExtensionName.dll *.vb /r:System.dll /r:Microsoft.ReportingServices.Interfaces.dll  
```  
  
> [!NOTE]  
>  <span data-ttu-id="821d2-112">Sie können die Datenverarbeitungserweiterung auch mit [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] entwerfen, entwickeln und erstellen.</span><span class="sxs-lookup"><span data-stu-id="821d2-112">You can also design, develop, and build your data processing extension using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="821d2-113">Weitere Informationen zum Entwickeln von Assemblys in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] finden Sie in der Dokumentation zu [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="821d2-113">For more information about developing assemblies in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], see your [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="821d2-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="821d2-114">See Also</span></span>  
 <span data-ttu-id="821d2-115">[Erweiterungen für Reporting Services](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="821d2-115">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 <span data-ttu-id="821d2-116">[Implementieren von Datenverarbeitungserweiterungen](implementing-a-data-processing-extension.md) </span><span class="sxs-lookup"><span data-stu-id="821d2-116">[Implementing a Data Processing Extension](implementing-a-data-processing-extension.md) </span></span>  
 [<span data-ttu-id="821d2-117">Reporting Services Extension Library (Reporting Services-Erweiterungsbibliothek)</span><span class="sxs-lookup"><span data-stu-id="821d2-117">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
