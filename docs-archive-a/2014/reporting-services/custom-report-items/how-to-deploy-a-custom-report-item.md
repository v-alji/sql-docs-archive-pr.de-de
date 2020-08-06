---
title: 'Gewusst wie: Bereitstellen eines benutzerdefinierten Berichtselements | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, deploying
ms.assetid: 80e97b0d-e355-4240-aebd-08cbc84089ed
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 66519610526478caadeb41b48c9823414e88d5d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725313"
---
# <a name="how-to-deploy-a-custom-report-item"></a><span data-ttu-id="279fb-102">Gewusst wie: Bereitstellen eines benutzerdefinierten Berichtselements</span><span class="sxs-lookup"><span data-stu-id="279fb-102">How to: Deploy a Custom Report Item</span></span>
  <span data-ttu-id="279fb-103">Zum Bereitstellen eines benutzerdefinierten Berichtselements in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] müssen Sie die Konfigurationsdateien des Berichtsservers ändern und die Entwurfszeit- und die Laufzeitkomponentenassemblys in die entsprechenden Anwendungsordner für den Berichts-Designer und den Berichtsserver kopieren.</span><span class="sxs-lookup"><span data-stu-id="279fb-103">To deploy a custom report item in [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)], you must modify the report server configuration files and copy the design-time and run-time component assemblies into the appropriate application folders for both Report Designer and the report server.</span></span>  
  
### <a name="to-deploy-a-custom-report-item"></a><span data-ttu-id="279fb-104">So stellen Sie ein benutzerdefiniertes Berichtselement bereit</span><span class="sxs-lookup"><span data-stu-id="279fb-104">To deploy a custom report item</span></span>  
  
1.  <span data-ttu-id="279fb-105">Bearbeiten Sie die Datei Rsreportdesigner.config, um die Laufzeit- und Entwurfszeitkomponenten für ein benutzerdefiniertes Berichtselement für die Verwendung im Designer zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="279fb-105">Edit the Rsreportdesigner.config file to configure the custom report item run-time and design-time components for use in the designer.</span></span> <span data-ttu-id="279fb-106">Beachten Sie dabei, dass der `ReportItemName`-Eintrag mit dem in der `CustomReportItemAttribute`-Klasse verwendeten `CustomReportItemDesigner`-Attribut übereinstimmen muss.</span><span class="sxs-lookup"><span data-stu-id="279fb-106">Note that the `ReportItemName` entry must match the `CustomReportItemAttribute` attribute used in your `CustomReportItemDesigner` class.</span></span> <span data-ttu-id="279fb-107">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="279fb-107">For example:</span></span>  
  
    ```  
    <ReportItems>  
       <ReportItem Name="Polygons" Type="PolygonsCRI.PolygonsCRI,PolygonsCRI"/>  
    </ReportItems>  
    <ReportItemDesigner>  
       <ReportItem Name="Polygons" Type="PolygonsCRI.PolygonsDesigner, PolygonsDesigner" />  
    </ReportItemDesigner>  
    <ReportItemConverter>  
       <Converter Source="Chart" Target="Polygons" Type="PolygonsCRI.PolygonsConverter, PolygonsDesigner" />  
    </ReportItemConverter>  
    ```  
  
2.  <span data-ttu-id="279fb-108">Bearbeiten Sie die Datei Rsreportserver.config, um die Laufzeitkomponente für ein benutzerdefiniertes Berichtselement zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="279fb-108">Edit the Rsreportserver.config file to register the custom report item run-time component.</span></span> <span data-ttu-id="279fb-109">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="279fb-109">For example:</span></span>  
  
    ```  
    <ReportItems>  
       <ReportItem Name="Polygons" Type="PolygonsCRI.PolygonsCRI,PolygonsCRI"/>  
    </ReportItems>  
    ```  
  
3.  <span data-ttu-id="279fb-110">Bearbeiten Sie die Datei Rsssrvpolicy.config, um ein `CodeGroup`-Objekt hinzuzufügen, das dem benutzerdefinierten Berichtselement die richtigen Berechtigungen gewährt.</span><span class="sxs-lookup"><span data-stu-id="279fb-110">Edit the Rsssrvpolicy.config file to add a `CodeGroup` that grants the proper permissions to the custom report item.</span></span> <span data-ttu-id="279fb-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="279fb-111">For example:</span></span>  
  
    ```  
    <CodeGroup   
       class="UnionCodeGroup"   
       version="1"   
       PermissionSetName="FullTrust"  
       Description="This code group grants MyCustomReportItem.dll FullTrust permission. ">  
       <IMembershipCondition   
          class="UrlMembershipCondition"  
          version="1"  
       Url="C:\Program Files\Microsoft SQL Server\ MSRS10_50.SQLSERVER\Reporting Services\ReportServer\bin\MyCustomReportItem.dll" />  
    </CodeGroup>  
    ```  
  
4.  <span data-ttu-id="279fb-112">Kopieren Sie die Laufzeitkomponenten-DLL für ein benutzerdefiniertes Berichtselement in die Verzeichnisse %ProgramFiles%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies und \Programme\Microsoft SQL Server\MSRS10_50.SQLSERVER\Reporting Services\ReportServer\bin.</span><span class="sxs-lookup"><span data-stu-id="279fb-112">Copy the custom report item run-time component DLL to the %ProgramFiles%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies and \Program Files\Microsoft SQL Server\MSRS10_50.SQLSERVER\Reporting Services\ReportServer\bin directories.</span></span>  
  
5.  <span data-ttu-id="279fb-113">Kopieren Sie die Entwurfszeitkomponenten-DLL für ein benutzerdefiniertes Berichtselement in das Verzeichnis %ProgramFiles%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies.</span><span class="sxs-lookup"><span data-stu-id="279fb-113">Copy the custom report item design-time component DLL to the %ProgramFiles%\Microsoft Visual Studio 9.0\Common7\IDE\PrivateAssemblies directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="279fb-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="279fb-114">See Also</span></span>  
 <span data-ttu-id="279fb-115">[Reporting Services-Konfigurationsdateien](../report-server/reporting-services-configuration-files.md) </span><span class="sxs-lookup"><span data-stu-id="279fb-115">[Reporting Services Configuration Files](../report-server/reporting-services-configuration-files.md) </span></span>  
 [<span data-ttu-id="279fb-116">Klassenbibliotheken für ein benutzerdefiniertes Berichtselement</span><span class="sxs-lookup"><span data-stu-id="279fb-116">Custom Report Item Class Libraries</span></span>](custom-report-item-class-libraries.md)  
  
  
