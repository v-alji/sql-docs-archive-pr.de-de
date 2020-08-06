---
title: Protokolle für MSSQLSERVER-Eigenschaften (Registerkarte „Zertifikat“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.computermgr.cert.general.f1
helpviewer_keywords:
- MSSQLSERVER property protocols
ms.assetid: 776addd6-25f3-4875-9a71-064035787090
author: stevestein
ms.author: sstein
ms.openlocfilehash: 020d33eba7621f877f8622ca89dbd26a071f16a8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722094"
---
# <a name="protocols-for-mssqlserver-properties-certificate-tab"></a><span data-ttu-id="ecc4f-102">Protokolle für MSSQLSERVER-Eigenschaften (Registerkarte Zertifikat)</span><span class="sxs-lookup"><span data-stu-id="ecc4f-102">Protocols for MSSQLSERVER Properties (Certificate Tab)</span></span>
  <span data-ttu-id="ecc4f-103">Im Dialogfeld **Protocols for MSSQLSERVER Properties** (Protokolle für MSSQLSERVER-Eigenschaften) auf der Registerkarte **Zertifikat** können Sie ein Zertifikat für [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auswählen oder sich die Eigenschaften eines Zertifikats ansehen.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-103">Use the **Certificate** tab on the **Protocols for MSSQLSERVER Properties** dialog box to select a certificate for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], or to view the properties of a certificate.</span></span> <span data-ttu-id="ecc4f-104">Alle Felder sind leer, bis ein Zertifikat ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-104">All fields are blank until a certificate is selected.</span></span>  
  
 <span data-ttu-id="ecc4f-105">Zertifikate werden lokal für diesen Benutzer auf dem Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-105">Certificates are stored locally for the users on the computer.</span></span> <span data-ttu-id="ecc4f-106">Um ein Zertifikat zum Verwenden durch [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zu laden, müssen Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager unter dem gleichen Benutzerkonto ausführen wie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienst.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-106">To load a certificate for use by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must be running [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager under the same user account as the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] service.</span></span>  
  
## <a name="page-header"></a><span data-ttu-id="ecc4f-107">Seitenheader</span><span class="sxs-lookup"><span data-stu-id="ecc4f-107">Page Header</span></span>  
 <span data-ttu-id="ecc4f-108">**Ansicht**</span><span class="sxs-lookup"><span data-stu-id="ecc4f-108">**View**</span></span>  
 <span data-ttu-id="ecc4f-109">Bietet Zugriff auf zusätzliche Details auf dem Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-109">Provides access to additional details on the certificate.</span></span> <span data-ttu-id="ecc4f-110">Steht erst dann zur Verfügung, wenn ein Zertifikat im Dialogfeld **Zertifikat** ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-110">Not available until a certificate is selected in the **Certificate** box.</span></span> <span data-ttu-id="ecc4f-111">Weitere Informationen zu Zertifikatdetails finden Sie in der [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-111">For additional information on certificate details, see your [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows documentation.</span></span>  
  
 <span data-ttu-id="ecc4f-112">**Clear**</span><span class="sxs-lookup"><span data-stu-id="ecc4f-112">**Clear**</span></span>  
 <span data-ttu-id="ecc4f-113">Entfernt die Auswahl aus dem Dialogfeld **Zertifikat** .</span><span class="sxs-lookup"><span data-stu-id="ecc4f-113">Removes the selection from the **Certificate** box.</span></span>  
  
 <span data-ttu-id="ecc4f-114">**Certificate**</span><span class="sxs-lookup"><span data-stu-id="ecc4f-114">**Certificate**</span></span>  
 <span data-ttu-id="ecc4f-115">Durch den Sicherheitsanbieter festgelegter Name des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-115">Name of certificate as determined by security provider.</span></span> <span data-ttu-id="ecc4f-116">Wählen Sie ein Zertifikat aus, um die Details im Eigenschaftenraster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-116">Select a certificate to see the details in the properties grid.</span></span>  
  
## <a name="options"></a><span data-ttu-id="ecc4f-117">Tastatur</span><span class="sxs-lookup"><span data-stu-id="ecc4f-117">Options</span></span>  
 <span data-ttu-id="ecc4f-118">Ablaufdatum</span><span class="sxs-lookup"><span data-stu-id="ecc4f-118">Expiration Date</span></span>  
 <span data-ttu-id="ecc4f-119">Das Enddatum für den Zeitraum, in dem das Zertifikat gültig ist.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-119">The final date for the period in which the certificate is valid.</span></span>  
  
 <span data-ttu-id="ecc4f-120">Anzeigename</span><span class="sxs-lookup"><span data-stu-id="ecc4f-120">Friendly Name</span></span>  
 <span data-ttu-id="ecc4f-121">Ein allgemein gebräuchlicher Name für das Individuum oder die Zertifizierungsstelle, dem oder der das Zertifikat ausgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-121">A friendly or common name for the individual or certification authority to whom the certificate is issued.</span></span>  
  
 <span data-ttu-id="ecc4f-122">Ausgestellt von</span><span class="sxs-lookup"><span data-stu-id="ecc4f-122">Issued By</span></span>  
 <span data-ttu-id="ecc4f-123">Informationen in Bezug auf die Zertifizierungsstelle, die das Zertifikat ausgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-123">Information regarding the certification authority that issued the certificate.</span></span>  
  
 <span data-ttu-id="ecc4f-124">Ausgestellt an</span><span class="sxs-lookup"><span data-stu-id="ecc4f-124">Issued To</span></span>  
 <span data-ttu-id="ecc4f-125">Informationen zum Empfänger des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="ecc4f-125">Information regarding the recipient of the certificate.</span></span>  
  
  
