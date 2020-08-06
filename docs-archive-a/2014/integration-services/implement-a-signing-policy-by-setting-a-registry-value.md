---
title: Implementieren einer Signatur Richtlinie durch Festlegen eines Registrierungs Werts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- signing policies [Integration Services]
ms.assetid: 64f6966f-2292-401f-acb1-2ccb5aee484a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1e844b65df5b45f212554f7583f4e4b327b740e0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609324"
---
# <a name="implement-a-signing-policy-by-setting-a-registry-value"></a><span data-ttu-id="c062a-102">Implementieren einer Signaturrichtlinie durch Festlegen eines Registrierungswerts</span><span class="sxs-lookup"><span data-stu-id="c062a-102">Implement a Signing Policy by Setting a Registry Value</span></span>
  <span data-ttu-id="c062a-103">Sie können einen optionalen Registrierungswert zum Verwalten einer Organisationsrichtlinie verwenden, um signierte und nicht signierte Pakete zu laden.</span><span class="sxs-lookup"><span data-stu-id="c062a-103">You can use an optional registry value to manage an organization's policy for loading signed or unsigned packages.</span></span> <span data-ttu-id="c062a-104">Wenn Sie diesen Registrierungswert verwenden, müssen Sie ihn auf jedem Computer erstellen, auf dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Pakete ausgeführt werden und auf dem Sie die Richtlinie durchsetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="c062a-104">If you use this registry value, you must create this registry value on each computer on which [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages will run and on which you want to enforce the policy.</span></span> <span data-ttu-id="c062a-105">Nachdem der Registrierungswert festgelegt wurde, überprüft oder verifiziert [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] die Signaturen vor dem Laden der Pakete.</span><span class="sxs-lookup"><span data-stu-id="c062a-105">After the registry value has been set, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] will check or verify the signatures before loading packages.</span></span>  
  
 <span data-ttu-id="c062a-106">Das Verfahren in diesem Thema beschreibt, wie Sie den optionalen `BlockedSignatureStates`-DWORD-Wert zum HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS-Registrierungsschlüssel hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="c062a-106">This procedure in this topic describes how to add the optional `BlockedSignatureStates` DWORD value to the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS registry key.</span></span> <span data-ttu-id="c062a-107">Der Datenwert in `BlockedSignatureStates` bestimmt, ob ein Paket blockiert werden soll, wenn es eine nicht vertrauenswürdige Signatur, eine ungültige Signatur oder keine Signatur aufweist.</span><span class="sxs-lookup"><span data-stu-id="c062a-107">The data value in `BlockedSignatureStates` determines whether a package should be blocked if it has an untrusted signature, has an invalid signature, or is unsigned.</span></span> <span data-ttu-id="c062a-108">Hinsichtlich des Status der zum Signieren von Paketen verwendeten Signaturen werden für den Registrierungswert `BlockedSignatureStates` folgende Definitionen verwendet:</span><span class="sxs-lookup"><span data-stu-id="c062a-108">With regard to the status of signatures used to sign packages, the `BlockedSignatureStates` registry value uses the following definitions:</span></span>  
  
-   <span data-ttu-id="c062a-109">Eine *gültige Signatur* ist eine Signatur, die erfolgreich gelesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c062a-109">A *valid signature* is one that can be read successfully.</span></span>  
  
