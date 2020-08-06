---
title: Verbindung mit Azure Storage herstellen (Wiederherstellen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: backup-restore
ms.topic: conceptual
f1_keywords:
- sql12.swb.restore.connectstorage.f1
ms.assetid: c0b7d7c8-b878-4b7f-8120-d0c6917b583f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: dff9730d6592381b1c8e8a1cf7ee45ad7532a440
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622713"
---
# <a name="connect-to-azure-storage-restore"></a><span data-ttu-id="456c9-102">Verbinden mit Azure Storage (Wiederherstellen)</span><span class="sxs-lookup"><span data-stu-id="456c9-102">Connect to Azure Storage (Restore)</span></span>
  <span data-ttu-id="456c9-103">Über das Dialogfeld können Sie die Verbindung zum Azure-Speicherkonto angeben, um den Dateispeicher im Azure-Speicherkonto abzurufen.</span><span class="sxs-lookup"><span data-stu-id="456c9-103">The dialog box allows you to specify the connection to Azure storage account information in order to retrieve the files storage in the Azure storage account.</span></span> <span data-ttu-id="456c9-104">Nachdem Sie die erforderlichen Informationen angegeben haben, klicken Sie auf **Verbinden**, um die Verbindung zum Azure-Speicher herzustellen.</span><span class="sxs-lookup"><span data-stu-id="456c9-104">After specifying the required information, click **Connect** to establish the connection to Azure storage.</span></span>  
  
## <a name="azure-storage-account"></a><span data-ttu-id="456c9-105">Azure Storage-Konto</span><span class="sxs-lookup"><span data-stu-id="456c9-105">Azure Storage Account</span></span>  
 <span data-ttu-id="456c9-106">**Speicherkonto**</span><span class="sxs-lookup"><span data-stu-id="456c9-106">**Storage account**</span></span>  
 <span data-ttu-id="456c9-107">Geben Sie den Namen des Azure-Speicherkontos an, das Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="456c9-107">Select, type or paste the name of the Azure storage account you want to use.</span></span> <span data-ttu-id="456c9-108">Im Dropdownfeld werden die zuvor verwendeten Konten aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="456c9-108">The drop down box lists the accounts previously used.</span></span>  
  
 <span data-ttu-id="456c9-109">**Kontoschlüssel**</span><span class="sxs-lookup"><span data-stu-id="456c9-109">**Account key**</span></span>  
 <span data-ttu-id="456c9-110">Geben Sie den Zugriffsschlüssel für das Azure-Speicherkonto an.</span><span class="sxs-lookup"><span data-stu-id="456c9-110">Specify the Azure storage account access key.</span></span>  
  
 <span data-ttu-id="456c9-111">**Sichere Endpunkte (HTTPS) verwenden** – Kontrollkästchen</span><span class="sxs-lookup"><span data-stu-id="456c9-111">**Use secure endpoints (HTTPS)** check box</span></span>  
 <span data-ttu-id="456c9-112">Wählen Sie diese Option, um eine sichere Verbindung zu Azure Storage herzustellen (empfohlen).</span><span class="sxs-lookup"><span data-stu-id="456c9-112">Select this option to make a secure connection to Azure storage - recommended.</span></span>  
  
 <span data-ttu-id="456c9-113">**Kontoschlüssel speichern** – Kontrollkästchen</span><span class="sxs-lookup"><span data-stu-id="456c9-113">**Save account key** check box</span></span>  
 <span data-ttu-id="456c9-114">Aktivieren Sie dieses Kontrollkästchen, wenn SQL Server den Zugriffsschlüssel für dieses Speicherkonto speichern soll.</span><span class="sxs-lookup"><span data-stu-id="456c9-114">Select this check box if you want SQL Server to remember the access key for this storage account.</span></span>  
  
### <a name="sql-credential"></a><span data-ttu-id="456c9-115">SQL-Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="456c9-115">SQL Credential</span></span>  
 <span data-ttu-id="456c9-116">**Auswählen vorhandener Anmeldeinformationen**</span><span class="sxs-lookup"><span data-stu-id="456c9-116">**Select an existing credential**</span></span>  
 <span data-ttu-id="456c9-117">Wählen Sie ein vorhandenes Objekt mit passenden SQL-Anmeldeinformationen für den Kontonamen und den Zugriffsschlüssel aus.</span><span class="sxs-lookup"><span data-stu-id="456c9-117">Select an existing SQL Credential that matches the storage account and account key information.</span></span>  
  
 <span data-ttu-id="456c9-118">**Erstellen von neuen Anmeldeinformationen**</span><span class="sxs-lookup"><span data-stu-id="456c9-118">**Create a new Credential**</span></span>  
 <span data-ttu-id="456c9-119">Wählen Sie diese Option aus, um neue Anmeldeinformationen auf Basis des Speicherkontos und des Kontoschlüssels zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="456c9-119">Select this option to create a new credential using the storage account and account key information.</span></span> <span data-ttu-id="456c9-120">Geben Sie den Namen der neuen Anmeldeinformationen im **Anmeldeinformationsname** -Feld an.</span><span class="sxs-lookup"><span data-stu-id="456c9-120">Specify the name of the new credential in the **Credential Name** field.</span></span>  
  
  
