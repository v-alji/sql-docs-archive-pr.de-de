---
title: GenerateDatabaseCreationScript-Methode (WMI-MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- GenerateDatabaseCreationScript (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- GenerateDatabaseCreationScript method
ms.assetid: 25232dc7-00fe-4cd1-8a1c-7e36d552de00
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5e798aa25bec1cc478a6ec2cbdd0c21f44fa8215
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616918"
---
# <a name="generatedatabasecreationscript-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="2d1c6-102">GenerateDatabaseCreationScript-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="2d1c6-102">GenerateDatabaseCreationScript Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="2d1c6-103">Generiert ein SQL-Skript, mit dem eine Berichtsserver-Datenbank erstellt werden kann</span><span class="sxs-lookup"><span data-stu-id="2d1c6-103">Generates a SQL Script that can be used to create a report server database.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d1c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d1c6-104">Syntax</span></span>  
  
```vb  
Public Sub GenerateDatabaseCreationScript(ByVal DatabaseName As String, _  
    ByVal Lcid As Int32, ByVal IsSharePointMode As Boolean, ByRef Script As String, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void GenerateDatabaseCreationScript(string DatabaseName, Int32 Lcid,   
    Boolean IsSharePointMode, out string Script, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2d1c6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2d1c6-105">Parameters</span></span>  
 <span data-ttu-id="2d1c6-106">*Databasename*</span><span class="sxs-lookup"><span data-stu-id="2d1c6-106">*Databasename*</span></span>  
 <span data-ttu-id="2d1c6-107">Eine Zeichenfolge, die den Namen der zu erstellenden Berichtsserver-Datenbank enthält</span><span class="sxs-lookup"><span data-stu-id="2d1c6-107">A string containing the name of the report server database to create.</span></span>  
  
 <span data-ttu-id="2d1c6-108">*Lcid*</span><span class="sxs-lookup"><span data-stu-id="2d1c6-108">*Lcid*</span></span>  
 <span data-ttu-id="2d1c6-109">Zur Lokalisierung von Rollennamen verwendeter Wert.</span><span class="sxs-lookup"><span data-stu-id="2d1c6-109">Value used for localization of role names.</span></span>  
  
 <span data-ttu-id="2d1c6-110">*IsSharePointMode*</span><span class="sxs-lookup"><span data-stu-id="2d1c6-110">*IsSharePointMode*</span></span>  
 <span data-ttu-id="2d1c6-111">Gibt an, ob die Datenbank im einheitlichen Modus oder im SharePoint-Modus erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2d1c6-111">Indicates whether to create database in native mode or SharePoint mode.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2d1c6-112">Ab [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)] wird *issharepointmode* = `True` nicht unterstützt, da im SharePoint-Modus [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] ein gemeinsamer SharePoint-Dienst ist und nicht vom WMI-Anbieter gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="2d1c6-112">Beginning in [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], *IsSharePointMode*=`True` is not supported because in SharePoint mode, [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] is a SharePoint shared service and is not controlled by the WMI provider.</span></span> <span data-ttu-id="2d1c6-113">Es wird empfohlen, diesen Parameter immer auf `False` festzulegen.</span><span class="sxs-lookup"><span data-stu-id="2d1c6-113">You should always set this parameter to `False`.</span></span>  
  
 <span data-ttu-id="2d1c6-114">*Skript*</span><span class="sxs-lookup"><span data-stu-id="2d1c6-114">*Script*</span></span>  
 <span data-ttu-id="2d1c6-115">[out] Eine Zeichenfolge, die das generierte SQL-Skript enthält</span><span class="sxs-lookup"><span data-stu-id="2d1c6-115">[out] A string containing the generated SQL script.</span></span>  
  
 <span data-ttu-id="2d1c6-116">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="2d1c6-116">*HRESULT*</span></span>  
 <span data-ttu-id="2d1c6-117">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="2d1c6-117">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d1c6-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2d1c6-118">Return Value</span></span>  
 <span data-ttu-id="2d1c6-119">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2d1c6-119">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="2d1c6-120">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="2d1c6-120">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="2d1c6-121">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="2d1c6-121">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d1c6-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2d1c6-122">Remarks</span></span>  
 <span data-ttu-id="2d1c6-123">Diese Methode generiert ein SQL-Skript, mit dem Berichtsserver-Datenbanken für die Version des Berichtsservers erstellt werden, zu dem derzeit eine Verbindung besteht.</span><span class="sxs-lookup"><span data-stu-id="2d1c6-123">This method generates an SQL script that creates report server databases for the version of the report server currently connected to.</span></span>  
  
 <span data-ttu-id="2d1c6-124">Der im Parameter *DatabaseName* angegebene Wert muss den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Benennungskonventionen für Datenbanken entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2d1c6-124">The value supplied in the *DatabaseName* parameter must conform to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database naming conventions.</span></span>  
  
 <span data-ttu-id="2d1c6-125">Die Methode überprüft beim Generieren des Skripts nicht das Vorhandensein der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2d1c6-125">The method does not check the existence of the database when generating the script.</span></span>  
  
 <span data-ttu-id="2d1c6-126">Beim Generieren des Skripts überprüft diese Methode nicht, ob die Berichtsserver-Datenbank vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2d1c6-126">This method does not check for the existence of the report server database when generating the script.</span></span>  
  
 <span data-ttu-id="2d1c6-127">Das generierte Skript unterstützt [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005 und [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2d1c6-127">The generated script supports [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 2005, and [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d1c6-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2d1c6-128">Requirements</span></span>  
 <span data-ttu-id="2d1c6-129">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d1c6-129">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d1c6-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d1c6-130">See Also</span></span>  
 [<span data-ttu-id="2d1c6-131">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="2d1c6-131">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
