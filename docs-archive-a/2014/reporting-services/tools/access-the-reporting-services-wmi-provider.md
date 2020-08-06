---
title: Auf den WMI-Anbieter für Reporting Services zugreifen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- Reporting Services WMI Provider
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- WMI provider [Reporting Services]
- programming [Reporting Services]
ms.assetid: 22cfbeb8-4ea3-4182-8f54-3341c771e87b
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: db0848ae8c988229a1804bbd4b19e6c38b68c35f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722514"
---
# <a name="access-the-reporting-services-wmi-provider"></a><span data-ttu-id="b55e2-102">Zugreifen auf den Reporting Services-WMI-Anbieter</span><span class="sxs-lookup"><span data-stu-id="b55e2-102">Access the Reporting Services WMI Provider</span></span>
  <span data-ttu-id="b55e2-103">Der Reporting Services-WMI-Anbieter macht zwei WMI-Klassen für die Verwaltung von Berichtsserverinstanzen im einheitlichen Modus durch Skripterstellung verfügbar:</span><span class="sxs-lookup"><span data-stu-id="b55e2-103">The Reporting Services WMI provider exposes two WMI classes for administration of Native mode report server instances through scripting:</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b55e2-104">Ab der [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] -Version wird der WMI-Anbieter nur für Berichtsserver im einheitlichen Modus unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b55e2-104">Starting with the [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] release, the WMI provider is supported for only native mode report servers.</span></span> <span data-ttu-id="b55e2-105">Berichtsserver im SharePoint-Modus können über Seiten der SharePoint-Zentraladministration und PowerShell-Skripts verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="b55e2-105">SharePoint mode report servers can be managed with SharePoint Central Administration pages and PowerShell scripts.</span></span>  
  
