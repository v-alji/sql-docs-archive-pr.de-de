---
title: Integration Services Parameter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Integration Services, parameters
ms.assetid: b1bb3ea3-8097-4e76-b9c2-78a0f46a23bc
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 76a5ebe7018fdc58f02a4d2454d40f172c752c4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724406"
---
# <a name="integration-services-parameters"></a><span data-ttu-id="7f8f1-102">Integration Services-Parameter</span><span class="sxs-lookup"><span data-stu-id="7f8f1-102">Integration Services Parameters</span></span>
  <span data-ttu-id="7f8f1-103">Für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] können Sie sich entscheiden, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Pakete auf dem Computer zu analysieren, oder [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Paketdateien im Dateisystem.</span><span class="sxs-lookup"><span data-stu-id="7f8f1-103">For [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you can decide to analyze [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages on the computer, or [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] package files in the file system.</span></span> <span data-ttu-id="7f8f1-104">Wenn Sie sich dafür entscheiden, Dateien im Dateisystem zu analysieren, müssen Sie einen Pfad zum Ordner angeben, der die [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Pakete enthält.</span><span class="sxs-lookup"><span data-stu-id="7f8f1-104">If you analyze files in the file system, provide a path to the folder that contains the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span>  
  
## <a name="options"></a><span data-ttu-id="7f8f1-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="7f8f1-105">Options</span></span>  
 <span data-ttu-id="7f8f1-106">**SSIS-Pakete auf dem Computer analysieren**</span><span class="sxs-lookup"><span data-stu-id="7f8f1-106">**Analyze SSIS packages on Computer**</span></span>  
 <span data-ttu-id="7f8f1-107">Wählen Sie diese Option aus, um [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Pakete auf dem Computer zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="7f8f1-107">Select this option to analyze [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages on the computer.</span></span> <span data-ttu-id="7f8f1-108">Diese Option ist standardmäßig ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="7f8f1-108">By default, this option is selected.</span></span>  
  
 <span data-ttu-id="7f8f1-109">**SSIS-Paketdateien analysieren**</span><span class="sxs-lookup"><span data-stu-id="7f8f1-109">**Analyze SSIS package files**</span></span>  
 <span data-ttu-id="7f8f1-110">Wählen Sie diese Option aus, um [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Pakete im Dateisystem zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="7f8f1-110">Select this option to analyze [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages in the file system.</span></span>  
  
 <span data-ttu-id="7f8f1-111">**Pfad zu SSIS-Paketen**</span><span class="sxs-lookup"><span data-stu-id="7f8f1-111">**Path to SSIS packages**</span></span>  
 <span data-ttu-id="7f8f1-112">Geben Sie einen UNC-Namen oder lokalen Pfad ein, unter dem sich die [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Pakete befinden.</span><span class="sxs-lookup"><span data-stu-id="7f8f1-112">Locate a UNC or local path that holds your [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="7f8f1-113">Sie müssen keine Dateinamen angeben.</span><span class="sxs-lookup"><span data-stu-id="7f8f1-113">You do not have to include file names.</span></span> <span data-ttu-id="7f8f1-114">Wenn nicht auf den eingegebenen Pfad zugegriffen werden kann, können Sie nicht auf **weiter**klicken.</span><span class="sxs-lookup"><span data-stu-id="7f8f1-114">If the path you have entered cannot be accessed, you cannot click **Next**.</span></span> <span data-ttu-id="7f8f1-115">Standardmäßig ist der Pfad leer.</span><span class="sxs-lookup"><span data-stu-id="7f8f1-115">By default, the path is blank.</span></span> <span data-ttu-id="7f8f1-116">Dieses Feld ist nur aktiviert, wenn Sie **SSIS-Paketdateien analysieren**auswählen.</span><span class="sxs-lookup"><span data-stu-id="7f8f1-116">This field is enabled only when you select **Analyze SSIS package files**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f8f1-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f8f1-117">See Also</span></span>  
 <span data-ttu-id="7f8f1-118">[Arbeiten mit Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="7f8f1-118">[Working with Upgrade Advisor](../../../2014/sql-server/install/working-with-upgrade-advisor.md) </span></span>  
 [<span data-ttu-id="7f8f1-119">Benutzeroberflächenreferenz des Upgrade Advisors</span><span class="sxs-lookup"><span data-stu-id="7f8f1-119">Upgrade Advisor User Interface Reference</span></span>](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md)  
  
  
