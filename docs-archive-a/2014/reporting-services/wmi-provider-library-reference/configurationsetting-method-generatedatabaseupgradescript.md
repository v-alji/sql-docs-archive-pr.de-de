---
title: 'GenerateDatabaseUpgradeScript-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- GenerateDatabaseUpgradeScript (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- GenerateDatabaseUpgradeScript method
ms.assetid: 88534e8e-2877-41cd-b5c2-b1d33a0fd203
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 6a619584b9f1cc095f8f624670386d388426e4a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616915"
---
# <a name="generatedatabaseupgradescript-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="6de86-102">GenerateDatabaseUpgradeScript-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="6de86-102">GenerateDatabaseUpgradeScript Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="6de86-103">Generiert ein Skript, das verwendet werden kann, um ein Upgrade der Berichtsserver-Datenbank auf das [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] -Schema durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="6de86-103">Generates a script that can be used to upgrade the report server database to the [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] schema.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6de86-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6de86-104">Syntax</span></span>  
  
```vb  
Public Sub GenerateDatabaseUpgradeScript(DatabaseName as String, _  
    ServerVersion as String, ByRef Script as String, _  
    ByRef HRESULT as Int32)  
```  
  
```csharp  
public void GenerateDatabaseUpgradeScript (string DatabaseName,   
    string ServerVersion, out string Script,   
    out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6de86-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6de86-105">Parameters</span></span>  
 <span data-ttu-id="6de86-106">*Databasename*</span><span class="sxs-lookup"><span data-stu-id="6de86-106">*Databasename*</span></span>  
 <span data-ttu-id="6de86-107">Eine Zeichenfolge, die den Namen der zu aktualisierenden Berichtsserver-Datenbank enthält</span><span class="sxs-lookup"><span data-stu-id="6de86-107">A string containing the name of the report server database to upgrade.</span></span>  
  
 <span data-ttu-id="6de86-108">*ServerVersion*</span><span class="sxs-lookup"><span data-stu-id="6de86-108">*ServerVersion*</span></span>  
 <span data-ttu-id="6de86-109">Eine Zeichenfolge, die die Version des Berichtsservers enthält</span><span class="sxs-lookup"><span data-stu-id="6de86-109">A string containing the version of the report server.</span></span>  
  
 <span data-ttu-id="6de86-110">*Skript*</span><span class="sxs-lookup"><span data-stu-id="6de86-110">*Script*</span></span>  
 <span data-ttu-id="6de86-111">[out] Eine Zeichenfolge, die das generierte SQL-Skript enthält</span><span class="sxs-lookup"><span data-stu-id="6de86-111">[out] A string containing the generated SQL script.</span></span>  
  
 <span data-ttu-id="6de86-112">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="6de86-112">*HRESULT*</span></span>  
 <span data-ttu-id="6de86-113">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="6de86-113">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6de86-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6de86-114">Return Value</span></span>  
 <span data-ttu-id="6de86-115">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6de86-115">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="6de86-116">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="6de86-116">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="6de86-117">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="6de86-117">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6de86-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6de86-118">Remarks</span></span>  
 <span data-ttu-id="6de86-119">Das generierte Skript unterstützt [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)]und [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6de86-119">The generated script supports [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)], and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6de86-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6de86-120">Requirements</span></span>  
 <span data-ttu-id="6de86-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6de86-121">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6de86-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6de86-122">See Also</span></span>  
 [<span data-ttu-id="6de86-123">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="6de86-123">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
