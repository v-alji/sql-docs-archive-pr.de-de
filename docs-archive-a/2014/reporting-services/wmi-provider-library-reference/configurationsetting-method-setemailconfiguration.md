---
title: 'SetEmailConfiguration-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetEmailConfiguration (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetEmailConfiguration method
ms.assetid: b40a2224-2c90-4d32-892f-1fe73a0591ca
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 19068d7d7fff8c31c455ef76e8d2c2caa26b743f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722382"
---
# <a name="setemailconfiguration-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="e948d-102">SetEmailConfiguration-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="e948d-102">SetEmailConfiguration Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="e948d-103">Konfiguriert die E-Mail-Übermittlungserweiterung, die vom Berichtsserver zum Senden von E-Mails verwendet wird</span><span class="sxs-lookup"><span data-stu-id="e948d-103">Configures the e-mail delivery extension used by the report server to send e-mail.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e948d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e948d-104">Syntax</span></span>  
  
```vb  
Public Sub SetEmailConfiguration(ByVal SendUsingSMTPServer As Boolean, _  
    ByVal SMTPServer As String, ByVal SenderEmailAddress As String, _  
    ByRef HRESULT As Int32)  
```  
  
```csharp  
public void SetEmailConfiguration (Boolean SendUsingSMTPServer,   
   string SMTPServer, string SenderEmailAddress,   
   out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e948d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e948d-105">Parameters</span></span>  
 <span data-ttu-id="e948d-106">*SendUsingSMTPServer*</span><span class="sxs-lookup"><span data-stu-id="e948d-106">*SendUsingSMTPServer*</span></span>  
 <span data-ttu-id="e948d-107">Ein boolescher Wert, der angibt, ob der Server zum Senden von E-Mails den SMTP-Server verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="e948d-107">A Boolean value indicating whether the server is to use the SMTP server to send email.</span></span> <span data-ttu-id="e948d-108">Dieser Wert kann nur auf true festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="e948d-108">This value can only be set to true.</span></span> <span data-ttu-id="e948d-109">Der Standardwert ist „false“.</span><span class="sxs-lookup"><span data-stu-id="e948d-109">Default value is false.</span></span>  
  
 <span data-ttu-id="e948d-110">*SMTPServer*</span><span class="sxs-lookup"><span data-stu-id="e948d-110">*SMTPServer*</span></span>  
 <span data-ttu-id="e948d-111">Eine Zeichenfolge, die den Namen oder die IP-Adresse eines SMTP-Servers enthält</span><span class="sxs-lookup"><span data-stu-id="e948d-111">A string containing the name or IP address of an SMTP server.</span></span>  
  
 <span data-ttu-id="e948d-112">*SenderEmailAddress*</span><span class="sxs-lookup"><span data-stu-id="e948d-112">*SenderEmailAddress*</span></span>  
 <span data-ttu-id="e948d-113">Die im Feld Von: verwendete E-Mail-Adresse für vom Berichtsserver gesendete E-Mails</span><span class="sxs-lookup"><span data-stu-id="e948d-113">The e-mail address used in the 'From:' field for e-mails sent from the report server.</span></span>  
  
 <span data-ttu-id="e948d-114">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="e948d-114">*HRESULT*</span></span>  
 <span data-ttu-id="e948d-115">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="e948d-115">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e948d-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e948d-116">Return Value</span></span>  
 <span data-ttu-id="e948d-117">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e948d-117">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="e948d-118">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="e948d-118">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="e948d-119">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="e948d-119">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e948d-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e948d-120">Remarks</span></span>  
 <span data-ttu-id="e948d-121">Wenn der *SendUsingSMTPServer* -Parameter auf festgelegt ist `true` , wird der **SendUsing** -Eintrag in der Berichts Server-Konfigurationsdatei auf 1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e948d-121">When the *SendUsingSMTPServer* parameter is set to `true`, the **SendUsing** entry in the report server configuration file is set to 1.</span></span> <span data-ttu-id="e948d-122">Wenn *SendUsingSMTPServer* auf festgelegt ist `false` , wird der **SendUsing** -Eintrag nicht konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="e948d-122">When *SendUsingSMTPServer* is set to `false`, the **SendUsing** entry is not configured.</span></span>  
  
 <span data-ttu-id="e948d-123">Diese Methode gibt Benutzern keine Möglichkeit, den **SendUsing** -Eintrag in der Berichtsserver-Konfigurationsdatei auf einen anderen Wert als 1 festzulegen.</span><span class="sxs-lookup"><span data-stu-id="e948d-123">This method does not provide a way for users to set the **SendUsing** entry in the report server configuration file to a value other than 1.</span></span> <span data-ttu-id="e948d-124">Sie müssen die Konfigurationsdateien manuell bearbeiten, um den Berichtsserver für eine andere Option als SMTP-Mail zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e948d-124">To configure the report server for anything other than SMTP mail, you must edit the configuration file manually.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e948d-125">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e948d-125">Requirements</span></span>  
 <span data-ttu-id="e948d-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e948d-126">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e948d-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e948d-127">See Also</span></span>  
 [<span data-ttu-id="e948d-128">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="e948d-128">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
