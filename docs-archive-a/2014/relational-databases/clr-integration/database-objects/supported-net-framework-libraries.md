---
title: Unterstützte .NET Framework Bibliotheken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- common language runtime [SQL Server], .NET Framework libraries
- .NET Framework [CLR Integration]
ms.assetid: 417544ff-c25c-496e-add4-2f278f8a4911
author: rothja
ms.author: jroth
ms.openlocfilehash: 22f92e3eadccc869452cf35534f786724c8e259a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607831"
---
# <a name="supported-net-framework-libraries"></a><span data-ttu-id="9009f-102">Unterstützte .NET Framework-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="9009f-102">Supported .NET Framework Libraries</span></span>
  <span data-ttu-id="9009f-103">Mit in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] gehosteter CLR (Common Language Runtime) können Sie gespeicherte Prozeduren, Trigger, benutzerdefinierte Funktionen, benutzerdefinierte Typen (User-Defined Types, UDT) und benutzerdefinierte Aggregate in verwaltetem Code erstellen.</span><span class="sxs-lookup"><span data-stu-id="9009f-103">With the common language runtime (CLR) hosted in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="9009f-104">Mit den in den Bibliotheken der .NET Framework-Klasse verfügbaren Funktionen haben Sie Zugriff auf vorgefertigte Klassen, die Funktionen u. a. zur Zeichenfolgenbearbeitung, für erweiterte mathematische Vorgänge, den Dateizugriff und die Kryptografie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="9009f-104">With the functionality found in the .NET Framework class libraries, you have access to pre-built classes that provide functionality for string manipulation, advanced math operations, file access, cryptography, and more.</span></span> <span data-ttu-id="9009f-105">Auf diese Klassen können Sie von jeder verwalteten gespeicherten Prozedur, jedem benutzerdefinierten Typ, jedem Trigger, jeder benutzerdefinierten Funktion oder jedem benutzerdefinierten Aggregat aus zugreifen.</span><span class="sxs-lookup"><span data-stu-id="9009f-105">These classes can be accessed from any managed stored procedure, user-defined type, trigger, user-defined function, or user-defined aggregate.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9009f-106">Wenn Sie nicht unterstützte Assemblys im globalen Assemblycache (Global Assembly Cache, GAC) Dienst oder aktualisieren, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] können Sie</span><span class="sxs-lookup"><span data-stu-id="9009f-106">If you service or upgrade unsupported assemblies in the global assembly cache (GAC), your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9009f-107">Wenn eine Assembly in einer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] CLR-Integration vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9009f-107">If an assembly exists both in a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] CLR integration.</span></span> <span data-ttu-id="9009f-108">Wenn Sie im GAC Assemblys warten oder aktualisieren, die auch in der Datenbank registriert sind, müssen Sie auch die Kopie der Assembly in den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Datenbanken mit der `ALTER ASSEMBLY`-Anweisung warten oder aktualisieren. Dies gilt auch für nicht unterstützte .NET Framework-Assemblys.</span><span class="sxs-lookup"><span data-stu-id="9009f-108">If you service or upgrade any assemblies in the GAC that are also registered in the database, including unsupported .NET Framework assemblies, make sure to also service or upgrade the copy of the assembly inside your [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] databases with the `ALTER ASSEMBLY` statement.</span></span> <span data-ttu-id="9009f-109">Weitere Informationen finden Sie im [Knowledge Base-Artikel 949080](https://support.microsoft.com/kb/949080).</span><span class="sxs-lookup"><span data-stu-id="9009f-109">For more information, see [Knowledge Base article 949080](https://support.microsoft.com/kb/949080).</span></span>  
  
## <a name="supported-libraries"></a><span data-ttu-id="9009f-110">Unterstützte Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="9009f-110">Supported Libraries</span></span>  
 <span data-ttu-id="9009f-111">Ab [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] verfügt über eine Liste der unterstützten .NET Framework-Bibliotheken, die getestet wurden, um sicherzustellen, dass Sie die Zuverlässigkeits-und Sicherheitsstandards für die Interaktion mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] der direkten Auslastung aus dem globalen Assemblycache (GAC) erfüllen.</span><span class="sxs-lookup"><span data-stu-id="9009f-111">Beginning with [!INCLUDE[ssVersion2005](../../../includes/ssnoversion-md.md)] has a list of supported .NET Framework libraries, which have been tested to ensure that they meet reliability and security standards for interaction with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] loads them directly from the Global Assembly Cache (GAC).</span></span>  
  
 <span data-ttu-id="9009f-112">Folgende Bibliotheken/Namespaces werden von der CLR-Integration in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] unterstützt:</span><span class="sxs-lookup"><span data-stu-id="9009f-112">The libraries/namespaces supported by CLR integration in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] are:</span></span>  
  
-   <span data-ttu-id="9009f-113">CustomMarshalers</span><span class="sxs-lookup"><span data-stu-id="9009f-113">CustomMarshalers</span></span>  
  
-   <span data-ttu-id="9009f-114">Microsoft.VisualBasic</span><span class="sxs-lookup"><span data-stu-id="9009f-114">Microsoft.VisualBasic</span></span>  
  
-   <span data-ttu-id="9009f-115">Microsoft.VisualC</span><span class="sxs-lookup"><span data-stu-id="9009f-115">Microsoft.VisualC</span></span>  
  
-   <span data-ttu-id="9009f-116">mscorlib</span><span class="sxs-lookup"><span data-stu-id="9009f-116">mscorlib</span></span>  
  
-   <span data-ttu-id="9009f-117">System</span><span class="sxs-lookup"><span data-stu-id="9009f-117">System</span></span>  
  
