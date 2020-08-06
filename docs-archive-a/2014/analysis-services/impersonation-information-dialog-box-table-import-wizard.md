---
title: Identitätswechsel Informationen (Dialog Feld, Tabellen Import-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.impersonationinfo.f1
ms.assetid: bee7eee5-0650-41f1-a372-5076ae97a58c
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5300f8b6106a7f29f51018b4e039c2a8c28aa729
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696286"
---
# <a name="impersonation-information-dialog-box-table-import-wizard"></a><span data-ttu-id="3efc2-102">Identitätswechselinformationen (Dialogfeld, Tabellenimport-Assistent)</span><span class="sxs-lookup"><span data-stu-id="3efc2-102">Impersonation Information Dialog Box (Table Import Wizard)</span></span>
  <span data-ttu-id="3efc2-103">Verwenden Sie die Seite **Identitätswechselinformationen** , um die Anmeldeinformationen anzugeben, mit denen [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] eine Verbindung mit der Datenquelle herstellt.</span><span class="sxs-lookup"><span data-stu-id="3efc2-103">Use the **Impersonation Information** page to specify the credentials that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] will use to connect to the data source.</span></span> <span data-ttu-id="3efc2-104">Weitere Informationen zum Identitätswechsel mit Anmeldeinformationen finden Sie unter [Impersonation &#40;SSAS Tabular&#41;](tabular-models/impersonation-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="3efc2-104">For more information about credentials impersonation, see [Impersonation &#40;SSAS Tabular&#41;](tabular-models/impersonation-ssas-tabular.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="3efc2-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="3efc2-105">Options</span></span>  
 <span data-ttu-id="3efc2-106">**Bestimmter Windows-Benutzername und bestimmtes Kennwort**</span><span class="sxs-lookup"><span data-stu-id="3efc2-106">**Specific Windows user name and password**</span></span>  
 <span data-ttu-id="3efc2-107">Wählen Sie diese Option aus, damit vom Tabellenmodell die Sicherheitsanmeldeinformationen eines angegebenen Windows-Benutzerkontos verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3efc2-107">Select this option to have the tabular model use the security credentials of a specified Windows user account.</span></span>  
  
 <span data-ttu-id="3efc2-108">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="3efc2-108">**User name**</span></span>  
 <span data-ttu-id="3efc2-109">Geben Sie die Domäne und den Name des zu verwendenden Benutzerkontos ein.</span><span class="sxs-lookup"><span data-stu-id="3efc2-109">Type the domain and name of the user account to be used.</span></span> <span data-ttu-id="3efc2-110">Verwenden Sie das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="3efc2-110">Use the following format:</span></span>  
  
 <span data-ttu-id="3efc2-111">*\<Domain name>* **\\** *\<User account name>*</span><span class="sxs-lookup"><span data-stu-id="3efc2-111">*\<Domain name>* **\\** *\<User account name>*</span></span>  
  
 <span data-ttu-id="3efc2-112">Die Option ist nur verfügbar, wenn die Option **Bestimmten Benutzernamen und bestimmtes Kennwort verwenden** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="3efc2-112">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="3efc2-113">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="3efc2-113">**Password**</span></span>  
 <span data-ttu-id="3efc2-114">Geben Sie das Kennwort des Benutzerkontos ein, das vom Tabellenmodell verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3efc2-114">Type the password of the user account to be used by the Tabular model.</span></span>  
  
 <span data-ttu-id="3efc2-115">Die Option ist nur verfügbar, wenn die Option **Bestimmten Benutzernamen und bestimmtes Kennwort verwenden** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="3efc2-115">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="3efc2-116">**Dienstkonto**</span><span class="sxs-lookup"><span data-stu-id="3efc2-116">**Service account**</span></span>  
 <span data-ttu-id="3efc2-117">Wählen Sie diese Option aus, damit die Sicherheitsanmeldeinformationen verwendet werden, die dem [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Dienst zugeordnet sind, der das Objekt verwaltet.</span><span class="sxs-lookup"><span data-stu-id="3efc2-117">Select this option to use the security credentials associated with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] service that manages the model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3efc2-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3efc2-118">See Also</span></span>  
 [<span data-ttu-id="3efc2-119">Identitätswechsel &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="3efc2-119">Impersonation &#40;SSAS Tabular&#41;</span></span>](tabular-models/impersonation-ssas-tabular.md)  
  
  
