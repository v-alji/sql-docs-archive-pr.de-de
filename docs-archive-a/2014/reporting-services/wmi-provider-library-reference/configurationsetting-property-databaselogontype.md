---
title: 'DatabaseLogonType-Eigenschaft (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- DatabaseLogonType
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- DatabaseLogonType property
ms.assetid: 6b592582-4c35-4029-ab86-982fff47d8d6
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 3bb5a4149c29fb7532b7140a2616dd856e6db2b5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722338"
---
# <a name="databaselogontype-property-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="58390-102">DatabaseLogonType-Eigenschaft (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="58390-102">DatabaseLogonType Property (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="58390-103">Gibt an, ob der Berichtsserver für den Zugriff auf die Berichtsserver-Datenbank ein [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Dienstkonto, ein Windows-Benutzerkonto oder eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung verwendet.</span><span class="sxs-lookup"><span data-stu-id="58390-103">Specifies whether the report server uses a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows service account, a Windows user account, or a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login to access the report server database.</span></span> <span data-ttu-id="58390-104">Schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="58390-104">Read-only.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58390-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="58390-105">Syntax</span></span>  
  
```vb  
Public Dim DatabaseLogonType As Integer  
```  
  
```csharp  
public int DatabaseLogonType;  
```  
  
## <a name="property-values"></a><span data-ttu-id="58390-106">Eigenschaftswerte</span><span class="sxs-lookup"><span data-stu-id="58390-106">Property Values</span></span>  
 <span data-ttu-id="58390-107">Ein `integer`-Objekt, das den Anmeldetyp darstellt</span><span class="sxs-lookup"><span data-stu-id="58390-107">An `integer` object that represents the login type.</span></span>  
  
## <a name="example-code"></a><span data-ttu-id="58390-108">Beispielcode</span><span class="sxs-lookup"><span data-stu-id="58390-108">Example Code</span></span>  
 [<span data-ttu-id="58390-109">MSReportServer_ConfigurationSetting Class (MSReportServer_ConfigurationSetting-Klasse)</span><span class="sxs-lookup"><span data-stu-id="58390-109">MSReportServer_ConfigurationSetting Class</span></span>](msreportserver-configurationsetting-class.md)  
  
## <a name="remarks"></a><span data-ttu-id="58390-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="58390-110">Remarks</span></span>  
 <span data-ttu-id="58390-111">Werte:</span><span class="sxs-lookup"><span data-stu-id="58390-111">Values are:</span></span>  
  
-   <span data-ttu-id="58390-112">0 für Windows-Anmeldung</span><span class="sxs-lookup"><span data-stu-id="58390-112">0 for Windows login</span></span>  
  
-   <span data-ttu-id="58390-113">1 für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung</span><span class="sxs-lookup"><span data-stu-id="58390-113">1 for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login</span></span>  
  
-   <span data-ttu-id="58390-114">2 für Anmeldung als Dienst</span><span class="sxs-lookup"><span data-stu-id="58390-114">2 to log in as a service</span></span>  
  
 <span data-ttu-id="58390-115">Wenn 0 (Windows) angegeben wird, muss der Wert in der [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) -Eigenschaft auf ein entsprechendes gültiges Windows-Benutzerkonto festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="58390-115">If you specify 0 (Windows), you must set the value in the [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) property to a corresponding a valid Windows user account.</span></span>  
  
 <span data-ttu-id="58390-116">Wenn Sie 1 (SQL Server) angeben, muss der Wert von [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) einer gültigen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung entsprechen.</span><span class="sxs-lookup"><span data-stu-id="58390-116">If you specify 1 (SQL Server), make sure the value of the [DatabaseLogonAccount](configurationsetting-property-databaselogonaccount.md) corresponds to a valid [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login.</span></span>  
  
 <span data-ttu-id="58390-117">Wenn 2 (Windows-Dienst) angegeben wird, verwendet der Berichtsserver ein [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] -Konto und das Windows-Dienstkonto für den Zugriff auf die Berichtsserver-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="58390-117">If you specify 2 (Windows service), the report server uses an [!INCLUDE[vstecasp](../../includes/vstecasp-md.md)] account and the Windows service account to access the report server database.</span></span> <span data-ttu-id="58390-118">Die DatabaseLogonAccount-Eigenschaft wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="58390-118">The DatabaseLogonAccount property is ignored.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58390-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="58390-119">Requirements</span></span>  
 <span data-ttu-id="58390-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58390-120">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58390-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="58390-121">See Also</span></span>  
 [<span data-ttu-id="58390-122">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="58390-122">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
