---
title: Atom-Geräteinformationseinstellungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fe4a56a4-5552-423c-85c1-895e2e212fee
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bdbac1500063accf868d4b538b82ba9f3b5aebb0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617817"
---
# <a name="atom-device-information-settings"></a><span data-ttu-id="42032-102">ATOM-Geräteinformationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="42032-102">ATOM Device Information Settings</span></span>
  <span data-ttu-id="42032-103">Die Geräteinformationseinstellungen für die Atom-Renderingerweiterung unterstützen die Übergabe des Namens eines Atom-Feeds und der zu verwendenden Zeichencodierung.</span><span class="sxs-lookup"><span data-stu-id="42032-103">The device information settings for the Atom rendering extension support submittal of the name of an Atom feed and character encoding to use.</span></span>  
  
 <span data-ttu-id="42032-104">In der folgenden Tabelle sind die Geräteinformationseinstellungen für das Rendering in einem Datendienstdokument aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="42032-104">The following table lists the device information settings for rendering to a data service document.</span></span>  
  
|<span data-ttu-id="42032-105">Einstellung</span><span class="sxs-lookup"><span data-stu-id="42032-105">Setting</span></span>|<span data-ttu-id="42032-106">value</span><span class="sxs-lookup"><span data-stu-id="42032-106">Value</span></span>|  
|-------------|-----------|  
|`DataFeed`|<span data-ttu-id="42032-107">Wenn diese Einstellung angegeben ist, wird der Atom-Feed entsprechend dem Feednamen gerendert, der in ihr bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="42032-107">If specified, renders the Atom feed corresponding to the feed name provided in this setting.</span></span> <span data-ttu-id="42032-108">Andernfalls wird das Atom-Dienstdokument für den Bericht gerendert.</span><span class="sxs-lookup"><span data-stu-id="42032-108">If not, renders the Atom service document for the report.</span></span> <span data-ttu-id="42032-109">Der eindeutige automatisch generierte Bezeichner des Datenfeeds.</span><span class="sxs-lookup"><span data-stu-id="42032-109">The unique auto-generated identifier of the data feed.</span></span> <span data-ttu-id="42032-110">Dieser Wert wird intern verwendet, und Sie sollten ihn nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="42032-110">This  value is used internally and you should not change it.</span></span>|  
|<span data-ttu-id="42032-111">**Codierung**</span><span class="sxs-lookup"><span data-stu-id="42032-111">**Encoding**</span></span>|<span data-ttu-id="42032-112">Der Internet Assigned Numbers Authority (IANA)-Name einer Zeichencodierung, die von .NET Framework unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="42032-112">The Internet Assigned Numbers Authority (IANA) name of a character encoding that is supported by the .NET Framework.</span></span> <span data-ttu-id="42032-113">Standardwert: `UTF-8`.</span><span class="sxs-lookup"><span data-stu-id="42032-113">The default value is `UTF-8`.</span></span> <span data-ttu-id="42032-114">Beispiele für andere Werte: ASCII, UTF-7 und UTF-16.</span><span class="sxs-lookup"><span data-stu-id="42032-114">Examples of other values include ASCII, UTF-7, and UTF-16.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="42032-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="42032-115">See Also</span></span>  
 <xref:ReportExecution2005.ReportExecutionService.Render%2A>   
 <span data-ttu-id="42032-116">[Übergeben von Geräte Informationseinstellungen an Renderingerweiterungen](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="42032-116">[Passing Device Information Settings to Rendering Extensions](report-server-web-service/net-framework/passing-device-information-settings-to-rendering-extensions.md) </span></span>  
 <span data-ttu-id="42032-117">[Anpassen von Renderingerweiterungsparametern in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span><span class="sxs-lookup"><span data-stu-id="42032-117">[Customize Rendering Extension Parameters in RSReportServer.Config](customize-rendering-extension-parameters-in-rsreportserver-config.md) </span></span>  
 [<span data-ttu-id="42032-118">Technische Referenz (SSRS)</span><span class="sxs-lookup"><span data-stu-id="42032-118">Technical Reference &#40;SSRS&#41;</span></span>](../../2014/reporting-services/technical-reference-ssrs.md)  
  
  
