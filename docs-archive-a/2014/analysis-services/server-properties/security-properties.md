---
title: Sicherheitseigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- security [Analysis Services], properties
- SecurityPackageList property
- BuiltinAdminsAreServerAdmins property
- DisableClientImpersonation property
- ErrorMessageMode property
- RequiredProtectionLevel property
- ServiceAccountIsServerAdmin property
- RequireClientAuthentication property
ms.assetid: 2fc7fe10-0cbb-49ac-aa8c-8ec3f7a7705f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 20133554835803908a340c5369eb66e86b119d72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617303"
---
# <a name="security-properties"></a><span data-ttu-id="d891a-102">Sicherheitseigenschaften</span><span class="sxs-lookup"><span data-stu-id="d891a-102">Security Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="d891a-103">werden die in der folgenden Tabelle aufgeführten Sicherheitseigenschaften des Servers aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="d891a-103">supports the security server properties listed in the following table.</span></span> <span data-ttu-id="d891a-104">Weitere Informationen zu zusätzlichen Servereigenschaften und zum Festlegen dieser Eigenschaften finden Sie unter [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="d891a-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="d891a-105">**Gilt für:** mehrdimensionalen und Tabellenservermodus</span><span class="sxs-lookup"><span data-stu-id="d891a-105">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d891a-106">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d891a-106">Properties</span></span>  
 `RequireClientAuthentication`  
 <span data-ttu-id="d891a-107">Eine boolesche Eigenschaft, die anzeigt, ob eine Client-Authentifizierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d891a-107">A Boolean property that indicates whether client authentication is required.</span></span>  
  
 <span data-ttu-id="d891a-108">Der Standardwert für diese Eigenschaft ist auf True festgelegt, was anzeigt, dass eine Client-Authentifizierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d891a-108">The default value for this property is True, which indicates that client authentication is required.</span></span>  
  
 `SecurityPackageList`  
 <span data-ttu-id="d891a-109">Eine Zeichenfolgeneigenschaft, die eine Liste mit durch Trennzeichen getrennten SSPI-Paketen enthält, die vom Server zur Client-Authentifizierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d891a-109">A string property that contains a comma-separated list of SSPI packages used by server for client authentication.</span></span>  
  
 `DisableClientImpersonation`  
 <span data-ttu-id="d891a-110">Eine boolesche Eigenschaft, die anzeigt, ob Clientidentitätswechsel (z. B. für gespeicherte Prozeduren) deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="d891a-110">A Boolean property that indicates whether client impersonation (for example, from stored procedures) is disabled.</span></span>  
  
 <span data-ttu-id="d891a-111">Der Standardwert für diese Eigenschaft ist auf False festgelegt, was anzeigt, dass Clientidentitätswechsel aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="d891a-111">The default value for this property is False, which indicates that client impersonation is enabled.</span></span>  
  
 `BuiltinAdminsAreServerAdmins`  
 <span data-ttu-id="d891a-112">Eine boolesche Eigenschaft, die anzeigt, ob Mitglieder der Gruppe Administratoren auf dem lokalen Computer Administratoren von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] sind.</span><span class="sxs-lookup"><span data-stu-id="d891a-112">A Boolean property that indicates whether members of the local machine administrators group are [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] administrators.</span></span>  
  
 `ServiceAccountIsServerAdmin`  
 <span data-ttu-id="d891a-113">Eine boolesche Eigenschaft, die anzeigt, ob das Dienstkonto ein Serveradministrator ist.</span><span class="sxs-lookup"><span data-stu-id="d891a-113">A Boolean property that indicates whether the service account is a server administrator.</span></span>  
  
 <span data-ttu-id="d891a-114">Der Standardwert für diese Eigenschaft ist auf True festgelegt, was anzeigt, dass das Dienstkonto ein Serveradministrator ist.</span><span class="sxs-lookup"><span data-stu-id="d891a-114">The default value for this property is True, which indicates that the service account is a server administrator.</span></span>  
  
 `ErrorMessageMode`  
 <span data-ttu-id="d891a-115">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="d891a-115">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `DataProtection\ RequiredProtectionLevel`  
 <span data-ttu-id="d891a-116">Eine ganze 32-Bit-Zahl mit Vorzeichen, die die erforderliche Schutzebene für alle Clientanforderungen definiert.</span><span class="sxs-lookup"><span data-stu-id="d891a-116">A signed 32-bit integer property that defines the required protection level for all client requests.</span></span> <span data-ttu-id="d891a-117">Diese Eigenschaft hat einen der in der folgenden Tabelle aufgeführten Werte.</span><span class="sxs-lookup"><span data-stu-id="d891a-117">This property has one of the values listed in the following table.</span></span>  
  
|<span data-ttu-id="d891a-118">Wert</span><span class="sxs-lookup"><span data-stu-id="d891a-118">Value</span></span>|<span data-ttu-id="d891a-119">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d891a-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d891a-120">*0*</span><span class="sxs-lookup"><span data-stu-id="d891a-120">*0*</span></span>|<span data-ttu-id="d891a-121">Keine, Klartext ist zulässig</span><span class="sxs-lookup"><span data-stu-id="d891a-121">None, clear text allowed.</span></span>|  
|<span data-ttu-id="d891a-122">*1*</span><span class="sxs-lookup"><span data-stu-id="d891a-122">*1*</span></span>|<span data-ttu-id="d891a-123">(Standard) Verschlüsselung erforderlich, keine Klartextprotokollierung</span><span class="sxs-lookup"><span data-stu-id="d891a-123">(Default) Encryption required, no clear-text logging.</span></span>|  
|<span data-ttu-id="d891a-124">*2*</span><span class="sxs-lookup"><span data-stu-id="d891a-124">*2*</span></span>|<span data-ttu-id="d891a-125">Klartextanforderungen zulässig, aber nur mit Signaturen (schwächer als die Verschlüsselung)</span><span class="sxs-lookup"><span data-stu-id="d891a-125">Clear-text requests allowed but only with signatures (weaker protection than encryption).</span></span>|  
  
 `AdministrativeDataProtection\ RequiredProtectionLevel`  
 <span data-ttu-id="d891a-126">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="d891a-126">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d891a-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d891a-127">See Also</span></span>  
 <span data-ttu-id="d891a-128">[Konfigurieren von Server Eigenschaften in Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="d891a-128">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="d891a-129">Bestimmen des Servermodus einer Analysis Services-Instanz</span><span class="sxs-lookup"><span data-stu-id="d891a-129">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
