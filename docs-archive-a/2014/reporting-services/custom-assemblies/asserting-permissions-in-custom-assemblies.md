---
title: Berechtigungserteilung in benutzerdefinierten Assemblys | Microsoft-Dokumentationen
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- secure calls [Reporting Services]
- custom assemblies [Reporting Services], permissions
- permission sets [Reporting Services]
- asserting permissions
- permissions [Reporting Services], custom assemblies
- limited permission sets
- security configuration files [Reporting Services]
ms.assetid: 3afb9631-f15e-405e-990b-ee102828f298
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: cba3c0b74712b6b4d0f6b5c58925cfd562f0df77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607542"
---
# <a name="asserting-permissions-in-custom-assemblies"></a><span data-ttu-id="9971b-102">Berechtigungserteilung in benutzerdefinierten Assemblys</span><span class="sxs-lookup"><span data-stu-id="9971b-102">Asserting Permissions in Custom Assemblies</span></span>
  <span data-ttu-id="9971b-103">Standardmäßig wird Code von benutzerdefinierten Assemblys mit dem eingeschränkten Berechtigungssatz **Execution** ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="9971b-103">By default, custom assembly code runs with the limited **Execution** permission set.</span></span> <span data-ttu-id="9971b-104">In einigen Fällen möchten Sie vielleicht eine benutzerdefinierte Assembly implementieren, die gesicherte Aufrufe an geschützte Ressourcen innerhalb Ihres Sicherheitssystems durchführt (z. B. an Dateien oder die Registrierung).</span><span class="sxs-lookup"><span data-stu-id="9971b-104">In some cases, you may wish to implement a custom assembly that makes secured calls to protected resources within your security system (such as a file or the registry).</span></span> <span data-ttu-id="9971b-105">Hierzu müssen Sie folgende Schritte durchführen:</span><span class="sxs-lookup"><span data-stu-id="9971b-105">In order to accomplish this, you must do the following:</span></span>  
  
1.  <span data-ttu-id="9971b-106">Identifizieren Sie die genauen Berechtigungen, die der Code benötigt, um den gesicherten Aufruf zu machen.</span><span class="sxs-lookup"><span data-stu-id="9971b-106">Identify the exact permissions that your code needs in order to make the secured call.</span></span> <span data-ttu-id="9971b-107">Wenn diese Methode Teil einer- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Bibliothek ist, sollten diese Informationen in der-Methoden Dokumentation enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="9971b-107">If this method is part of a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] library, this information should be included in the method documentation.</span></span>  
  
2.  <span data-ttu-id="9971b-108">Ändern Sie die Dateien für die Berichtsserver-Richtlinienkonfiguration, um der benutzerdefinierten Assembly die erforderlichen Berechtigungen zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="9971b-108">Modify the report server policy configuration files in order to grant the custom assembly the required permissions.</span></span> <span data-ttu-id="9971b-109">Weitere Informationen zu den Konfigurationsdateien der Sicherheitsrichtlinie finden Sie unter [Using Reporting Services Security Policy Files (Verwenden von Reporting Services-Sicherheitsrichtliniendateien)](../extensions/secure-development/using-reporting-services-security-policy-files.md).</span><span class="sxs-lookup"><span data-stu-id="9971b-109">For more information about the security policy configuration files, see [Using Reporting Services Security Policy Files](../extensions/secure-development/using-reporting-services-security-policy-files.md).</span></span>  
  
3.  <span data-ttu-id="9971b-110">Erteilen Sie die erforderlichen Berechtigungen als ein Teil der Methode, in der der gesicherte Aufruf gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="9971b-110">Assert the required permissions as part of the method in which the secure call is made.</span></span> <span data-ttu-id="9971b-111">Dies ist notwendig, da der vom Berichtsserver aufgerufene Code für die benutzerdefinierte Assembly ein Teil der Berichtsausdrucks-Hostassembly ist, die standardmäßig mit der Berechtigung **Execution** ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9971b-111">This is required because the custom assembly code that is called by the report server is part of the report expression host assembly, which runs with **Execution** permission by default.</span></span> <span data-ttu-id="9971b-112">Der Berechtigungssatz **Execution** besagt, dass Code ausgeführt werden kann, aber keine geschützten Ressourcen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="9971b-112">The **Execution** permission set enables code to run, but not to use protected resources.</span></span>  
  
