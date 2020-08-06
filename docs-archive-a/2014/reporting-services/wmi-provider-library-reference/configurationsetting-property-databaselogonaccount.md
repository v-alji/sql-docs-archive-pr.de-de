---
title: DatabaseLogonAccount-Eigenschaft (WMI MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseLogonAccount
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseLogonAccount property
ms.assetid: 55f2863f-1ac1-4519-b512-e7f11c0ea5ea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6f9e844ff1d1447bd5abfefad8e82939575c7f47
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722349"
---
# <a name="databaselogonaccount-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="89bdd-102">DatabaseLogonAccount-Eigenschaft (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="89bdd-102">DatabaseLogonAccount Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="89bdd-103">Gibt das Anmeldekonto an, mit dem der Berichtsserver eine Verbindung mit der Berichtsserver-Datenbank herstellt.</span><span class="sxs-lookup"><span data-stu-id="89bdd-103">Specifies the logon account that the report server uses when connecting to the report server database.</span></span> <span data-ttu-id="89bdd-104">Schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="89bdd-104">Read only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89bdd-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="89bdd-105">Syntax</span></span>  
  
```vb  
Public Dim DatabaseLogonAccount As String  
```  
  
```csharp  
public string DatabaseLogonAccount;  
```  
  
## <a name="property-values"></a><span data-ttu-id="89bdd-106">Eigenschaftswerte</span><span class="sxs-lookup"><span data-stu-id="89bdd-106">Property Values</span></span>  
 <span data-ttu-id="89bdd-107">Ein `String`-Objekt, das den Namen des Anmeldekontos darstellt</span><span class="sxs-lookup"><span data-stu-id="89bdd-107">A `String` object that represents the logon account name.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="89bdd-108">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="89bdd-108">Example Code</span></span>  
 [<span data-ttu-id="89bdd-109">MSReportServer_ConfigurationSetting Class (MSReportServer_ConfigurationSetting-Klasse)</span><span class="sxs-lookup"><span data-stu-id="89bdd-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="remarks"></a><span data-ttu-id="89bdd-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="89bdd-110">Remarks</span></span>  
 <span data-ttu-id="89bdd-111">Gültige Werte für diese Eigenschaft hängen vom Wert der [DatabaseLogonType](configurationsetting-property-databaselogontype.md) -Eigenschaft ab.</span><span class="sxs-lookup"><span data-stu-id="89bdd-111">Valid values for this property will vary depending on the value of the [DatabaseLogonType](configurationsetting-property-databaselogontype.md) property.</span></span>  
  
 <span data-ttu-id="89bdd-112">Diese Eigenschaft wird ignoriert, wenn die [DatabaseLogonType](configurationsetting-property-databaselogontype.md) -Eigenschaft auf festgelegt ist `2 (Service)` .</span><span class="sxs-lookup"><span data-stu-id="89bdd-112">This property is ignored if the [DatabaseLogonType](configurationsetting-property-databaselogontype.md) property is set to `2 (Service)`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89bdd-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="89bdd-113">Requirements</span></span>  
 <span data-ttu-id="89bdd-114">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89bdd-114">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89bdd-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89bdd-115">See Also</span></span>  
 [<span data-ttu-id="89bdd-116">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="89bdd-116">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