-   <span data-ttu-id="c062a-110">Eine *ungültige Signatur* ist eine Signatur, bei der die entschlüsselte Prüfsumme (der mit einem privaten Schlüssel verschlüsselte unidirektionale Hash des Paketcodes) nicht der entschlüsselten Prüfsumme entspricht, die während des Ladevorgangs von [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paketen berechnet wird.</span><span class="sxs-lookup"><span data-stu-id="c062a-110">An *invalid signature* is one for which the decrypted checksum (the one-way hash of the package code encrypted by a private key) does not match the decrypted checksum that is calculated as part of the process of loading [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages.</span></span>  
  
-   <span data-ttu-id="c062a-111">Eine *vertrauenswürdige Signatur* ist eine Signatur, die mithilfe eines von einer vertrauenswürdigen Stammzertifizierungsstelle signierten digitalen Zertifikats erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c062a-111">A *trusted signature* is one that is created by using a digital certificate signed by a Trusted Root Certification Authority.</span></span> <span data-ttu-id="c062a-112">Für diese Einstellung ist es nicht erforderlich, dass der Unterzeichner in der Liste vertrauenswürdiger Herausgeber des Benutzers vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c062a-112">This setting does not require the signer to be found in the user's list of Trusted Publishers.</span></span>  
  
-   <span data-ttu-id="c062a-113">Eine *nicht vertrauenswürdige Signatur* ist eine Signatur, bei der nicht überprüft werden kann, ob sie von einer vertrauenswürdigen Stammzertifizierungsstelle ausgestellt wurde, oder eine Signatur, die nicht aktuell ist.</span><span class="sxs-lookup"><span data-stu-id="c062a-113">An *untrusted signature* is one that cannot be verified as issued by a Trusted Root Certification Authority, or a signature that is not current.</span></span>  
  
 <span data-ttu-id="c062a-114">In der folgenden Tabelle werden die gültigen Werte der DWORD-Daten und ihre verbundenen Richtlinien aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c062a-114">The following table lists the valid values of the DWORD data and their associated policy.</span></span>  
  
|<span data-ttu-id="c062a-115">Wert</span><span class="sxs-lookup"><span data-stu-id="c062a-115">Value</span></span>|<span data-ttu-id="c062a-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c062a-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c062a-117">0</span><span class="sxs-lookup"><span data-stu-id="c062a-117">0</span></span>|<span data-ttu-id="c062a-118">Keine administrative Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="c062a-118">No administrative restriction.</span></span>|  
|<span data-ttu-id="c062a-119">1</span><span class="sxs-lookup"><span data-stu-id="c062a-119">1</span></span>|<span data-ttu-id="c062a-120">Blockieren von ungültigen Signaturen.</span><span class="sxs-lookup"><span data-stu-id="c062a-120">Block invalid signatures.</span></span><br /><br /> <span data-ttu-id="c062a-121">Bei dieser Einstellung werden nicht signierte Pakete nicht blockiert.</span><span class="sxs-lookup"><span data-stu-id="c062a-121">This setting does not block unsigned packages.</span></span>|  
|<span data-ttu-id="c062a-122">2</span><span class="sxs-lookup"><span data-stu-id="c062a-122">2</span></span>|<span data-ttu-id="c062a-123">Blockieren von ungültigen und nicht vertrauenswürdigen Signaturen.</span><span class="sxs-lookup"><span data-stu-id="c062a-123">Block invalid and untrusted signatures.</span></span><br /><br /> <span data-ttu-id="c062a-124">Bei dieser Einstellung werden zwar nicht signierte Pakete nicht blockiert, selbst generierte Signaturen werden jedoch blockiert.</span><span class="sxs-lookup"><span data-stu-id="c062a-124">This setting does not block unsigned packages, but blocks self-generated signatures.</span></span>|  
|<span data-ttu-id="c062a-125">3</span><span class="sxs-lookup"><span data-stu-id="c062a-125">3</span></span>|<span data-ttu-id="c062a-126">Blockieren von ungültigen und nicht vertrauenswürdigen Signaturen und nicht signierten Paketen.</span><span class="sxs-lookup"><span data-stu-id="c062a-126">Block invalid and untrusted signatures and unsigned packages</span></span><br /><br /> <span data-ttu-id="c062a-127">Bei dieser Einstellung werden auch selbst generierte Signaturen blockiert.</span><span class="sxs-lookup"><span data-stu-id="c062a-127">This setting also blocks self-generated signatures.</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="c062a-128">Die empfohlene Einstellung für `BlockedSignatureStates` ist 3.</span><span class="sxs-lookup"><span data-stu-id="c062a-128">The recommended setting for `BlockedSignatureStates` is 3.</span></span> <span data-ttu-id="c062a-129">Diese Einstellung bietet den besten Schutz vor nicht signierten Paketen oder Signaturen, die entweder ungültig oder nicht vertrauenswürdig sind.</span><span class="sxs-lookup"><span data-stu-id="c062a-129">This setting provides the greatest protection against unsigned packages or signatures that are either not valid or untrusted.</span></span> <span data-ttu-id="c062a-130">Die empfohlene Einstellung eignet sich jedoch möglicherweise nicht in allen Fällen.</span><span class="sxs-lookup"><span data-stu-id="c062a-130">However, the recommended setting may not be appropriate in all circumstances.</span></span> <span data-ttu-id="c062a-131">Weitere Informationen zum Signieren von Digital Assets finden Sie im Thema "[Introduction to Code Signing](https://go.microsoft.com/fwlink/?LinkId=51414)" (in Englisch) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="c062a-131">For more information about signing digital assets, see the topic, "[Introduction to Code Signing](https://go.microsoft.com/fwlink/?LinkId=51414)," in the MSDN Library.</span></span>  
  
### <a name="to-implement-a-signing-policy-for-packages"></a><span data-ttu-id="c062a-132">So implementieren Sie eine Signaturrichtlinie für ein Paket</span><span class="sxs-lookup"><span data-stu-id="c062a-132">To implement a signing policy for packages</span></span>  
  
1.  <span data-ttu-id="c062a-133">Klicken Sie im Menü **Start** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c062a-133">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="c062a-134">Geben Sie im Dialogfeld Ausführen ein `Regedit` , und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c062a-134">In the Run dialog box, type `Regedit`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="c062a-135">Suchen Sie den Schlüssel HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS.</span><span class="sxs-lookup"><span data-stu-id="c062a-135">Locate the registry key, HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\100\SSIS.</span></span>  
  
4.  <span data-ttu-id="c062a-136">Klicken Sie mit der rechten Maustaste auf **MSDTS**, zeigen Sie auf **Neu**, und klicken Sie anschließend auf **DWORD-Wert**.</span><span class="sxs-lookup"><span data-stu-id="c062a-136">Right-click **MSDTS**, point to **New**, and then click **DWORD Value**.</span></span>  
  
5.  <span data-ttu-id="c062a-137">Aktualisieren Sie den Namen des neuen Werts auf `BlockedSignatureStates`.</span><span class="sxs-lookup"><span data-stu-id="c062a-137">Update the name of the new value to `BlockedSignatureStates`.</span></span>  
  
6.  <span data-ttu-id="c062a-138">Klicken Sie mit der rechten Maustaste auf `BlockedSignatureStates` **ändern**.</span><span class="sxs-lookup"><span data-stu-id="c062a-138">Right-click `BlockedSignatureStates` and click **Modify**.</span></span>  
  
7.  <span data-ttu-id="c062a-139">Geben Sie im Dialogfeld **DWORD-Wert bearbeiten** den Wert 0, 1, 2, oder 3 ein.</span><span class="sxs-lookup"><span data-stu-id="c062a-139">In the **Edit DWORD Value** dialog box, type the value 0, 1, 2, or 3.</span></span>  
  
8.  <span data-ttu-id="c062a-140">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c062a-140">Click **OK**.</span></span>  
  
9. <span data-ttu-id="c062a-141">Klicken Sie im Menü **Datei** auf **Beenden**.</span><span class="sxs-lookup"><span data-stu-id="c062a-141">On the **File** menu, click **Exit**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c062a-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c062a-142">See Also</span></span>  
 <span data-ttu-id="c062a-143">[Sicherheitsübersicht &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="c062a-143">[Security Overview &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span></span>  
 [<span data-ttu-id="c062a-144">Identifizieren der Quelle von Paketen mit digitalen Signaturen</span><span class="sxs-lookup"><span data-stu-id="c062a-144">Identify the Source of Packages with Digital Signatures</span></span>](security/identify-the-source-of-packages-with-digital-signatures.md)  
  
  