4.  <span data-ttu-id="9971b-113">Markieren Sie die benutzerdefinierte Assembly mit **AllowPartiallyTrustedCallersAttribute**, wenn sie mit einem sicheren Namen signiert wird.</span><span class="sxs-lookup"><span data-stu-id="9971b-113">Mark the custom assembly with **AllowPartiallyTrustedCallersAttribute** if it is signed with a strong name.</span></span> <span data-ttu-id="9971b-114">Dies ist notwendig, da benutzerdefinierte Assemblys von einem Berichtsausdruck aufgerufen werden, der Teil der Berichtsausdrucks-Hostassembly ist, die standardmäßig nicht **FullTrust** erhält und die somit nur „teilweise vertrauenswürdig“ ist.</span><span class="sxs-lookup"><span data-stu-id="9971b-114">This is required because custom assemblies are called from a report expression that is part of the report expression host assembly, which, by default, is not granted **FullTrust**; thus it is a "partially trusted" caller.</span></span> <span data-ttu-id="9971b-115">Weitere Informationen finden Sie unter [Using Strong-Named Custom Assemblies (Verwenden von benutzerdefinierten Assemblys mit starken Namen)](using-strong-named-custom-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="9971b-115">For more information, see [Using Strong-Named Custom Assemblies](using-strong-named-custom-assemblies.md).</span></span>  
  
## <a name="implementing-a-secure-call"></a><span data-ttu-id="9971b-116">Implementieren sicherer Aufrufe</span><span class="sxs-lookup"><span data-stu-id="9971b-116">Implementing a Secure Call</span></span>  
 <span data-ttu-id="9971b-117">Sie können die Dateien für die Richtlinienkonfiguration ändern, um der Assembly bestimmte Berechtigungen zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="9971b-117">You can modify the policy configuration files to grant your assembly specific permissions.</span></span> <span data-ttu-id="9971b-118">Wenn Sie beispielsweise eine benutzerdefinierte Assembly für die Währungsumrechnung schreiben, kann es nötig sein, dass die aktuellen Wechselkurse aus einer Datei gelesen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="9971b-118">For example, if you were writing a custom assembly to handle currency conversion, you might need to read the current currency exchange rates from a file.</span></span> <span data-ttu-id="9971b-119">Sie müssen ein weiteres Sicherheitsrecht, **FileIOPermission**, zum Berechtigungssatz der Assembly hinzufügen, um die Kursdaten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="9971b-119">To retrieve the rate information, you would need to add an additional security permission, **FileIOPermission**, to your permission set for the assembly.</span></span> <span data-ttu-id="9971b-120">Sie können folgenden zusätzlichen Eintrag in der Datei für die Richtlinienkonfiguration vornehmen:</span><span class="sxs-lookup"><span data-stu-id="9971b-120">You can make the following additional entry in the policy configuration file:</span></span>  
  
```  
<PermissionSet class="NamedPermissionSet"  
   version="1"  
   Name="CurrencyRatesFilePermissionSet"  
   Description="A special permission set that grants read access to my currency rates file.">  
      <IPermission class="FileIOPermission"  
         version="1"  
         Read="C:\CurrencyRates.xml"/>  
      <IPermission class="SecurityPermission"  
         version="1"  
         Flags="Execution, Assertion"/>  
</PermissionSet>  
```  
  
 <span data-ttu-id="9971b-121">Sie fügen dann eine Codegruppe hinzu, die auf diesen Berechtigungssatz verweist:</span><span class="sxs-lookup"><span data-stu-id="9971b-121">You then add a code group that references that permission set:</span></span>  
  
```  
<CodeGroup class="UnionCodeGroup"  
   version="1"  
   PermissionSetName="CurrencyRatesFilePermissionSet"  
   Name="MyNewCodeGroup"  
   Description="A special code group for my custom assembly.">  
   <IMembershipCondition class="UrlMembershipCondition"  
      version="1"  
      Url="C:\Program Files\Microsoft SQL Server\MSRS10_50.MSSQLSERVER\MSSQL\Reporting Services\ReportServer\bin\CurrencyConversion.dll"/>  
</CodeGroup>  
```  
  
 <span data-ttu-id="9971b-122">Damit Ihr Code die entsprechende Berechtigung erhält, müssen Sie diese Berechtigung im Code der benutzerdefinierten Assembly erteilen.</span><span class="sxs-lookup"><span data-stu-id="9971b-122">In order for your code to acquire the appropriate permission, you must assert the permission within your custom assembly code.</span></span> <span data-ttu-id="9971b-123">Wenn Sie beispielsweise Lesezugriff zur XML-Datei, C:\CurrencyRates.xml, hinzufügen möchten, müssen Sie folgenden Code zu Ihrer Methode hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="9971b-123">For example, if you want to add read-only access to an XML file, C:\CurrencyRates.xml, you must add the following code to your method:</span></span>  
  
```  
// C#  
FileIOPermission permission = new FileIOPermission(FileIOPermissionAccess.Read, @"C:\CurrencyRates.xml");  
try  
{  
   permission.Assert();  
   // Load the XML currency rates file  
   XmlDocument doc = new XmlDocument();  
   doc.Load(@"C:\CurrencyRates.xml");  
...  
```  
  
 <span data-ttu-id="9971b-124">Sie können diese Erteilung auch als Methodenattribut hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="9971b-124">You can also add the assertion as a method attribute:</span></span>  
  
```  
[FileIOPermissionAttribute(SecurityAction.Assert, Read=@"C:\CurrencyRates.xml")]  
```  
  
 <span data-ttu-id="9971b-125">Weitere Informationen finden Sie in der .NET Framework-Sicherheit im .NET Framework Developer's Guide.</span><span class="sxs-lookup"><span data-stu-id="9971b-125">For more information, see ".NET Framework Security" in the .NET Framework Developer's Guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9971b-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9971b-126">See Also</span></span>  
 [<span data-ttu-id="9971b-127">Verwenden benutzerdefinierter Assemblys mit Berichten</span><span class="sxs-lookup"><span data-stu-id="9971b-127">Using Custom Assemblies with Reports</span></span>](using-custom-assemblies-with-reports.md)  
  
  