-   <span data-ttu-id="9009f-118">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="9009f-118">System.Configuration</span></span>  
  
-   <span data-ttu-id="9009f-119"><legacyBold>System.Data</legacyBold></span><span class="sxs-lookup"><span data-stu-id="9009f-119">System.Data</span></span>  
  
-   <span data-ttu-id="9009f-120">System.Data.OracleClient</span><span class="sxs-lookup"><span data-stu-id="9009f-120">System.Data.OracleClient</span></span>  
  
-   <span data-ttu-id="9009f-121">System.Data.SqlXml</span><span class="sxs-lookup"><span data-stu-id="9009f-121">System.Data.SqlXml</span></span>  
  
-   <span data-ttu-id="9009f-122">System.Deployment</span><span class="sxs-lookup"><span data-stu-id="9009f-122">System.Deployment</span></span>  
  
-   <span data-ttu-id="9009f-123">System.Security</span><span class="sxs-lookup"><span data-stu-id="9009f-123">System.Security</span></span>  
  
-   <span data-ttu-id="9009f-124">System.Transactions</span><span class="sxs-lookup"><span data-stu-id="9009f-124">System.Transactions</span></span>  
  
-   <span data-ttu-id="9009f-125">System.Web.Services</span><span class="sxs-lookup"><span data-stu-id="9009f-125">System.Web.Services</span></span>  
  
-   <span data-ttu-id="9009f-126">System.Xml</span><span class="sxs-lookup"><span data-stu-id="9009f-126">System.Xml</span></span>  
  
-   <span data-ttu-id="9009f-127">System.Core.dll</span><span class="sxs-lookup"><span data-stu-id="9009f-127">System.Core.dll</span></span>  
  
-   <span data-ttu-id="9009f-128">System.Xml.Linq.dll</span><span class="sxs-lookup"><span data-stu-id="9009f-128">System.Xml.Linq.dll</span></span>  
  
## <a name="unsupported-libraries"></a><span data-ttu-id="9009f-129">Nicht unterstützte Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="9009f-129">Unsupported Libraries</span></span>  
 <span data-ttu-id="9009f-130">Nicht unterstützte Bibliotheken können Sie nach wie vor von Ihren verwalteten gespeicherten Prozeduren, Triggern, benutzerdefinierten Funktionen, benutzerdefinierten Typen (User-Defined Types, UDT) und benutzerdefinierten Aggregaten aus aufrufen.</span><span class="sxs-lookup"><span data-stu-id="9009f-130">Unsupported libraries can still be called from your managed stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates.</span></span> <span data-ttu-id="9009f-131">Die nicht unterstützten Bibliotheken müssen zunächst in der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Datenbank mit der `CREATE ASSEMBLY`-Anweisung registriert werden, bevor sie in Ihrem Code verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="9009f-131">The unsupported library must first be registered in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] database, using the `CREATE ASSEMBLY` statement, before it can be used in your code.</span></span> <span data-ttu-id="9009f-132">Alle nicht unterstützten Bibliotheken, die registriert und auf dem Server ausgeführt werden, sollten überprüft und auf Sicherheit und Zuverlässigkeit getestet werden.</span><span class="sxs-lookup"><span data-stu-id="9009f-132">Any unsupported library that is registered and run on the server should be reviewed and tested for security and reliability.</span></span>  
  
 <span data-ttu-id="9009f-133">Der `System.DirectoryServices`-Namespace wird beispielsweise nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9009f-133">For example, the `System.DirectoryServices` namespace is not supported.</span></span> <span data-ttu-id="9009f-134">Sie müssen die System.DirectoryServices.dll-Assembly mit `UNSAFE`-Berechtigungen registrieren, bevor Sie sie vom Code aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="9009f-134">You must register the System.DirectoryServices.dll assembly with `UNSAFE` permissions before you can call it from your code.</span></span> <span data-ttu-id="9009f-135">Die `UNSAFE`-Berechtigung ist erforderlich, da Klassen im `System.DirectoryServices`-Namespace die Anforderungen für `SAFE` oder `EXTERNAL_ACCESS` nicht erfüllen.</span><span class="sxs-lookup"><span data-stu-id="9009f-135">The `UNSAFE` permission is necessary because classes in the `System.DirectoryServices` namespace do not meet the requirements for `SAFE` or `EXTERNAL_ACCESS`.</span></span> <span data-ttu-id="9009f-136">Weitere Informationen finden Sie unter [Einschränkungen für das CLR-Integrations Programmiermodell](clr-integration-programming-model-restrictions.md) und [CLR-Integration Code Zugriffssicherheit](../security/clr-integration-code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="9009f-136">For more information, see [CLR Integration Programming Model Restrictions](clr-integration-programming-model-restrictions.md) and [CLR Integration Code Access Security](../security/clr-integration-code-access-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9009f-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9009f-137">See Also</span></span>  
 <span data-ttu-id="9009f-138">[Erstellen einer Assembly](../assemblies/creating-an-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="9009f-138">[Creating an Assembly](../assemblies/creating-an-assembly.md) </span></span>  
 <span data-ttu-id="9009f-139">[Code Zugriffssicherheit für die CLR-Integration](../security/clr-integration-code-access-security.md) </span><span class="sxs-lookup"><span data-stu-id="9009f-139">[CLR Integration Code Access Security](../security/clr-integration-code-access-security.md) </span></span>  
 [<span data-ttu-id="9009f-140">Beschränkungen des Programmiermodells für die CLR-Integration</span><span class="sxs-lookup"><span data-stu-id="9009f-140">CLR Integration Programming Model Restrictions</span></span>](clr-integration-programming-model-restrictions.md)  
  
  
