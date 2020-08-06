---
title: Weglassen von Werten für optionale Webdienstobjekte | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- Web service [Reporting Services], omitted values
- XML Web service [Reporting Services], omitted values
- Report Server Web service, omitted values
- omitting values [Reporting Services]
ms.assetid: ceb68b8b-9214-4745-abc9-f47f33ecd6f7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3858f73e1b332acfa1a1bbc640007f6f0884abff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697494"
---
# <a name="omitting-values-for-optional-web-service-objects"></a><span data-ttu-id="2b705-102">Weglassen von Werten für optionale Webdienstobjekte</span><span class="sxs-lookup"><span data-stu-id="2b705-102">Omitting Values for Optional Web Service Objects</span></span>
  <span data-ttu-id="2b705-103">Eigenschaften von mehreren der komplexen Typen eines Berichtsserver-Webdiensts besitzen eine zugehörige Eigenschaft, die als die Specified-Eigenschaft bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="2b705-103">Properties of several of the Report Server Web service complex types have an accompanying property known as the Specified property.</span></span> <span data-ttu-id="2b705-104">Der Name der Eigenschaft setzt sich aus dem ursprünglichen Eigenschaftennamen und dem daran angefügten Wort "Specified" zusammen.</span><span class="sxs-lookup"><span data-stu-id="2b705-104">The name of the property consists of the original property name with the word "Specified" appended to it.</span></span> <span data-ttu-id="2b705-105">Wenn diese Eigenschaft vorhanden ist, bedeutet dies, dass ein Wert für die ursprüngliche Eigenschaft unter Umständen manchmal weggelassen wird.</span><span class="sxs-lookup"><span data-stu-id="2b705-105">The presence of this property indicates that a value for the original property may sometimes be omitted.</span></span> <span data-ttu-id="2b705-106">Das ist das direkte Ergebnis der Übersetzung aus WSDL (Web Service Description Language) in eine [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]-Proxyklasse.</span><span class="sxs-lookup"><span data-stu-id="2b705-106">This is a direct result of the translation from the Web Service Description Language (WSDL) to a [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] proxy class.</span></span> <span data-ttu-id="2b705-107">Beispiel: Die Webdiensteigenschaft <xref:ReportService2010.DataSourceDefinition.Enabled%2A> des komplexen Typs <xref:ReportService2010.DataSourceDefinition> besitzt eine zugehörige Eigenschaft mit dem Namen <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A>.</span><span class="sxs-lookup"><span data-stu-id="2b705-107">For example, the Web service property <xref:ReportService2010.DataSourceDefinition.Enabled%2A> of the complex type <xref:ReportService2010.DataSourceDefinition> has an accompanying property named <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A>.</span></span> <span data-ttu-id="2b705-108">Wenn Sie eine Anwendung erstellen und keinen Wert für die <xref:ReportService2010.DataSourceDefinition.Enabled%2A>-Eigenschaft festlegen möchten, müssen keinen Wert für <xref:ReportService2010.DataSourceDefinition.Enabled%2A> angeben. Es wird der Standardwert `true` verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b705-108">If you are building an application and do not want to set a value for the <xref:ReportService2010.DataSourceDefinition.Enabled%2A> property, you do not have to supply a value for <xref:ReportService2010.DataSourceDefinition.Enabled%2A>; the default value of `true` is used.</span></span> <span data-ttu-id="2b705-109">Sie müssen <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> jedoch trotzdem auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="2b705-109">However, you still need to set <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> to `false`.</span></span> <span data-ttu-id="2b705-110">Wenn Sie einen Wert für die <xref:ReportService2010.DataSourceDefinition.Enabled%2A>-Eigenschaft angeben, müssen Sie <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> gleich `true` festlegen.</span><span class="sxs-lookup"><span data-stu-id="2b705-110">If you supply a value for the <xref:ReportService2010.DataSourceDefinition.Enabled%2A> property, you need to set <xref:ReportService2010.DataSourceDefinition.EnabledSpecified%2A> equal to `true`.</span></span> <span data-ttu-id="2b705-111">Das ist bei schreibbaren Eigenschaften der Fall.</span><span class="sxs-lookup"><span data-stu-id="2b705-111">This is the case for writable properties.</span></span> <span data-ttu-id="2b705-112">Für schreibgeschützte Eigenschaften müssen Sie keine Aktion durchführen.</span><span class="sxs-lookup"><span data-stu-id="2b705-112">For read-only properties, you do not need to take any action.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2b705-113">Wird keine Eigenschaft mit den oben genannten Vorgehensweisen festgelegt, kann dies zu unvorgesehenem Verhalten des Webdiensts führen.</span><span class="sxs-lookup"><span data-stu-id="2b705-113">Failure to specify a property using the above-mentioned technique can result in unpredictable Web service behavior.</span></span>  
  
 <span data-ttu-id="2b705-114">Die Datentypen, für die Sie normalerweise die zusätzliche angegebene Eigenschaft behandeln müssen `Boolean` , sind, `DateTime` und `Enumeration` .</span><span class="sxs-lookup"><span data-stu-id="2b705-114">The data types that usually require you to handle the additional Specified property are `Boolean`, `DateTime`, and `Enumeration`.</span></span>  
  
 <span data-ttu-id="2b705-115">Ein Beispiel hierzu finden Sie unter <xref:ReportService2010.ReportingService2010.CreateDataSource%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="2b705-115">For an example, see <xref:ReportService2010.ReportingService2010.CreateDataSource%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b705-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2b705-116">See Also</span></span>  
 <span data-ttu-id="2b705-117">[Erstellen von Anwendungen mit dem Webdienst und .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span><span class="sxs-lookup"><span data-stu-id="2b705-117">[Building Applications Using the Web Service and the .NET Framework](building-applications-using-the-web-service-and-the-net-framework.md) </span></span>  
 [<span data-ttu-id="2b705-118">Technische Referenz (SSRS)</span><span class="sxs-lookup"><span data-stu-id="2b705-118">Technical Reference &#40;SSRS&#41;</span></span>](../../technical-reference-ssrs.md)  
  
  
