---
title: 'DatabaseQueryTimeout-Eigenschaft (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseQueryTimeout Property
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseQueryTimeout property
ms.assetid: 96faed97-9799-4bbf-a66f-fdd532d3eace
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2e92e3e0f6752ea99fe89c962ebe96e343c0195b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722334"
---
# <a name="databasequerytimeout-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="67199-102">DatabaseQueryTimeout-Eigenschaft (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="67199-102">DatabaseQueryTimeout Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="67199-103">Gibt die Anzahl von Sekunden an, die verstreichen müssen, ehe der Berichtsserver annimmt, dass der Befehl fehlgeschlagen ist oder die Ausführungszeit zu lang war.</span><span class="sxs-lookup"><span data-stu-id="67199-103">Specifies the number of seconds that must elapse before the report server assumes the command failed or took too much time to perform.</span></span> <span data-ttu-id="67199-104">Der Berichtsserver nimmt die zeitliche Steuerung der Abfrage anhand des SQL-Katalogs und nicht anhand einer Datenquelle für den Bericht vor.</span><span class="sxs-lookup"><span data-stu-id="67199-104">The report server is timing the querying against the SQL catalog, not a data source for the report.</span></span> <span data-ttu-id="67199-105">Lese-/Schreibzugriff.</span><span class="sxs-lookup"><span data-stu-id="67199-105">Read/write.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67199-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="67199-106">Syntax</span></span>  
  
```vb  
Public Dim DatabaseQueryTimeout As UInt32  
```  
  
```csharp  
public UInt32 DatabaseQueryTimeout;  
```  
  
## <a name="property-values"></a><span data-ttu-id="67199-107">Eigenschaftswerte</span><span class="sxs-lookup"><span data-stu-id="67199-107">Property Values</span></span>  
 <span data-ttu-id="67199-108">Ein 32-Bit-`integer`-Objekt ohne Vorzeichen, das die Anzahl der Sekunden darstellt, die für die Ausführung der Abfrage erlaubt sind</span><span class="sxs-lookup"><span data-stu-id="67199-108">A 32-bit unsigned `integer` object that represents the number of seconds that the query is allowed to run.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="67199-109">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="67199-109">Example Code</span></span>  
 [<span data-ttu-id="67199-110">MSReportServer_ConfigurationSetting Class (MSReportServer_ConfigurationSetting-Klasse)</span><span class="sxs-lookup"><span data-stu-id="67199-110">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="requirements"></a><span data-ttu-id="67199-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="67199-111">Requirements</span></span>  
 <span data-ttu-id="67199-112">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67199-112">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67199-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="67199-113">See Also</span></span>  
 [<span data-ttu-id="67199-114">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="67199-114">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
