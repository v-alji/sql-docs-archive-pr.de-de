---
title: Signieren eines Pakets mit einem digitalen Zertifikat | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- digital signatures [Integration Services]
- signing packages [Integration Services]
- signatures [Integration Services]
ms.assetid: 182b115e-0fe2-4717-8dff-183f9eb6e397
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6bd0f73d609623f882e474c96a01cd3bc0274b6b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726038"
---
# <a name="sign-a-package-by-using-a-digital-certificate"></a><span data-ttu-id="9afa0-102">Signieren eines Pakets mit einem digitalen Zertifikat</span><span class="sxs-lookup"><span data-stu-id="9afa0-102">Sign a Package by Using a Digital Certificate</span></span>
  <span data-ttu-id="9afa0-103">In diesem Thema wird beschrieben, wie ein [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket mit einem digitalen Zertifikat signiert wird.</span><span class="sxs-lookup"><span data-stu-id="9afa0-103">This topic describes how to sign an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package with a digital certificate.</span></span> <span data-ttu-id="9afa0-104">Mit einer digitalen Signatur in Verbindung mit anderen Einstellungen können Sie verhindern, dass ein ungültiges Paket geladen und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9afa0-104">You can use a digital signature, together with other settings, to prevent a package that is not valid from loading and running.</span></span>  
  
 <span data-ttu-id="9afa0-105">Bevor Sie ein [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket signieren können, müssen Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="9afa0-105">Before you can sign an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, you must do the following tasks:</span></span>  
  
-   <span data-ttu-id="9afa0-106">Erstellen oder besorgen Sie sich einen privaten Schlüssel für die Zuordnung zum Zertifikat, und speichern Sie diesen Schlüssel auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="9afa0-106">Create or obtain a private key to associate with the certificate, and store this private key on the local computer.</span></span>  
  
-   <span data-ttu-id="9afa0-107">Besorgen Sie sich ein Zertifikat zum Zwecke der Codesignierung von einer vertrauenswürdigen Zertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="9afa0-107">Obtain a certificate for the purpose of code signing from a trusted certification authority.</span></span> <span data-ttu-id="9afa0-108">Sie können eine der folgenden Methoden verwenden, um ein Zertifikat zu erhalten oder zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="9afa0-108">You can use one of the following methods to obtain or create a certificate:</span></span>  
  
    -   <span data-ttu-id="9afa0-109">Rufen Sie ein Zertifikat von einer öffentlichen, kommerziellen Zertifizierungsstelle ab, die Zertifikate ausgibt.</span><span class="sxs-lookup"><span data-stu-id="9afa0-109">Obtain a certificate from a public, commercial certification authority that issues certificates.</span></span>  
  
    -   <span data-ttu-id="9afa0-110">Rufen Sie ein Zertifikat von einem Zertifikatserver ab, mit dem eine Organisation Zertifikate intern ausstellen kann.</span><span class="sxs-lookup"><span data-stu-id="9afa0-110">Obtain a certificate from a certificate server, that enables an organization to internally issue certificates.</span></span> <span data-ttu-id="9afa0-111">Sie müssen das Stammzertifikat, mit dem das Zertifikat signiert wird, zum Speicher für **Vertrauenswürdige Stammzertifizierungsstellen** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9afa0-111">You have to add the root certificate that is used to sign the certificate to the **Trusted Root Certification Authorities** store.</span></span> <span data-ttu-id="9afa0-112">Zum Hinzufügen des Stammzertifikats verwenden Sie das Zertifikate-Snap-In für die [!INCLUDE[msCoName](../includes/msconame-md.md)] -Verwaltungskonsole (MMC).</span><span class="sxs-lookup"><span data-stu-id="9afa0-112">To add the root certificate, you can use the Certificates snap-in for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Management Console (MMC).</span></span> <span data-ttu-id="9afa0-113">Weitere Informationen finden Sie im Thema "[Certificate Services](https://go.microsoft.com/fwlink/?LinkId=100755)" (möglicherweise nur in englischer Sprache) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="9afa0-113">For more information, see the topic, "[Certificate Services](https://go.microsoft.com/fwlink/?LinkId=100755)," in the MSDN library.</span></span>  
  
    -   <span data-ttu-id="9afa0-114">Erstellen Sie ein eigenes Zertifikat nur für Testzwecke.</span><span class="sxs-lookup"><span data-stu-id="9afa0-114">Create your own certificate for testing purposes only.</span></span> <span data-ttu-id="9afa0-115">Das Certificate Creation-Tool (Makecert.exe) generiert X.509-Zertifikate für Testzwecke.</span><span class="sxs-lookup"><span data-stu-id="9afa0-115">The Certificate Creation Tool (Makecert.exe) generates X.509 certificates for testing purposes.</span></span> <span data-ttu-id="9afa0-116">Weitere Informationen finden Sie im Thema „[Certificate Creation Tool (Makecert.exe)](https://go.microsoft.com/fwlink/?LinkId=100756)“ in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="9afa0-116">For more information, see the topic, "[Certificate Creation Tool (Makecert.exe)](https://go.microsoft.com/fwlink/?LinkId=100756)," in the MSDN Library.</span></span>  
  
     <span data-ttu-id="9afa0-117">Weitere Informationen über Zertifikate finden Sie in der Onlinehilfe für das Zertifikate-Snap-In.</span><span class="sxs-lookup"><span data-stu-id="9afa0-117">For more information about certificates, see the online Help for the Certificates snap-in.</span></span> <span data-ttu-id="9afa0-118">Weitere Informationen zum Signieren von Digital Assets finden Sie im Thema "[Signing and Checking Code with Authenticode](https://go.microsoft.com/fwlink/?LinkId=78100)" (möglicherweise nur in englischer Sprache) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="9afa0-118">For more information about how to sign digital assets, see the topic, "[Signing and Checking Code with Authenticode](https://go.microsoft.com/fwlink/?LinkId=78100)," in the MSDN Library.</span></span>  
  
-   <span data-ttu-id="9afa0-119">Stellen Sie sicher, dass das Zertifikat für Codesignaturen aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="9afa0-119">Make sure that the certificate has been enabled for code signing.</span></span> <span data-ttu-id="9afa0-120">Überprüfen Sie die Eigenschaften des Zertifikats im Zertifikate-Snap-In, um festzustellen, ob ein Zertifikat zum Signieren von Code aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9afa0-120">To determine whether a certificate is enabled for code signing, review the properties of the certificate in the Certificates snap-in.</span></span>  
  
-   <span data-ttu-id="9afa0-121">Legen Sie das Zertifikat im Speicher Persönlich ab.</span><span class="sxs-lookup"><span data-stu-id="9afa0-121">Store the certificate in the Personal store.</span></span>  
  
 <span data-ttu-id="9afa0-122">Nachdem Sie die vorherigen Schritte ausgeführt haben, können Sie das folgende Verfahren verwenden, um ein Paket zu signieren.</span><span class="sxs-lookup"><span data-stu-id="9afa0-122">After you have completed the previous tasks, you can use the following procedure to sign a package.</span></span>  
  
### <a name="to-sign-a-package"></a><span data-ttu-id="9afa0-123">So signieren Sie ein Paket</span><span class="sxs-lookup"><span data-stu-id="9afa0-123">To sign a package</span></span>  
  
1.  <span data-ttu-id="9afa0-124">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt mit dem Paket, das Sie signieren möchten.</span><span class="sxs-lookup"><span data-stu-id="9afa0-124">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package to be signed.</span></span>  
  
2.  <span data-ttu-id="9afa0-125">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9afa0-125">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="9afa0-126">Klicken Sie in [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer im Menü **SSIS** auf **Digitale Signatur**.</span><span class="sxs-lookup"><span data-stu-id="9afa0-126">In [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer, on the **SSIS** menu, click **Digital Signing**.</span></span>  
  
4.  <span data-ttu-id="9afa0-127">Klicken Sie im Dialogfeld **Digitale Signatur** auf **Signieren**.</span><span class="sxs-lookup"><span data-stu-id="9afa0-127">In the **Digital Signing** dialog box, click **Sign**.</span></span>  
  
5.  <span data-ttu-id="9afa0-128">Wählen Sie im Dialogfeld **Zertifikat auswählen** ein Zertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="9afa0-128">In the **Select a Certificate** dialog box, select a certificate.</span></span>  
  
6.  <span data-ttu-id="9afa0-129">(Optional) Klicken Sie auf **Zertifikat anzeigen**, um Zertifikatinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9afa0-129">(Optional) Click **View Certificat**e to view certificate information.</span></span>  
  
7.  <span data-ttu-id="9afa0-130">Klicken Sie auf **OK** , um das Dialogfeld **Zertifikat auswählen** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="9afa0-130">Click **OK** to close the **Select a Certificate** dialog box.</span></span>  
  
8.  <span data-ttu-id="9afa0-131">Klicken Sie auf **OK** , um das Dialogfeld **Digitale Signatur** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="9afa0-131">Click **OK** to close the **Digital Signing** dialog box.</span></span>  
  
9. <span data-ttu-id="9afa0-132">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="9afa0-132">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
     <span data-ttu-id="9afa0-133">Obwohl das Paket signiert wurde, müssen Sie [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] nun so konfigurieren, dass die digitale Signatur vor dem Laden des Pakets geprüft oder verifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="9afa0-133">Although the package has been signed, you must now configure [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] to check or verify the digital signature before loading the package.</span></span> <span data-ttu-id="9afa0-134">Weitere Informationen finden Sie unter [Identifizieren der Quelle von Paketen mit digitalen Signaturen](security/identify-the-source-of-packages-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="9afa0-134">For more information, see [Identify the Source of Packages with Digital Signatures](security/identify-the-source-of-packages-with-digital-signatures.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9afa0-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9afa0-135">See Also</span></span>  
 [<span data-ttu-id="9afa0-136">Sicherheitsübersicht &#40;Integration Services&#41;</span><span class="sxs-lookup"><span data-stu-id="9afa0-136">Security Overview &#40;Integration Services&#41;</span></span>](security/security-overview-integration-services.md)  
  
  
