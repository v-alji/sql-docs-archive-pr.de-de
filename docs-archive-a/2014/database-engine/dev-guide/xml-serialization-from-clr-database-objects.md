---
title: XML-Serialisierung von CLR-Datenbankobjekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- serialization
- XML serialization [CLR integration]
- common language runtime [SQL Server], XML serialization
- XmlSerializer class
ms.assetid: ac84339b-9384-4710-bebc-01607864a344
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: ee93ee4b7bf9cba3f11b329244d4523636cb7704
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701649"
---
# <a name="xml-serialization-from-clr-database-objects"></a><span data-ttu-id="c6fc8-102">XML-Serialisierung auf Grundlage von CLR-Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="c6fc8-102">XML Serialization from CLR Database Objects</span></span>
  <span data-ttu-id="c6fc8-103">Die XML-Serialisierung ist in zwei Szenarien erforderlich:</span><span class="sxs-lookup"><span data-stu-id="c6fc8-103">XML serialization is required for two scenarios:</span></span>  
  
-   <span data-ttu-id="c6fc8-104">Aufrufen von Webdiensten aus CLR-Objekten (Common Language Runtime)</span><span class="sxs-lookup"><span data-stu-id="c6fc8-104">Invoking Web Services from common language runtime (CLR) objects.</span></span>  
  
-   <span data-ttu-id="c6fc8-105">Konvertieren eines benutzerdefinierten Typs (UDT) in XML</span><span class="sxs-lookup"><span data-stu-id="c6fc8-105">Converting a user-defined type (UDT) to XML.</span></span>  
  
 <span data-ttu-id="c6fc8-106">Wenn durch Aufrufen der `XmlSerializer`-Klasse eine XML-Serialisierung durchgeführt wird, wird in der Regel eine zusätzliche Serialisierungsassembly erstellt, die in das Projekt mit der Quellassembly überladen wird.</span><span class="sxs-lookup"><span data-stu-id="c6fc8-106">Performing XML serialization by invoking the `XmlSerializer` class normally generates an additional serialization assembly that is overloaded into the project with the source assembly.</span></span> <span data-ttu-id="c6fc8-107">Aus Sicherheitsgründen wird diese Überladung jedoch in der CLR deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="c6fc8-107">However, for security purposes, this overload is disabled in the CLR.</span></span> <span data-ttu-id="c6fc8-108">Um daher einen Webdienst aufzurufen oder eine Konvertierung von UDT in XML in auszuführen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , muss die Assembly manuell mithilfe eines Tools **Sgen.exe** namens erstellt werden, das mit dem .NET Framework bereitgestellt wird, der die erforderlichen Serialisierungsassemblys generiert.</span><span class="sxs-lookup"><span data-stu-id="c6fc8-108">Therefore, to call a web service or perform conversion from UDT to XML inside [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the assembly must be created manually using a tool called **Sgen.exe** provided with the .NET Framework that generates the necessary serialization assemblies.</span></span> <span data-ttu-id="c6fc8-109">Beim Aufrufen von `XmlSerializer` muss die Serialisierungsassembly wie folgt manuell erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="c6fc8-109">When invoking `XmlSerializer`, the serialization assembly must be created manually by following these steps:</span></span>  
  
1.  <span data-ttu-id="c6fc8-110">Führen Sie das **Sgen.exe** Tool aus, das mit dem .NET Framework SDK bereitgestellt wird, um die Assembly zu erstellen, die die XML-Serialisierer für die Quellassembly enthält.</span><span class="sxs-lookup"><span data-stu-id="c6fc8-110">Run the **Sgen.exe** tool that is provided with the .NET Framework SDK to create the assembly containing the XML serializers for the source assembly.</span></span>  
  
2.  <span data-ttu-id="c6fc8-111">Registrieren Sie die generierte Assembly mithilfe der `CREATE ASSEMBLY`-Anweisung in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6fc8-111">Register the generated assembly in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using the `CREATE ASSEMBLY` statement.</span></span>  
  
 <span data-ttu-id="c6fc8-112">Informationen zu Fehlern, die beim Ausführen der XML-Serialisierung auftreten können, finden Sie im folgenden Microsoft-Support Artikel: ["kann dynamisch generierte Serialisierungsassembly nicht laden"](https://support.microsoft.com/kb/913668).</span><span class="sxs-lookup"><span data-stu-id="c6fc8-112">For information about errors that you may receive when performing XML serialization, see the following Microsoft Support article: ["Cannot load dynamically generated serialization assembly"](https://support.microsoft.com/kb/913668).</span></span>  
  
 <span data-ttu-id="c6fc8-113">Informationen über Datentypen, die vom XML-Serialisierungsprogramm nicht unterstützt werden, finden Sie in der Dokumentation zu .NET Framework unter "Bindungsunterstützung für XML-Schema in .NET Framework".</span><span class="sxs-lookup"><span data-stu-id="c6fc8-113">For information on data types that are not supported by XMLSerializer, see XML Schema Binding Support in the .NET Framework in the .NET Framework documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6fc8-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6fc8-114">See Also</span></span>  
 <span data-ttu-id="c6fc8-115">[Datenzugriff von CLR-Datenbankobjekten](../../relational-databases/clr-integration/data-access/data-access-from-clr-database-objects.md) </span><span class="sxs-lookup"><span data-stu-id="c6fc8-115">[Data Access from CLR Database Objects](../../relational-databases/clr-integration/data-access/data-access-from-clr-database-objects.md) </span></span>  
 [<span data-ttu-id="c6fc8-116">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="c6fc8-116">CREATE ASSEMBLY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-assembly-transact-sql)  
  
  
