---
title: Erweiterbare Schlüsselverwaltung mit Azure Key Vault (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- EKM, with key vault
- TDE, EKM and key vault
- Extensible Key Management with key vault
- Key Management with key vault
- Transparent Data Encryption, using EKM and key vault
ms.assetid: 3efdc48a-8064-4ea6-a828-3fbf758ef97c
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 0e4bbc4f0c371c927988e6b91fdbf47307ad9d3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726853"
---
# <a name="extensible-key-management-using-azure-key-vault-sql-server"></a><span data-ttu-id="cb045-102">Erweiterbare Schlüsselverwaltung mit Azure Key Vault (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="cb045-102">Extensible Key Management Using Azure Key Vault (SQL Server)</span></span>
  <span data-ttu-id="cb045-103">Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector für [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure Key Vault ermöglicht [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] die Verschlüsselung, um den Azure Key Vault-Dienst als [erweiterbare Schlüsselverwaltung &#40;EKM-&#41;](extensible-key-management-ekm.md) Anbieter zum Schutz seiner Verschlüsselungsschlüssel zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="cb045-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure Key Vault enables [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption to leverage the Azure Key Vault service as an [Extensible Key Management &#40;EKM&#41;](extensible-key-management-ekm.md) provider to protect its encryption keys.</span></span>

 <span data-ttu-id="cb045-104">In diesem Thema:</span><span class="sxs-lookup"><span data-stu-id="cb045-104">Included in this topic:</span></span>

-   [<span data-ttu-id="cb045-105">Verwendungsmöglichkeiten für erweiterbare Schlüsselverwaltung</span><span class="sxs-lookup"><span data-stu-id="cb045-105">Uses of EKM</span></span>](#Uses)

-   [<span data-ttu-id="cb045-106">Schritt 1: Einrichten des Schlüsseltresors für die Verwendung durch SQL Server</span><span class="sxs-lookup"><span data-stu-id="cb045-106">Step 1: Setting up the Key Vault for use by SQL Server</span></span>](#Step1)

-   [<span data-ttu-id="cb045-107">Schritt 2: Installieren des SQL Server-Connectors</span><span class="sxs-lookup"><span data-stu-id="cb045-107">Step 2: Installing the SQL Server Connector</span></span>](#Step2)

-   [<span data-ttu-id="cb045-108">Schritt 3: Konfigurieren von SQL Server zur Verwendung eines Anbieters für erweiterbare Schlüsselverwaltung für den Schlüsseltresor</span><span class="sxs-lookup"><span data-stu-id="cb045-108">Step 3: Configure SQL Server to use an EKM provider for the Key Vault</span></span>](#Step3)

-   [<span data-ttu-id="cb045-109">Beispiel A: Transparente Datenverschlüsselung mit einem asymmetrischen Schlüssel aus dem Schlüsseltresor</span><span class="sxs-lookup"><span data-stu-id="cb045-109">Example A: Transparent Data Encryption by Using an Asymmetric Key from the Key Vault</span></span>](#ExampleA)

-   [<span data-ttu-id="cb045-110">Beispiel B: Verschlüsseln von Sicherungen mit einem asymmetrischen Schlüssel aus dem Schlüsseltresor</span><span class="sxs-lookup"><span data-stu-id="cb045-110">Example B: Encrypting Backups by Using an Asymmetric Key from the Key Vault</span></span>](#ExampleB)

-   [<span data-ttu-id="cb045-111">Beispiel C: Verschlüsselung auf Spaltenebene mit einem asymmetrischen Schlüssel aus dem Schlüsseltresor</span><span class="sxs-lookup"><span data-stu-id="cb045-111">Example C: Column Level Encryption by Using an Asymmetric Key from the Key Vault</span></span>](#ExampleC)

##  <a name="uses-of-ekm"></a><a name="Uses"></a><span data-ttu-id="cb045-112">Verwendung von EKM</span><span class="sxs-lookup"><span data-stu-id="cb045-112">Uses of EKM</span></span>
 <span data-ttu-id="cb045-113">Organisationen können die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Verschlüsselung zum Schutz sensibler Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb045-113">An organization can use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption to protect sensitive data.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="cb045-114">die Verschlüsselung umfasst [transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md), [Verschlüsselung auf Spaltenebene](/sql/t-sql/functions/cryptographic-functions-transact-sql) (CLE) und [Sicherungs Verschlüsselung](../../backup-restore/backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="cb045-114">encryption includes [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md), [Column Level Encryption](/sql/t-sql/functions/cryptographic-functions-transact-sql) (CLE), and [Backup Encryption](../../backup-restore/backup-encryption.md).</span></span> <span data-ttu-id="cb045-115">In all diesen Fällen werden die Daten mit einem symmetrischen Datenverschlüsselungsschlüssel verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="cb045-115">In all of these cases the data is encrypted using a symmetric data encryption key.</span></span> <span data-ttu-id="cb045-116">Der symmetrische Datenverschlüsselungsschlüssel wird außerdem geschützt durch Verschlüsselung mit einer Hierarchie von Schlüsseln, die in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="cb045-116">The symmetric data encryption key is further protected by encrypting it with a hierarchy of keys stored in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cb045-117">Alternativ bietet die Architektur des Anbieters für erweiterbare Schlüsselverwaltung [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] die Möglichkeit, die Datenverschlüsselungsschlüssel mit einem asymmetrischen Schlüssel zu schützen, der außerhalb von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in einem externen Kryptografieanbieter gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="cb045-117">Alternatively, the EKM provider architecture enables [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to protect the data encryption keys by using an asymmetric key stored outside of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in an external cryptographic provider.</span></span> <span data-ttu-id="cb045-118">Die Verwendung der Architektur des Anbieters für erweiterbare Schlüsselverwaltung stellt eine zusätzliche Sicherheitsebene dar und ermöglicht Unternehmen die getrennte Verwaltung von Schlüsseln und Daten.</span><span class="sxs-lookup"><span data-stu-id="cb045-118">Using EKM provider architecture adds an additional layer of security and allows organizations to separate the management of keys and data.</span></span>

 <span data-ttu-id="cb045-119">Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Connector für die Azure Key Vault-Vorschau ermöglicht [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] die Nutzung des skalierbaren, leistungsfähigen und hochverfügbaren Schlüsseltresordiensts als EKM-Anbieter für den Schutz des Verschlüsselungsschlüssels.</span><span class="sxs-lookup"><span data-stu-id="cb045-119">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector for Azure Key Vault lets [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] leverage the scalable, high performance, and highly available key vault service as an EKM provider for encryption key protection.</span></span> <span data-ttu-id="cb045-120">Der Schlüsseltresordienst kann mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Installationen auf virtuellen [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure-Computern und für lokale Server verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cb045-120">The key vault service can be used with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installations on [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure Virtual Machines and for on-premises servers.</span></span> <span data-ttu-id="cb045-121">Der Schlüsseltresordienst bietet auch die Option, genau gesteuerte und stark überwachte Hardwaresicherheitsmodule (HSMs) für ein höheres Maß an Schutz für asymmetrische Schlüssel zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb045-121">The key vault service also provides the option to use tightly controlled and monitored Hardware Security Modules (HSMs) for a higher level of protection for asymmetric encryption keys.</span></span> <span data-ttu-id="cb045-122">Weitere Informationen zum Schlüsseltresor finden Sie unter [Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521401).</span><span class="sxs-lookup"><span data-stu-id="cb045-122">For more information about the key vault, see [Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521401).</span></span>

 <span data-ttu-id="cb045-123">Die folgende Grafik enthält eine Zusammenfassung des Prozessablaufs der erweiterbaren Schlüsselverwaltung mit Schlüsseltresor.</span><span class="sxs-lookup"><span data-stu-id="cb045-123">The following image summarizes the process flow of EKM using the key vault.</span></span> <span data-ttu-id="cb045-124">Die Nummern der Prozessschritte in der Grafik stimmen nicht mit den Nummern der Einrichtungsschritte, die auf die Grafik folgen, überein.</span><span class="sxs-lookup"><span data-stu-id="cb045-124">The process step numbers in the image are not meant to match the setup step numbers that follow the image.</span></span>

 <span data-ttu-id="cb045-125">![Erweiterbare Schlüsselverwaltung in SQL Server mithilfe von Azure Key Vault](../../../database-engine/media/ekm-using-azure-key-vault.png "Erweiterbare Schlüsselverwaltung in SQL Server mithilfe von Azure Key Vault")</span><span class="sxs-lookup"><span data-stu-id="cb045-125">![SQL Server EKM using the Azure Key Vault](../../../database-engine/media/ekm-using-azure-key-vault.png "SQL Server EKM using the Azure Key Vault")</span></span>

##  <a name="step-1-set-up-the-key-vault-for-use-by-sql-server"></a><a name="Step1"></a><span data-ttu-id="cb045-126">Schritt 1: Einrichten der Key Vault für die Verwendung durch SQL Server</span><span class="sxs-lookup"><span data-stu-id="cb045-126">Step 1: Set up the Key Vault for use by SQL Server</span></span>
 <span data-ttu-id="cb045-127">Führen Sie die folgenden Schritte aus, um einen Schlüsseltresor für die Verwendung mit der [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] für den Schutz des Verschlüsselungsschlüssels einzurichten.</span><span class="sxs-lookup"><span data-stu-id="cb045-127">Use the following steps to set up a key vault for use with the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] for encryption key protection.</span></span> <span data-ttu-id="cb045-128">Für die Organisation wird möglicherweise bereits ein Tresor verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb045-128">A vault may already be in use for the organization.</span></span> <span data-ttu-id="cb045-129">Wenn kein Tresor vorhanden ist, kann der Azure-Administrator in Ihrem Unternehmen, der die Verschlüsselungsschlüssel verwaltet, einen Tresor erstellen, einen asymmetrischen Schlüssel im Tresor generieren und dann [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] autorisieren, den Schlüssel zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb045-129">When a vault does not exist, the Azure Administrator in your organization that is designated to manage encryption keys can create a vault, generate an asymmetric key in the vault, and then authorize [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to use the key.</span></span> <span data-ttu-id="cb045-130">Machen Sie sich unter [Erste Schritte mit Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402)und der Referenz zu PowerShell- [Azure Key Vault-Cmdlets](https://docs.microsoft.com/powershell/module/azurerm.keyvault) mit dem Schlüsseltresordienst vertraut.</span><span class="sxs-lookup"><span data-stu-id="cb045-130">To familiarize yourself with the key vault service review [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402), and the PowerShell [Azure Key Vault Cmdlets](https://docs.microsoft.com/powershell/module/azurerm.keyvault) reference.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="cb045-131">Wenn Sie über mehrere Azure-Abonnements verfügen, müssen Sie das Abonnement nehmen, das [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]enthält.</span><span class="sxs-lookup"><span data-stu-id="cb045-131">If you have multiple Azure subscriptions, you must use the subscription that contains [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>

1.  <span data-ttu-id="cb045-132">**Erstellen Sie einen Tresor:** Erstellen Sie einen Tresor nach der Anweisungen im Abschnitt **Erstellen eines Schlüsseltresors** in [Erste Schritte mit Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="cb045-132">**Create a vault:** Create a vault by using the instructions in the **Create a key vault** section of [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span> <span data-ttu-id="cb045-133">Notieren Sie den Namen des Tresors.</span><span class="sxs-lookup"><span data-stu-id="cb045-133">Record the name of the vault.</span></span> <span data-ttu-id="cb045-134">In diesem Thema wird **ContosoKeyVault** als Schlüsseltresorname verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb045-134">This topic uses **ContosoKeyVault** as the key vault name.</span></span>

2.  <span data-ttu-id="cb045-135">**Generieren Sie einen asymmetrischen Schlüssel im Tresor:** Der asymmetrische Schlüssel im Schlüsseltresor dient zum Schutz der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Verschlüsselungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="cb045-135">**Generate an asymmetric key in the vault:** The asymmetric key in the key vault is used to protect [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption keys.</span></span> <span data-ttu-id="cb045-136">Nur der öffentliche Teil des asymmetrischen Schlüssels verlässt jemals den Tresor, der private Teil wird nie vom Tresor exportiert.</span><span class="sxs-lookup"><span data-stu-id="cb045-136">Only the public portion of the asymmetric key ever leaves the vault, the private portion is never exported by the vault.</span></span> <span data-ttu-id="cb045-137">Alle kryptografischen Vorgänge mit dem asymmetrischen Schlüssel werden an den Azure-Schlüsseltresor delegiert und durch die Schlüsseltresorsicherheit geschützt.</span><span class="sxs-lookup"><span data-stu-id="cb045-137">All cryptographic operations using the asymmetric key are delegated to the Azure Key Vault, and are protected by the key vault security.</span></span>

     <span data-ttu-id="cb045-138">Es gibt mehrere Möglichkeiten, wie Sie einen asymmetrischen Schlüssel generieren und im Tresor speichern können.</span><span class="sxs-lookup"><span data-stu-id="cb045-138">There are several ways that you can generate an asymmetric key and store it in the vault.</span></span> <span data-ttu-id="cb045-139">Sie können einen Schlüssel extern generieren und den Schlüssel als PFX-Datei in den Tresor importieren.</span><span class="sxs-lookup"><span data-stu-id="cb045-139">You can externally generate a key, and import the key into the vault as a .pfx file.</span></span> <span data-ttu-id="cb045-140">Oder Sie erstellen den Schlüssel mit den Schlüsseltresor-APIs direkt im Tresor.</span><span class="sxs-lookup"><span data-stu-id="cb045-140">Or create the key directly in the vault by using the key vault APIs.</span></span>

     <span data-ttu-id="cb045-141">Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Connector erfordert asymmetrische Schlüssel nach 2048-Bit-RSA, und der Name des Schlüssels darf nur die Zeichen „a–z“, „A–Z“, „0–9“ und „-“ enthalten.</span><span class="sxs-lookup"><span data-stu-id="cb045-141">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector requires the asymmetric keys to be 2048-bit RSA, and the key name can only use the characters "a-z", "A-Z", "0-9", and "-".</span></span> <span data-ttu-id="cb045-142">In diesem Dokument wird als Name des asymmetrischen Schlüssels **ContosoMasterKey**verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb045-142">In this document the name of the asymmetric key is referred to as **ContosoMasterKey**.</span></span> <span data-ttu-id="cb045-143">Ersetzen Sie dies durch den eindeutigen Namen, den Sie für den Schlüssel verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb045-143">Replace this with the unique name you use for the key.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="cb045-144">Das Importieren des asymmetrischen Schlüssels wird für Produktionsszenarien dringend empfohlen, da der Administrator dann den Schlüssel in einem Schlüsselhinterlegungssystem hinterlegen kann.</span><span class="sxs-lookup"><span data-stu-id="cb045-144">Importing the asymmetric key is highly recommended for production scenarios because it allows the administrator to escrow the key in a key escrow system.</span></span> <span data-ttu-id="cb045-145">Wenn der asymmetrische Schlüssel im Tresor erstellt wird, kann er nicht hinterlegt werden, da der private Schlüssel nie den Tresor verlassen kann.</span><span class="sxs-lookup"><span data-stu-id="cb045-145">If the asymmetric key is created in the vault, it cannot be escrowed because the private key can never leave the vault.</span></span> <span data-ttu-id="cb045-146">Schlüssel zum Schützen wichtiger Daten sollten hinterlegt werden.</span><span class="sxs-lookup"><span data-stu-id="cb045-146">Keys used to protect critical data should be escrowed.</span></span> <span data-ttu-id="cb045-147">Der Verlust eines asymmetrischen Schlüssels führt dazu, dass Daten dauerhaft nicht wiederhergestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="cb045-147">The loss of an asymmetric key will result in permanently unrecoverable data.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="cb045-148">Der Schlüsseltresor unterstützt mehrere Versionen desselben benannten Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="cb045-148">The key vault supports multiple versions of the same named key.</span></span> <span data-ttu-id="cb045-149">Schlüssel zur Verwendung durch den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Connector sollten nicht mit Versionsangabe versehen oder mehrfach wieder verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cb045-149">Keys to be used by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector should not be versioned or rolled.</span></span> <span data-ttu-id="cb045-150">Wenn der Administrator den Schlüssel für die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Verschlüsselung wieder verwenden möchte, sollte ein neuer Schlüssel mit einem anderen Namen im Tresor erstellt und zum Verschlüsseln des Datenverschlüsselungsschlüssels verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cb045-150">If the administrator wants to roll the key used for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption, a new key with a different name should be created in the vault and used to encrypt the DEK.</span></span>

     <span data-ttu-id="cb045-151">Weitere Informationen zum Importieren eines Schlüssels in den Tresor oder zum Erstellen eines Schlüssels im Schlüsseltresor (nicht empfohlen für Produktionsumgebungen) finden Sie im Abschnitt **Hinzufügen eines Schlüssels oder eines geheimen Schlüssels zum Schlüsseltresor** in [Erste Schritte mit Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="cb045-151">For more information on how to import a key into the key vault or to create a key in the key vault (not recommended for a production environment), see the **Add a key or secret to the key vault** section in [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span>

3.  <span data-ttu-id="cb045-152">**Rufen Sie Azure Active Directory-Dienstprinzipale für SQL Server ab:** Wenn sich die Organisation für einen Microsoft Cloud-Dienst registriert, erhält sie ein Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cb045-152">**Get Azure Active Directory Service Principals to use for SQL Server:** When the organization signs up for a Microsoft cloud service, it gets an Azure Active Directory.</span></span> <span data-ttu-id="cb045-153">Erstellen Sie in Azure Active Directory **Dienstprinzipale** , die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (zur Authentifizierung gegenüber Azure Active Directory) beim Zugriff auf den Schlüsseltresor verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb045-153">Create **Service Principals** in the Azure Active Directory for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to use (to authenticate itself to Azure Active Directory) while accessing the key vault.</span></span>

    -   <span data-ttu-id="cb045-154">Ein **Dienstprinzipal** wird von einem [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Administrator benötigt, um beim Konfigurieren von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] für die Verschlüsselung auf den Tresor zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="cb045-154">One **Service Principal** will be needed by a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] administrator to access the vault while configuring [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to use encryption.</span></span>

    -   <span data-ttu-id="cb045-155">Ein anderer **Dienstprinzipal** wird von der [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] benötigt, um beim Entpacken von zur [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Verschlüsselung verwendeten Schlüsseln auf den Tresor zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="cb045-155">Another **Service Principal** will be needed by the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] to access the vault for unwrapping keys used in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption.</span></span>

     <span data-ttu-id="cb045-156">Weitere Informationen zum Registrieren einer Anwendung und Generieren eines Dienstprinzipals finden Sie im Abschnitt **Registrieren einer Anwendung in Azure Active Directory** in [Erste Schritte mit Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="cb045-156">For more information about how to register an application and generate a service principal, see the **Register an Application with Azure Active Directory** section in [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span> <span data-ttu-id="cb045-157">Der Registrierungsprozess gibt eine **Anwendungs-ID** (auch bekannt als **CLIENT-ID**) und einen **Authentifizierungsschlüssel** (auch bekannt als **geheimer Schlüssel**) für jeden Azure Active Directory- **Dienstprinzipal**zurück.</span><span class="sxs-lookup"><span data-stu-id="cb045-157">The registration process returns an **Application ID** (also known as a **CLIENT ID**) and a **Authentication Key** (also known as a **Secret**) for each Azure Active Directory **Service Principal**.</span></span> <span data-ttu-id="cb045-158">Wenn Sie in der-Anweisung verwendet wird `CREATE CREDENTIAL` , muss der Bindestrich aus der **Client-ID**entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="cb045-158">When used in the `CREATE CREDENTIAL` statement, the hyphen must be removed from the **CLIENT ID**.</span></span> <span data-ttu-id="cb045-159">Notieren Sie diese für die Verwendung in den unten stehenden Skripts:</span><span class="sxs-lookup"><span data-stu-id="cb045-159">Record these for use in the scripts below:</span></span>

    -   <span data-ttu-id="cb045-160">**Dienstprinzipal** für eine **sysadmin** -Anmeldung: **CLIENTID_sysadmin_login** und **SECRET_sysadmin_login**</span><span class="sxs-lookup"><span data-stu-id="cb045-160">**Service Principal** for a **sysadmin** login: **CLIENTID_sysadmin_login** and **SECRET_sysadmin_login**</span></span>

    -   <span data-ttu-id="cb045-161">**Dienstprinzipal** für die [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)]: **CLIENTID_DBEngine** und **SECRET_DBEngine**.</span><span class="sxs-lookup"><span data-stu-id="cb045-161">**Service Principal** for the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)]: **CLIENTID_DBEngine** and **SECRET_DBEngine**.</span></span>

4.  <span data-ttu-id="cb045-162">**Erteilen Sie dem Dienst Prinzipal die Berechtigung, auf die Key Vault zuzugreifen:** Sowohl der **CLIENTID_sysadmin_login** als auch **CLIENTID_DBEngineService Prinzipale** benötigen die Berechtigungen **Get**, **List**, **wrapkey**und **unwrapkey** im Schlüssel Tresor.</span><span class="sxs-lookup"><span data-stu-id="cb045-162">**Grant Permission for the Service Principals to access the Key Vault:** Both the **CLIENTID_sysadmin_login** and **CLIENTID_DBEngineService Principals** require the **get**, **list**, **wrapKey**, and **unwrapKey** permissions in the key vault.</span></span> <span data-ttu-id="cb045-163">Wenn Sie beabsichtigen, Schlüssel über [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] zu erstellen, müssen Sie auch die Berechtigung **create** im Schlüsseltresor erteilen.</span><span class="sxs-lookup"><span data-stu-id="cb045-163">If you intend to create keys through [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] you also need to grant the **create** permission in key vault.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="cb045-164">Benutzer müssen mindestens über die Vorgänge **wrapKey** und **unwrapKey** für den Schlüsseltresor verfügen.</span><span class="sxs-lookup"><span data-stu-id="cb045-164">Users must have at least the **wrapKey** and **unwrapKey** operations for the key vault.</span></span>

     <span data-ttu-id="cb045-165">Weitere Informationen zum Erteilen von Berechtigungen für den Tresor finden Sie im Abschnitt **Autorisieren der Anwendung zum Verwenden des Schlüssels oder des geheimen Schlüssels** in [Erste Schritte mit Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="cb045-165">For more information about granting permissions to the vault, see the **Authorize the application to use the key or secret** section in [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span>

     <span data-ttu-id="cb045-166">Links zur Dokumentation für Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="cb045-166">Links to Azure Key Vault documentation</span></span>

    -   [<span data-ttu-id="cb045-167">Was ist der Azure-Schlüsseltresor?</span><span class="sxs-lookup"><span data-stu-id="cb045-167">What is Azure Key Vault?</span></span>](https://go.microsoft.com/fwlink/?LinkId=521401)

    -   [<span data-ttu-id="cb045-168">Erste Schritte mit Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="cb045-168">Get Started with Azure Key Vault</span></span>](https://go.microsoft.com/fwlink/?LinkId=521402)

    -   <span data-ttu-id="cb045-169">Referenz der PowerShell- [Azure Key Vault-Cmdlets](https://docs.microsoft.com/powershell/module/azurerm.keyvault)</span><span class="sxs-lookup"><span data-stu-id="cb045-169">PowerShell [Azure Key Vault Cmdlets](https://docs.microsoft.com/powershell/module/azurerm.keyvault) reference</span></span>

##  <a name="step-2-install-the-sql-server-connector"></a><a name="Step2"></a><span data-ttu-id="cb045-170">Schritt 2: Installieren des SQL Server-Connector</span><span class="sxs-lookup"><span data-stu-id="cb045-170">Step 2: Install the SQL Server Connector</span></span>
 <span data-ttu-id="cb045-171">Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Connector wird vom Administrator des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Computers heruntergeladen und installiert.</span><span class="sxs-lookup"><span data-stu-id="cb045-171">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector is downloaded and installed by the administrator of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] computer.</span></span> <span data-ttu-id="cb045-172">Der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Connector steht im [Microsoft-Downloadcenter](https://go.microsoft.com/fwlink/p/?LinkId=521700)als Download zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cb045-172">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector is available as a download from the [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=521700).</span></span>  <span data-ttu-id="cb045-173">Suchen Sie nach **SQL Server-Connector für Microsoft Azure Key Vault**. Überprüfen Sie die Details, Systemanforderungen und Installationsanweisungen, wählen Sie den Download des Connectors, und starten Sie die Installation mit **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="cb045-173">Search for **SQL Server Connector for Microsoft Azure Key Vault**, review the details, system requirements and install instructions and choose to download the connector and start the installation using **Run**.</span></span> <span data-ttu-id="cb045-174">Lesen Sie die Lizenzbedingungen, stimmen Sie ihnen zu, und setzen Sie den Vorgang fort.</span><span class="sxs-lookup"><span data-stu-id="cb045-174">Review the license and accept the license and continue.</span></span>

 <span data-ttu-id="cb045-175">Der Connector wird standardmäßig unter " **c:\Programme\SQL Server Connector" für Microsoft Azure Key Vault**installiert.</span><span class="sxs-lookup"><span data-stu-id="cb045-175">By default the connector is installed at **C:\Program Files\SQL Server Connector for Microsoft Azure Key Vault**.</span></span> <span data-ttu-id="cb045-176">Dieser Speicherort kann während des Setups geändert werden.</span><span class="sxs-lookup"><span data-stu-id="cb045-176">This location can be changed during setup.</span></span> <span data-ttu-id="cb045-177">(Wenn Sie ihn ändern, passen Sie die unten angegebenen Skripts entsprechend an.)</span><span class="sxs-lookup"><span data-stu-id="cb045-177">(If changed, adjust the scripts below.)</span></span>

 <span data-ttu-id="cb045-178">Nach Abschluss der Installation ist Folgendes auf dem Computer installiert:</span><span class="sxs-lookup"><span data-stu-id="cb045-178">On completing the install, the following are installed on the machine:</span></span>

-   <span data-ttu-id="cb045-179">**Microsoft.AzureKeyVaultService.EKM.dll**: Dies ist die kryptografische DLL des Anbieters für erweiterbare Schlüsselverwaltung, die bei [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] mit der CREATE CRYPTOGRAPHIC PROVIDER-Anweisung registriert werden muss.</span><span class="sxs-lookup"><span data-stu-id="cb045-179">**Microsoft.AzureKeyVaultService.EKM.dll**: This is the cryptographic EKM provider DLL that needs to be registered with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using the CREATE CRYPTOGRAPHIC PROVIDER statement.</span></span>

-   <span data-ttu-id="cb045-180">**Azure Key Vault SQL Server-Connector**: Dies ist ein Windows-Dienst, der dem kryptografischen Anbieter für erweiterbare Schlüsselverwaltung die Kommunikation mit dem Schlüsseltresor ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="cb045-180">**Azure Key Vault SQL Server Connector**: This is a Windows service that enables the cryptographic EKM provider to communicate with the key vault.</span></span>

 <span data-ttu-id="cb045-181">Bei der Installation des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Connectors können Sie optional auch Beispielskripts für die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Verschlüsselung herunterladen.</span><span class="sxs-lookup"><span data-stu-id="cb045-181">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector installation also allows you to optionally download sample scripts for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption.</span></span>

##  <a name="step-3-configure-sql-server-to-use-an-ekm-provider-for-the-key-vault"></a><a name="Step3"></a><span data-ttu-id="cb045-182">Schritt 3: Konfigurieren von SQL Server für die Verwendung eines EKM-Anbieters für das Key Vault</span><span class="sxs-lookup"><span data-stu-id="cb045-182">Step 3: Configure SQL Server to use an EKM provider for the Key Vault</span></span>

###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="cb045-183">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="cb045-183">Permissions</span></span>
 <span data-ttu-id="cb045-184">Das gesamte Verfahren erfordert die CONTROL SERVER-Berechtigung oder die Mitgliedschaft in der festen Serverrolle **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="cb045-184">To complete this entire process requires CONTROL SERVER permission or membership in the **sysadmin** fixed server role.</span></span> <span data-ttu-id="cb045-185">Bestimmte Aktionen erfordern die folgenden Berechtigungen:</span><span class="sxs-lookup"><span data-stu-id="cb045-185">Specific actions require the following permissions:</span></span>

-   <span data-ttu-id="cb045-186">Zum Erstellen eines Kryptografieanbieters ist die CONTROL SERVER-Berechtigung oder die Mitgliedschaft in der festen Serverrolle **sysadmin** erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cb045-186">To create a cryptographic provider, requires CONTROL SERVER permission or membership in the **sysadmin** fixed server role.</span></span>

-   <span data-ttu-id="cb045-187">Zum Ändern einer Konfigurationsoption und Ausführen der RECONFIGURE-Anweisung muss Ihnen die ALTER SETTINGS-Berechtigung auf Serverebene erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="cb045-187">To change a configuration option and run the RECONFIGURE statement, you must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="cb045-188">Die ALTER SETTINGS-Berechtigung ist in den festen Serverrollen **sysadmin** und **serveradmin** eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="cb045-188">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>

-   <span data-ttu-id="cb045-189">Zum Erstellen von Anmeldeinformationen ist die ALTER ANY CREDENTIAL-Berechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cb045-189">To create a credential, requires ALTER ANY CREDENTIAL permission.</span></span>

-   <span data-ttu-id="cb045-190">Zum Hinzufügen von Anmeldeinformationen zu einem Anmeldenamen ist die ALTER ANY LOGIN-Berechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cb045-190">To add a credential to a login, requires ALTER ANY LOGIN permission.</span></span>

-   <span data-ttu-id="cb045-191">Zum Erstellen eines asymmetrischen Schlüssels ist die CREATE ASYMMETRIC KEY-Berechtigung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cb045-191">To create an asymmetric key, requires CREATE ASYMMETRIC KEY permission.</span></span>

###  <a name="to-configure-sql-server-to-use-a-cryptographic-provider"></a><a name="TsqlProcedure"></a><span data-ttu-id="cb045-192">So konfigurieren Sie SQL Server für die Verwendung eines Kryptografieanbieters</span><span class="sxs-lookup"><span data-stu-id="cb045-192">To configure SQL Server to use a cryptographic provider</span></span>

1.  <span data-ttu-id="cb045-193">Konfigurieren Sie die [!INCLUDE[ssDE](../../../includes/ssde-md.md)] für die Verwendung der erweiterbaren Schlüsselverwaltung, und registrieren (erstellen) Sie den Kryptografieanbieter in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cb045-193">Configure the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to use EKM, and register (create) the cryptographic provider with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>

    ```sql
    -- Enable advanced options.
    USE master;
    GO

    sp_configure 'show advanced options', 1 ;
    GO
    RECONFIGURE ;
    GO
    -- Enable EKM provider
    sp_configure 'EKM provider enabled', 1 ;
    GO
    RECONFIGURE ;
    GO

    -- Create a cryptographic provider, using the SQL Server Connector
    -- which is an EKM provider for the Azure Key Vault. This example uses 
    -- the name AzureKeyVault_EKM_Prov.

    CREATE CRYPTOGRAPHIC PROVIDER AzureKeyVault_EKM_Prov 
    FROM FILE = 'C:\Program Files\SQL Server Connector for Microsoft Azure Key Vault\Microsoft.AzureKeyVaultService.EKM.dll';
    GO
    ```

2.  <span data-ttu-id="cb045-194">Richten Sie [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Anmeldeinformationen für eine [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Administratoranmeldung ein, die den Schlüsseltresor verwendet, um [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Verschlüsselungsszenarien einzurichten und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="cb045-194">Setup a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] credential for a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] administrator login to use the key vault in order to setup and manage [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption scenarios.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="cb045-195">Das **Identity** -Argument von `CREATE CREDENTIAL` erfordert den Schlüssel Tresor Namen.</span><span class="sxs-lookup"><span data-stu-id="cb045-195">The **IDENTITY** argument of `CREATE CREDENTIAL` requires the key vault name.</span></span> <span data-ttu-id="cb045-196">Das **Secret** -Argument von `CREATE CREDENTIAL` erfordert *\<Client ID>* , dass (ohne Bindestriche) und *\<Secret>* gemeinsam ohne Leerzeichen dazwischen gereicht werden.</span><span class="sxs-lookup"><span data-stu-id="cb045-196">The **SECRET** argument of `CREATE CREDENTIAL` requires the *\<Client ID>* (without hyphens) and *\<Secret>* to be passed together without a space between them.</span></span>

     <span data-ttu-id="cb045-197">Im folgenden Beispiel wird die **Client-ID** ( `EF5C8E09-4D2A-4A76-9998-D93440D8115D` ) aus den Bindestrichen entfernt und als Zeichenfolge eingegeben, `EF5C8E094D2A4A769998D93440D8115D` und der **geheime** Schlüssel wird durch die Zeichenfolge *SECRET_sysadmin_login*dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cb045-197">In the following example, the **Client ID** (`EF5C8E09-4D2A-4A76-9998-D93440D8115D`) is stripped of the hyphens and entered as the string `EF5C8E094D2A4A769998D93440D8115D` and the **Secret** is represented by the string *SECRET_sysadmin_login*.</span></span>

    ```sql
    USE master;
    CREATE CREDENTIAL sysadmin_ekm_cred 
        WITH IDENTITY = 'ContosoKeyVault', 
        SECRET = 'EF5C8E094D2A4A769998D93440D8115DSECRET_sysadmin_login' 
    FOR CRYPTOGRAPHIC PROVIDER AzureKeyVault_EKM_Prov ;

    -- Add the credential to the SQL Server administrators domain login 
    ALTER LOGIN [<domain>/<login>]
    ADD CREDENTIAL sysadmin_ekm_cred;
    ```

     <span data-ttu-id="cb045-198">Ein Beispiel für die Verwendung von Variablen für die `CREATE CREDENTIAL` Argumente und die programmgesteuerte Entfernung der Bindestriche aus der Client-ID finden Sie unter [Create Credential &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cb045-198">For an example of using variables for the `CREATE CREDENTIAL` arguments and programmatically removing the hyphens from the Client ID, see [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span></span>

3.  <span data-ttu-id="cb045-199">Wenn Sie einen asymmetrischen Schlüssel importiert haben, wie zuvor in Schritt 1, Abschnitt 3, beschrieben, öffnen Sie den Schlüssel, indem Sie im folgenden Beispiel Ihren Schlüsselnamen angeben.</span><span class="sxs-lookup"><span data-stu-id="cb045-199">If you imported an asymmetric key as described earlier in step 1, section 3, open the key by providing your key name in the following example.</span></span>

    ```sql
    CREATE ASYMMETRIC KEY CONTOSO_KEY 
    FROM PROVIDER [AzureKeyVault_EKM_Prov]
    WITH PROVIDER_KEY_NAME = 'ContosoMasterKey',
    CREATION_DISPOSITION = OPEN_EXISTING;
    ```

     <span data-ttu-id="cb045-200">Obwohl dies für die Produktionsumgebung nicht empfohlen wird (da der Schlüssel nicht exportiert werden kann), ist es möglich, von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]aus einen asymmetrischen Schlüssel direkt im Tresor zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cb045-200">Though not recommended for production (because the key cannot be exported), it is possible to create an asymmetric key directly in the vault from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="cb045-201">Wenn Sie zuvor keinen Schlüssel importiert haben, erstellen Sie mit dem folgenden Skript zu Testzwecken einen asymmetrischen Schlüssel im Schlüsseltresor.</span><span class="sxs-lookup"><span data-stu-id="cb045-201">If you did not import a key earlier, then create an asymmetric key in the key vault for testing by using the following script.</span></span> <span data-ttu-id="cb045-202">Führen Sie das Skript mithilfe einer mit den Anmeldeinformationen **sysadmin_ekm_cred** bereitgestellten Anmeldung aus.</span><span class="sxs-lookup"><span data-stu-id="cb045-202">Execute the script, using a login provisioned with the **sysadmin_ekm_cred** credential.</span></span>

    ```sql
    CREATE ASYMMETRIC KEY CONTOSO_KEY 
    FROM PROVIDER [AzureKeyVault_EKM_Prov]
    WITH ALGORITHM = RSA_2048,
    PROVIDER_KEY_NAME = 'ContosoMasterKey';
    ```

> [!TIP]
>  <span data-ttu-id="cb045-203">Benutzer, die den Fehler **kann nicht öffentlichen Schlüssel vom Anbieter exportiert. Anbieterfehlercode: 2053.**</span><span class="sxs-lookup"><span data-stu-id="cb045-203">Users receiving the error **Cannot export public key from the provider. Provider error code: 2053.**</span></span> <span data-ttu-id="cb045-204">sollten ihre **get**, **list**, **wrapKey**- und **unwrapKey** -Berechtigungen im Schlüsseltresor prüfen.</span><span class="sxs-lookup"><span data-stu-id="cb045-204">should check their **get**, **list**, **wrapKey**, and **unwrapKey** permissions in the key vault.</span></span>

 <span data-ttu-id="cb045-205">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="cb045-205">For more information, see the following:</span></span>

-   [<span data-ttu-id="cb045-206">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cb045-206">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)

-   [<span data-ttu-id="cb045-207">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cb045-207">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-cryptographic-provider-transact-sql)

-   [<span data-ttu-id="cb045-208">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cb045-208">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-credential-transact-sql)

-   [<span data-ttu-id="cb045-209">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cb045-209">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-asymmetric-key-transact-sql)

-   [<span data-ttu-id="cb045-210">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cb045-210">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)

-   [<span data-ttu-id="cb045-211">ALTER LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cb045-211">ALTER LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-login-transact-sql)

## <a name="examples"></a><span data-ttu-id="cb045-212">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cb045-212">Examples</span></span>

###  <a name="example-a-transparent-data-encryption-by-using-an-asymmetric-key-from-the-key-vault"></a><a name="ExampleA"></a><span data-ttu-id="cb045-213">Beispiel A: Transparent Data Encryption mithilfe eines asymmetrischen Schlüssels aus der Key Vault</span><span class="sxs-lookup"><span data-stu-id="cb045-213">Example A: Transparent Data Encryption by Using an Asymmetric Key from the Key Vault</span></span>
 <span data-ttu-id="cb045-214">Erstellen Sie nach Abschluss der obigen Schritte Anmeldeinformationen und eine Anmeldung, und erstellen Sie einen Datenbank-Verschlüsselungsschlüssel, der durch den asymmetrischen Schlüssel im Schlüsseltresor geschützt wird.</span><span class="sxs-lookup"><span data-stu-id="cb045-214">After completing the steps above, create a credential and a login, create a database encryption key protected by the asymmetric key in the key vault.</span></span> <span data-ttu-id="cb045-215">Verwenden Sie den Datenbank-Verschlüsselungsschlüssel zum Verschlüsseln einer Datenbank mit transparenter Datenverschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="cb045-215">Use the database encryption key to encrypt a database with TDE.</span></span>

 <span data-ttu-id="cb045-216">Zum Verschlüsseln einer Datenbank ist die CONTROL-Berechtigung für die Datenbank erforderlich.</span><span class="sxs-lookup"><span data-stu-id="cb045-216">To encrypt a database requires CONTROL permission on the database.</span></span>

##### <a name="to-enable-tde-using-ekm-and-the-key-vault"></a><span data-ttu-id="cb045-217">So aktivieren Sie die transparente Datenverschlüsselung mit erweiterbarer Schlüsselverwaltung und dem Schlüsseltresor</span><span class="sxs-lookup"><span data-stu-id="cb045-217">To enable TDE using EKM and the Key Vault</span></span>

1.  <span data-ttu-id="cb045-218">Erstellen Sie [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Anmeldeinformationen für die [!INCLUDE[ssDE](../../../includes/ssde-md.md)] , die beim Laden der Datenbank für den Zugriff auf die erweiterbare Schlüsselverwaltung mit Schlüsseltresor verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cb045-218">Create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] credential for the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to use when accessing the key vault EKM during database load.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="cb045-219">Das **Identity** -Argument von `CREATE CREDENTIAL` erfordert den Schlüssel Tresor Namen.</span><span class="sxs-lookup"><span data-stu-id="cb045-219">The **IDENTITY** argument of `CREATE CREDENTIAL` requires the key vault name.</span></span> <span data-ttu-id="cb045-220">Das **Secret** -Argument von `CREATE CREDENTIAL` erfordert *\<Client ID>* , dass (ohne Bindestriche) und *\<Secret>* gemeinsam ohne Leerzeichen dazwischen gereicht werden.</span><span class="sxs-lookup"><span data-stu-id="cb045-220">The **SECRET** argument of `CREATE CREDENTIAL` requires the *\<Client ID>* (without hyphens) and *\<Secret>* to be passed together without a space between them.</span></span>

     <span data-ttu-id="cb045-221">Im folgenden Beispiel wird die **Client-ID** (`EF5C8E09-4D2A-4A76-9998-D93440D8115D`) von den Bindestrichen bereinigt und als Zeichenfolge `EF5C8E094D2A4A769998D93440D8115D` eingegeben. Der **geheime Schlüssel** wird durch die Zeichenfolge *SECRET_DBEngine*dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cb045-221">In the following example, the **Client ID** (`EF5C8E09-4D2A-4A76-9998-D93440D8115D`) is stripped of the hyphens and entered as the string `EF5C8E094D2A4A769998D93440D8115D` and the **Secret** is represented by the string *SECRET_DBEngine*.</span></span>

    ```sql
    USE master;
    CREATE CREDENTIAL Azure_EKM_TDE_cred 
        WITH IDENTITY = 'ContosoKeyVault', 
        SECRET = 'EF5C8E094D2A4A769998D93440D8115DSECRET_DBEngine' 
        FOR CRYPTOGRAPHIC PROVIDER AzureKeyVault_EKM_Prov ;
    ```

2.  <span data-ttu-id="cb045-222">Erstellen Sie eine [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Anmeldung, die von der [!INCLUDE[ssDE](../../../includes/ssde-md.md)] für die transparente Datenverschlüsselung verwendet wird, und fügen Sie die Anmeldeinformationen hinzu.</span><span class="sxs-lookup"><span data-stu-id="cb045-222">Create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login to be used by the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] for TDE, and add the credential to it.</span></span> <span data-ttu-id="cb045-223">In diesem Beispiel wird der asymmetrische Schlüssel CONTOSO_KEY aus dem Schlüsseltresor verwendet, der importiert oder zuvor für die Masterdatenbank erstellt wurde, wie oben in [Schritt 3, Abschnitt 3](#Step3) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cb045-223">This example uses the CONTOSO_KEY asymmetric key stored in the key vault, which was imported or created earlier for the master database, as described in [Step 3, section 3](#Step3) above.</span></span>

    ```sql
    USE master;
    -- Create a SQL Server login associated with the asymmetric key 
    -- for the Database engine to use when it loads a database 
    -- encrypted by TDE.
    CREATE LOGIN TDE_Login 
    FROM ASYMMETRIC KEY CONTOSO_KEY;
    GO 

    -- Alter the TDE Login to add the credential for use by the 
    -- Database Engine to access the key vault
    ALTER LOGIN TDE_Login 
    ADD CREDENTIAL Azure_EKM_TDE_cred ;
    GO
    ```

3.  <span data-ttu-id="cb045-224">Erstellen Sie den Datenbank-Verschlüsselungsschlüssel (Database Encryption Key, DEK), der für die transparente Datenverschlüsselung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cb045-224">Create the database encryption key (DEK) that will be used for TDE.</span></span> <span data-ttu-id="cb045-225">Der DEK kann mit jedem von SQL Server unterstützten Algorithmus und jeder unterstützten Schlüssellänge erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="cb045-225">The DEK can be created using any SQL Server supported algorithm or key length.</span></span> <span data-ttu-id="cb045-226">Der DEK wird durch den asymmetrischen Schlüssel im Schlüsseltresor geschützt.</span><span class="sxs-lookup"><span data-stu-id="cb045-226">The DEK will be protected by the asymmetric key in the key vault.</span></span>

     <span data-ttu-id="cb045-227">In diesem Beispiel wird der asymmetrische Schlüssel CONTOSO_KEY aus dem Schlüsseltresor verwendet, der importiert oder zuvor erstellt wurde, wie oben in [Schritt 3, Abschnitt 3](#Step3) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cb045-227">This example uses the CONTOSO_KEY asymmetric key stored in the key vault, which was imported or created earlier, as described in [Step 3, section 3](#Step3) above.</span></span>

    ```sql
    USE ContosoDatabase;
    GO

    CREATE DATABASE ENCRYPTION KEY 
    WITH ALGORITHM = AES_128 
    ENCRYPTION BY SERVER ASYMMETRIC KEY CONTOSO_KEY;
    GO

    -- Alter the database to enable transparent data encryption.
    ALTER DATABASE ContosoDatabase 
    SET ENCRYPTION ON ;
    GO
    ```

     <span data-ttu-id="cb045-228">Weitere Informationen finden Sie unter</span><span class="sxs-lookup"><span data-stu-id="cb045-228">For more information, see the following:</span></span>

    -   [<span data-ttu-id="cb045-229">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cb045-229">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-encryption-key-transact-sql)

    -   [<span data-ttu-id="cb045-230">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="cb045-230">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)

###  <a name="example-b-encrypting-backups-by-using-an-asymmetric-key-from-the-key-vault"></a><a name="ExampleB"></a><span data-ttu-id="cb045-231">Beispiel B: Verschlüsseln von Sicherungen mit einem asymmetrischen Schlüssel aus der Key Vault</span><span class="sxs-lookup"><span data-stu-id="cb045-231">Example B: Encrypting Backups by Using an Asymmetric Key from the Key Vault</span></span>
 <span data-ttu-id="cb045-232">Verschlüsselte Sicherungen werden ab [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)]unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cb045-232">Encrypted backups are supported starting with [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)].</span></span> <span data-ttu-id="cb045-233">Im folgenden Beispiel wird eine Sicherung erstellt und wiederhergestellt, die mit einem Verschlüsselungsschlüssel verschlüsselt wurde, der durch den asymmetrischen Schlüssel im Schlüsseltresor geschützt wird.</span><span class="sxs-lookup"><span data-stu-id="cb045-233">The following example creates and restores a backup encrypted a data encryption key protected by the asymmetric key in the key vault.</span></span>

```sql
USE master;
BACKUP DATABASE [DATABASE_TO_BACKUP]
TO DISK = N'[PATH TO BACKUP FILE]' 
WITH FORMAT, INIT, SKIP, NOREWIND, NOUNLOAD, 
ENCRYPTION(ALGORITHM = AES_256, SERVER ASYMMETRIC KEY = [CONTOSO_KEY]);
GO
```

 <span data-ttu-id="cb045-234">Beispiel für Wiederherstellungscode.</span><span class="sxs-lookup"><span data-stu-id="cb045-234">Sample restore code.</span></span>

```sql
RESTORE DATABASE [DATABASE_TO_BACKUP]
FROM DISK = N'[PATH TO BACKUP FILE]' WITH FILE = 1, NOUNLOAD, REPLACE;
GO
```

 <span data-ttu-id="cb045-235">Weitere Informationen zu Sicherungs Optionen finden Sie unter [Backup &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="cb045-235">For more information about backup options, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>

###  <a name="example-c-column-level-encryption-by-using-an-asymmetric-key-from-the-key-vault"></a><a name="ExampleC"></a><span data-ttu-id="cb045-236">Beispiel C: Verschlüsselung auf Spaltenebene mithilfe eines asymmetrischen Schlüssels aus der Key Vault</span><span class="sxs-lookup"><span data-stu-id="cb045-236">Example C: Column Level Encryption by Using an Asymmetric Key from the Key Vault</span></span>
 <span data-ttu-id="cb045-237">Das folgende Beispiel erstellt einen symmetrischen Schlüssel, der durch den asymmetrischen Schlüssel im Schlüsseltresor geschützt wird.</span><span class="sxs-lookup"><span data-stu-id="cb045-237">The following example creates a symmetric key protected by the asymmetric key in the key vault.</span></span> <span data-ttu-id="cb045-238">Anschließend wird der symmetrische Schlüssel zum Verschlüsseln von Daten in der Datenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb045-238">Then the symmetric key is used to encrypt data in the database.</span></span>

 <span data-ttu-id="cb045-239">In diesem Beispiel wird der asymmetrische Schlüssel CONTOSO_KEY aus dem Schlüsseltresor verwendet, der importiert oder zuvor erstellt wurde, wie oben in [Schritt 3, Abschnitt 3](#Step3) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cb045-239">This example uses the CONTOSO_KEY asymmetric key stored in the key vault, which was imported or created earlier, as described in [Step 3, section 3](#Step3) above.</span></span> <span data-ttu-id="cb045-240">Um diesen asymmetrischen Schlüssel in der `ContosoDatabase` -Datenbank zu verwenden, müssen Sie die CREATE ASYMMETRIC KEY-Anweisung erneut ausführen, um der `ContosoDatabase` -Datenbank einen Verweis auf den Schlüssel zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="cb045-240">To use this asymmetric key in the `ContosoDatabase` database, you must execute the CREATE ASYMMETRIC KEY statement again, to provide the `ContosoDatabase` database with a reference to the key.</span></span>

```sql
USE [ContosoDatabase];
GO

-- Create a reference to the key in the key vault
CREATE ASYMMETRIC KEY CONTOSO_KEY 
FROM PROVIDER [AzureKeyVault_EKM_Prov]
WITH PROVIDER_KEY_NAME = 'ContosoMasterKey',
CREATION_DISPOSITION = OPEN_EXISTING;

-- Create the data encryption key.
-- The data encryption key can be created using any SQL Server 
-- supported algorithm or key length.
-- The DEK will be protected by the asymmetric key in the key vault

CREATE SYMMETRIC KEY DATA_ENCRYPTION_KEY
    WITH ALGORITHM=AES_256
    ENCRYPTION BY ASYMMETRIC KEY CONTOSO_KEY;

DECLARE @DATA VARBINARY(MAX);

--Open the symmetric key for use in this session
OPEN SYMMETRIC KEY DATA_ENCRYPTION_KEY 
DECRYPTION BY ASYMMETRIC KEY CONTOSO_KEY;

--Encrypt syntax
SELECT @DATA = ENCRYPTBYKEY(KEY_GUID('DATA_ENCRYPTION_KEY'), CONVERT(VARBINARY,'Plain text data to encrypt'));

-- Decrypt syntax
SELECT CONVERT(VARCHAR, DECRYPTBYKEY(@DATA));

--Close the symmetric key
CLOSE SYMMETRIC KEY DATA_ENCRYPTION_KEY;
```

## <a name="see-also"></a><span data-ttu-id="cb045-241">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb045-241">See Also</span></span>
 <span data-ttu-id="cb045-242">[Erstellen eines Kryptografieanbieters &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-cryptographic-provider-transact-sql) Erstellen von Anmelde Informationen [&#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) [Erstellen eines asymmetrischen Schlüssels &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql) [Erstellen eines symmetrischen Schlüssels &#40;von Transact-SQL&#41;](/sql/t-sql/statements/create-symmetric-key-transact-sql) [erweiterbare Schlüsselverwaltung &#40;EKM](extensible-key-management-ekm.md)&#41;[Aktivieren von TDE mithilfe der EKM](enable-tde-on-sql-server-using-ekm.md) - [Sicherungs Verschlüsselung](../../backup-restore/backup-encryption.md) [Erstellen einer verschlüsselten Sicherung](../../backup-restore/create-an-encrypted-backup.md)</span><span class="sxs-lookup"><span data-stu-id="cb045-242">[CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-cryptographic-provider-transact-sql) [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) [CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql) [CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-symmetric-key-transact-sql) [Extensible Key Management &#40;EKM&#41;](extensible-key-management-ekm.md) [Enable TDE Using EKM](enable-tde-on-sql-server-using-ekm.md) [Backup Encryption](../../backup-restore/backup-encryption.md) [Create an Encrypted Backup](../../backup-restore/create-an-encrypted-backup.md)</span></span>
