---
title: Erstellen von Anmeldeinformationen – Authentifizieren beim Azure-Speicher | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.backuptourl.createcred.f1
ms.assetid: 0622619d-27c5-4ff0-83e5-cde31648c27a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: afdbf2647c79e07cf3f190ec6710eeb6b7718f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723945"
---
# <a name="create-credential---authenticate-to-azure-storage"></a><span data-ttu-id="fcf7d-102">Erstellen von Anmeldeinformationen – Authentifizieren beim Azure-Speicher</span><span class="sxs-lookup"><span data-stu-id="fcf7d-102">Create Credential - Authenticate to Azure Storage</span></span>
  <span data-ttu-id="fcf7d-103">Im Dialogfeld **URL-Sicherung > Anmeldeinformationen erstellen** können Sie neue SQL-Anmeldeinformationen erstellen.</span><span class="sxs-lookup"><span data-stu-id="fcf7d-103">Use the **Backup to URL - Create Credential** dialog box to create a new SQL Credential.</span></span>  
  
 <span data-ttu-id="fcf7d-104">Wenn Sie die Anmeldeinformationen mithilfe dieses Dialogfelds erstellen, müssen Sie ein Azure-Verwaltungszertifikat bereitstellen, das dem lokalen Zertifikatspeicher hinzugefügt wurde, oder ein Veröffentlichungsprofil angeben, das auf den Computer heruntergeladen wurde, um das Abonnement und die Speicherkontoinformationen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="fcf7d-104">When using this dialog box to create a credential, you must provide an Azure Management Certificate added to the local certificate store or a publishing profile downloaded to your computer to validate the subscription and the storage account information.</span></span>  
  
 <span data-ttu-id="fcf7d-105">**SQL-Anmeldeinformationen**</span><span class="sxs-lookup"><span data-stu-id="fcf7d-105">**SQL Credential**</span></span>  
 <span data-ttu-id="fcf7d-106">Geben Sie den Namen für die SQL-Anmeldeinformationen an, die Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="fcf7d-106">Specify the name of the SQL Credential you want to create.</span></span>  
  
## <a name="azure-credentials"></a><span data-ttu-id="fcf7d-107">Azure-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="fcf7d-107">Azure Credentials</span></span>  
 <span data-ttu-id="fcf7d-108">**Verwaltungszertifikat**</span><span class="sxs-lookup"><span data-stu-id="fcf7d-108">**Management Certificate**</span></span>  
 <span data-ttu-id="fcf7d-109">Mit dieser Option geben Sie ein Zertifikat aus dem lokalen Zertifikatspeicher an, das mit dem Verwaltungszertifikat von Azure übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="fcf7d-109">Use this option to specify a certificate from the local certificate store that matches the management certificate from Azure.</span></span> <span data-ttu-id="fcf7d-110">Weitere Informationen zu Azure-Verwaltungszertifikaten finden Sie unter [Erstellen und Hochladen eines Verwaltungszertifikats für Azure](https://go.microsoft.com/fwlink/?LinkId=320781).</span><span class="sxs-lookup"><span data-stu-id="fcf7d-110">For more information on Azure management certificate, see [Create and Upload a Management Certificate for Azure](https://go.microsoft.com/fwlink/?LinkId=320781).</span></span>  
  
 <span data-ttu-id="fcf7d-111">**Abonnement**</span><span class="sxs-lookup"><span data-stu-id="fcf7d-111">**Subscription**</span></span>  
 <span data-ttu-id="fcf7d-112">Wählen Sie die zugehörige Azure-Abonnement-ID für das Verwaltungszertifikat aus dem lokalen Zertifikatspeicher, oder geben bzw. fügen Sie sie ein.</span><span class="sxs-lookup"><span data-stu-id="fcf7d-112">Select, type, or paste your Azure subscription ID that matches the management certificate from the local certificate store.</span></span>  
  
 <span data-ttu-id="fcf7d-113">**Veröffentlichungsprofil**</span><span class="sxs-lookup"><span data-stu-id="fcf7d-113">**Publishing Profile**</span></span>  
 <span data-ttu-id="fcf7d-114">Verwenden Sie diese Option, wenn ein Veröffentlichungsprofil auf Ihren Computer heruntergeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="fcf7d-114">Use this option if you have a publishing profile downloaded to your computer.</span></span> <span data-ttu-id="fcf7d-115">Bei dieser Option werden die Abonnement-ID und das Zertifikat automatisch aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="fcf7d-115">If you use this option, the subscription ID, and the certificate are auto populated.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="fcf7d-116">SQL Server unterstützt derzeit die Version 2.0 des Veröffentlichungsprofils.</span><span class="sxs-lookup"><span data-stu-id="fcf7d-116">SQL Server currently supports publishing profile version 2.0.</span></span> <span data-ttu-id="fcf7d-117">Weitere Informationen zum Herunterladen der unterstützten Version des Veröffentlichungsprofils finden Sie unter [Herunterladen des Veröffentlichungsprofils 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span><span class="sxs-lookup"><span data-stu-id="fcf7d-117">To download the supported version of the publishing profile, see [Download Publishing Profile 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span></span>  
  
## <a name="storage-account"></a><span data-ttu-id="fcf7d-118">Speicherkonto</span><span class="sxs-lookup"><span data-stu-id="fcf7d-118">Storage Account</span></span>  
 <span data-ttu-id="fcf7d-119">Geben Sie den Namen des Speicherkontos an, in dem die Sicherungsdateien gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fcf7d-119">Select the storage account you want to use to store the backup files on.</span></span>  
  
  