|<span data-ttu-id="b55e2-106">Klasse</span><span class="sxs-lookup"><span data-stu-id="b55e2-106">Class</span></span>|<span data-ttu-id="b55e2-107">Namespace</span><span class="sxs-lookup"><span data-stu-id="b55e2-107">Namespace</span></span>|<span data-ttu-id="b55e2-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b55e2-108">Description</span></span>|  
|-----------|---------------|-----------------|  
|<span data-ttu-id="b55e2-109">MSReportServer_Instance</span><span class="sxs-lookup"><span data-stu-id="b55e2-109">MSReportServer_Instance</span></span>|<span data-ttu-id="b55e2-110">root\microsoft\sqlserver\reportserver\ RS_ *\<EncodedInstanceName>* \v11</span><span class="sxs-lookup"><span data-stu-id="b55e2-110">root\Microsoft\SqlServer\ReportServer\RS_*\<EncodedInstanceName>* \v11</span></span>|<span data-ttu-id="b55e2-111">Stellt grundlegende Informationen bereit, die ein Client benötigt, um eine Verbindung mit einem installierten Berichtsserver herzustellen.</span><span class="sxs-lookup"><span data-stu-id="b55e2-111">Provides basic information required for a client to connect to an installed report server.</span></span>|  
|<span data-ttu-id="b55e2-112">MSReportServer_ConfigurationSetting</span><span class="sxs-lookup"><span data-stu-id="b55e2-112">MSReportServer_ConfigurationSetting</span></span>|<span data-ttu-id="b55e2-113">root\microsoft\sqlserver\reportserver\ RS_ *\<EncodedInstanceName>* \v11\admin</span><span class="sxs-lookup"><span data-stu-id="b55e2-113">root\Microsoft\SqlServer\ReportServer\RS_*\<EncodedInstanceName>* \v11\Admin</span></span>|<span data-ttu-id="b55e2-114">Stellt die Installationsparameter und die Laufzeitparameter einer Berichtsserverinstanz dar.</span><span class="sxs-lookup"><span data-stu-id="b55e2-114">Represents the installation and run-time parameters of a report server instance.</span></span> <span data-ttu-id="b55e2-115">Diese Parameter werden in der Konfigurationsdatei für den Berichtsserver gespeichert.</span><span class="sxs-lookup"><span data-stu-id="b55e2-115">These parameters are stored in the configuration file for the report server.</span></span><br /><br /> <span data-ttu-id="b55e2-116">**\*\* Wichtig \*\*** Für den Zugriffe auf diese Klasse sind Administratorrechte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b55e2-116">**\*\* Important \*\*** This class is only accessible with administrative privileges.</span></span>|  
  
 <span data-ttu-id="b55e2-117">Für jede Berichtsserverinstanz wird eine Instanz von jeder der oben erwähnten Klassen erstellt.</span><span class="sxs-lookup"><span data-stu-id="b55e2-117">An instance of each of the above classes is created for each report server instance.</span></span> <span data-ttu-id="b55e2-118">Sie können mit jedem Microsoft- oder Drittanbietertool auf die WMI-Objekte zugreifen, die vom Berichtsserver verfügbar gemacht werden, einschließlich WMI-Programmierungsschnittstellen, die von .NET Framework verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="b55e2-118">You can use any Microsoft or third party tools to access the WMI objects exposed by the report server, including WMI programming interfaces exposed by the .NET Framework itself.</span></span> <span data-ttu-id="b55e2-119">In diesem Thema wird die Verwendung von und der Zugriff auf WMI-Klasseninstanzen mit dem PowerShell-Befehl [Get-WmiObject](https://technet.microsoft.com/library/dd315295.aspx)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b55e2-119">This topic describes how to access and use the WMI class instances with the PowerShell command [Get-WmiObject](https://technet.microsoft.com/library/dd315295.aspx).</span></span>  
  
## <a name="determine-the-instance-name-in-the-namespace-string"></a><span data-ttu-id="b55e2-120">Bestimmen des Instanznamens in der Namespacezeichenfolge</span><span class="sxs-lookup"><span data-stu-id="b55e2-120">Determine the Instance Name in the Namespace String</span></span>  
 <span data-ttu-id="b55e2-121">Der Instanzname im Namespacepfad für Reporting Services-WMI-Klassen stellt eine Codierung des Instanznamens dar, den Sie angeben, wenn Sie die benannten Reporting Services-Instanzen installieren.</span><span class="sxs-lookup"><span data-stu-id="b55e2-121">The instance name in the namespace path for the Reporting Services WMI classes is an encoding of the instance names that you specify when installing the named Reporting Services instances.</span></span> <span data-ttu-id="b55e2-122">Und zwar werden die Sonderzeichen in den Instanznamen codiert.</span><span class="sxs-lookup"><span data-stu-id="b55e2-122">Namely, special characters in the instance names are encoded.</span></span> <span data-ttu-id="b55e2-123">Ein Unterstrich (_) wird z.B. als „_5f“ codiert, d.h., der Instanzname „My_Instance“ wird im WMI-Namespacepfad als „My_5fInstance“ codiert.</span><span class="sxs-lookup"><span data-stu-id="b55e2-123">For example, an underline (_) is encoded as "_5f", so an instance name of "My_Instance" is encoded as "My_5fInstance" in the WMI namespace path.</span></span>  
  
 <span data-ttu-id="b55e2-124">Um die codierten Instanznamen der Berichtsserverinstanzen im WMI-Namespacepfad aufzulisten, verwenden Sie den folgenden PowerShell-Befehl:</span><span class="sxs-lookup"><span data-stu-id="b55e2-124">To list the encoded instance names of your report server instances in the WMI namespace path, use the following PowerShell command:</span></span>  
  
```powershell
Get-WmiObject -Namespace root\Microsoft\SqlServer\ReportServer -Class __Namespace -ComputerName hostname | Select Name  
```  
  
## <a name="access-the-wmi-classes-using-powershell"></a><span data-ttu-id="b55e2-125">Zugreifen auf die WMI-Klassen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="b55e2-125">Access the WMI Classes Using PowerShell</span></span>  
 <span data-ttu-id="b55e2-126">Führen Sie den folgenden Befehl aus, um auf die WMI-Klassen zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="b55e2-126">To access the WMI classes, run the following command:</span></span>  
  
```powershell
Get-WmiObject -Namespace <namespacename> -Class <classname> -ComputerName <hostname>  
```  
  
 <span data-ttu-id="b55e2-127">Um z. B. auf die MSReportServer_ConfigurationSetting-Klasse der Standardberichtsserverinstanz des Host "myrshost" zuzugreifen, führen Sie den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="b55e2-127">For example, to access the MSReportServer_ConfigurationSetting class on the default report server instance of the host myrshost, run the following command.</span></span> <span data-ttu-id="b55e2-128">Für eine erfolgreiche Ausführungs dieses Befehls muss die Standardberichtsserverinstanz auf myrshost installiert sein.</span><span class="sxs-lookup"><span data-stu-id="b55e2-128">The default report server instance must be installed on myrshost for this command to succeed.</span></span>  
  
```powershell
Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLSERER\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost  
```  
  
 <span data-ttu-id="b55e2-129">Mit dieser Befehlssyntax werden alle Klasseneigenschaftsnamen und -werte ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="b55e2-129">This command syntax outputs all class property names and values.</span></span> <span data-ttu-id="b55e2-130">Hinweis: Alle Instanzen der Klasse "MSReportServer_ConfigurationSetting" werden zurückgegeben, auch wenn der Zugriff auf die Klasse im Namespace der Standardberichtsserverinstanz (RS_MSSQLSERVER) erfolgt.</span><span class="sxs-lookup"><span data-stu-id="b55e2-130">Note that all instances of the class MSReportServer_ConfigurationSetting is returned, even though you are accessing the class in the namespace of the default report server instance (RS_MSSQLSERVER).</span></span> <span data-ttu-id="b55e2-131">Wenn myrshost z. B. mit der Standardberichtsserverinstanz und einer benannten Berichtsserverinstanz mit dem Namen SHAREPOINT installiert ist, werden mit diesem Befehl zwei WMI-Objekte zurückgegeben und die Eigenschaftsnamen und Werte für beide Berichtsserverinstanzen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="b55e2-131">For example, if myrshost is installed with the default report server instance and a named report server instance called SHAREPOINT, this command will return two WMI objects and output the property names and values for both report server instances.</span></span>  
  
 <span data-ttu-id="b55e2-132">Um eine bestimmte Klasseninstanz zurückzugeben, wenn mehrere Instanzen zurückgegeben werden, verwenden Sie den Parameter „-Filter“, um die Ergebnisse basierend auf den Eigenschaften mit eindeutigen Werten, z.B. InstanceName, zu filtern.</span><span class="sxs-lookup"><span data-stu-id="b55e2-132">To return a specific class instance when multiple instances are returned, use the -Filter parameter to filter the results based on properties with unique values such as InstanceName.</span></span> <span data-ttu-id="b55e2-133">Wenn Sie z. B. nur das WMI-Objekt für die Standardberichtsserverinstanz zurückgeben möchten, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="b55e2-133">For example, to return only the WMI object for the default report server instance, use the following command:</span></span>  
  
```powershell
Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLServer\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost -Filter "InstanceName='MSSQLSERVER'"  
```  
  
## <a name="query-the-available-methods-and-properties"></a><span data-ttu-id="b55e2-134">Abfragen der verfügbaren Methoden und Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b55e2-134">Query the Available Methods and Properties</span></span>  
 <span data-ttu-id="b55e2-135">Um die in einer der Reporting Services-WMI-Klassen verfügbaren Methoden und Eigenschaften anzuzeigen, reichen Sie die Ergebnisse von Get-WmiObject an den Get-Member-Befehl weiter.</span><span class="sxs-lookup"><span data-stu-id="b55e2-135">To see what methods and properties are available in one of the Reporting Services WMI classes, pipe the results from Get-WmiObject to the Get-Member command.</span></span> <span data-ttu-id="b55e2-136">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b55e2-136">For example:</span></span>  
  
```powershell
Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLServer\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost | Get-Member  
```  
  
 <span data-ttu-id="b55e2-137">Dokumentation zu den Eigenschaften und Methoden der Reporting Services WMI-Klassen finden Sie unter....</span><span class="sxs-lookup"><span data-stu-id="b55e2-137">For documentation on the properties and methods of the Reporting Services WMI classes, see ....</span></span>  
  
## <a name="use-a-wmi-method-or-property"></a><span data-ttu-id="b55e2-138">Verwenden einer WMI-Methode oder -Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="b55e2-138">Use a WMI Method or Property</span></span>  
 <span data-ttu-id="b55e2-139">Wenn Sie die WMI-Objekte der Reporting Services-Klassen abgerufen haben und die verfügbaren Methoden und Eigenschaften kennen, können Sie diese Methoden und Eigenschaften verwenden.</span><span class="sxs-lookup"><span data-stu-id="b55e2-139">Once you have the WMI objects to the Reporting Services classes and know the available methods and properties, you can use these methods and properties.</span></span> <span data-ttu-id="b55e2-140">Wenn z. B. eine Berichtsserverinstanz mit dem Namen SHAREPOINT im integrierten SharePoint-Modus vorhanden ist, rufen Sie die URL für die Website der SharePoint-Zentraladministration mithilfe der folgenden Befehlssequenz ab:</span><span class="sxs-lookup"><span data-stu-id="b55e2-140">For example, if you have a named report server instance in SharePoint integrated mode called SHAREPOINT, use the following command sequence to retrieve the URL for the SharePoint Central Administration site:</span></span>  
  
```powershell
$rsconfig = Get-WmiObject -Namespace "root\Microsoft\SqlServer\ReportServer\RS_MSSQLServer\v11\Admin" -Class MSReportServer_ConfigurationSetting -ComputerName myrshost -Filter "InstanceName='SHAREPOINT'"  
$rsconfig.GetAdminSiteUrl()  
```  
  
## <a name="see-also"></a><span data-ttu-id="b55e2-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b55e2-141">See Also</span></span>
 <span data-ttu-id="b55e2-142">[Reporting Services WMI-Anbieter Bibliotheks Referenz &#40;SSRS&#41;](../wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="b55e2-142">[Reporting Services WMI Provider Library Reference &#40;SSRS&#41;](../wmi-provider-library-reference/reporting-services-wmi-provider-library-reference-ssrs.md) </span></span>  
 [<span data-ttu-id="b55e2-143">RSReportServer Configuration File</span><span class="sxs-lookup"><span data-stu-id="b55e2-143">RSReportServer Configuration File</span></span>](../report-server/rsreportserver-config-configuration-file.md)  
