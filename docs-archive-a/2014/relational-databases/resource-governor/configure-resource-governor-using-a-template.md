---
title: Konfigurieren der Ressourcenkontrolle mit einer Vorlage | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- Resource Governor, templates
ms.assetid: f342dec2-d1d6-483e-b44e-98eb7d168b5e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 62edb23cf55a953cb0fef54f002f8eaaa16f58ec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621466"
---
# <a name="configure-resource-governor-using-a-template"></a><span data-ttu-id="62bc3-102">Konfigurieren der Ressourcenkontrolle mit einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="62bc3-102">Configure Resource Governor Using a Template</span></span>
  <span data-ttu-id="62bc3-103">Sie können die Ressourcenkontrolle mit einer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]bereitgestellten Vorlage konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="62bc3-103">You can configure Resource Governor by using a template that is provided in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
-   <span data-ttu-id="62bc3-104">**Vorbereitungen:**  [Berechtigungen](#Permissions)</span><span class="sxs-lookup"><span data-stu-id="62bc3-104">**Before you begin:**  [Permissions](#Permissions)</span></span>  
  
-   <span data-ttu-id="62bc3-105">**Erstellen einer Arbeitsauslastungsgruppe mit** [einer Vorlage](#ConfRGTemplate)</span><span class="sxs-lookup"><span data-stu-id="62bc3-105">**To create a workload group, using:**  [a template](#ConfRGTemplate)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="62bc3-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="62bc3-106">Before You Begin</span></span>  
 <span data-ttu-id="62bc3-107">Gehen Sie wie folgt vor, um eine Vorlage zu öffnen und zu bearbeiten, mit der ein Ressourcenpool und eine Arbeitsauslastungsgruppe für diesen Pool erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="62bc3-107">Use the following steps to open and modify a template that creates a resource pool and a workload group for the pool.</span></span> <span data-ttu-id="62bc3-108">Darüber hinaus können Sie mit dieser Vorlage eine benutzerdefinierte Klassifizierungsfunktion erstellen, die neue Verbindungen entweder in die Standardgruppe oder in die von Ihnen erstellte Arbeitsauslastungsgruppe leitet.</span><span class="sxs-lookup"><span data-stu-id="62bc3-108">In addition, this template enables you to create a classifier user-defined function that routes new connections to either the default group or the workload group that you create.</span></span>  
  
###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="62bc3-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="62bc3-109">Permissions</span></span>  
 <span data-ttu-id="62bc3-110">Die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen der Ressourcenkontrolle in der Vorlage erfordern die CONTROL SERVER-Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="62bc3-110">The resource governor [!INCLUDE[tsql](../../includes/tsql-md.md)] statements in the template require CONTROL SERVER permission.</span></span>  
  
##  <a name="configure-resource-governor-using-a-template"></a><a name="ConfRGTemplate"></a> <span data-ttu-id="62bc3-111">Konfigurieren der Ressourcenkontrolle mit einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="62bc3-111">Configure Resource Governor Using a Template</span></span>  
 <span data-ttu-id="62bc3-112">**So konfigurieren Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span><span class="sxs-lookup"><span data-stu-id="62bc3-112">**To configure resource governor by using a template in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]**</span></span>  
  
1.  <span data-ttu-id="62bc3-113">Klicken Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]im Menü **Ansicht** auf **Vorlagen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="62bc3-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="62bc3-114">Erweitern Sie unter **Vorlagen-Explorer**den Eintrag **Resource Governor**, und doppelklicken Sie auf **Resource Governor konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="62bc3-114">In **Template Explorer**, expand **Resource Governor**, and then double-click **Configure Resource Governor**.</span></span>  
  
3.  <span data-ttu-id="62bc3-115">Geben Sie unter **Verbindung mit Datenbank-Engine herstellen**die erforderlichen Informationen ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="62bc3-115">In **Connect to Database Engine**, enter the required information, and then click **OK**.</span></span> <span data-ttu-id="62bc3-116">Die Vorlage Configure Resource Governor.sql wird im Abfrage-Editor bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="62bc3-116">The template Configure Resource Governor.sql is provided in the Query Editor.</span></span> <span data-ttu-id="62bc3-117">Verwenden Sie diese Vorlage, um einen Ressourcenpool, eine Arbeitsauslastungsgruppe und eine Klassifizierungsfunktion zu erstellen und zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="62bc3-117">Use this template to create and configure a resource pool, a workload group, and a classifier function.</span></span>  
  
4.  <span data-ttu-id="62bc3-118">Wenn Sie die Werte in der Vorlage ändern möchten, drücken Sie die Tastenkombination STRG+UMSCHALT+M.</span><span class="sxs-lookup"><span data-stu-id="62bc3-118">To change the values in the template, press CTRL+SHIFT+M.</span></span> <span data-ttu-id="62bc3-119">Geben Sie im Fenster **Werte für Vorlagenparameter angeben** die gewünschten Werte ein.</span><span class="sxs-lookup"><span data-stu-id="62bc3-119">In the **Specify Values for Template Parameters** window, enter the values that you want to use.</span></span>  
  
5.  <span data-ttu-id="62bc3-120">Klicken Sie auf **OK**, um die an der Vorlage vorgenommenen Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="62bc3-120">To save the changes that you make to the template, click **OK**.</span></span>  
  
6.  <span data-ttu-id="62bc3-121">Klicken Sie auf **Ausführen**, um die Abfrage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="62bc3-121">To run the query, click **Execute**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62bc3-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="62bc3-122">See Also</span></span>  
 <span data-ttu-id="62bc3-123">[Resource Governor](resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="62bc3-123">[Resource Governor](resource-governor.md) </span></span>  
 <span data-ttu-id="62bc3-124">[Aktivieren der Ressourcenkontrolle](enable-resource-governor.md) </span><span class="sxs-lookup"><span data-stu-id="62bc3-124">[Enable Resource Governor](enable-resource-governor.md) </span></span>  
 <span data-ttu-id="62bc3-125">[Ressourcenpool für die Ressourcenkontrolle](resource-governor-resource-pool.md) </span><span class="sxs-lookup"><span data-stu-id="62bc3-125">[Resource Governor Resource Pool](resource-governor-resource-pool.md) </span></span>  
 <span data-ttu-id="62bc3-126">[Arbeitsauslastungsgruppe der Ressourcenkontrolle](resource-governor-workload-group.md) </span><span class="sxs-lookup"><span data-stu-id="62bc3-126">[Resource Governor Workload Group](resource-governor-workload-group.md) </span></span>  
 <span data-ttu-id="62bc3-127">[Klassifizierungsfunktion der Ressourcenkontrolle](resource-governor-classifier-function.md) </span><span class="sxs-lookup"><span data-stu-id="62bc3-127">[Resource Governor Classifier Function](resource-governor-classifier-function.md) </span></span>  
 <span data-ttu-id="62bc3-128">[Anzeigen der Eigenschaften der Ressourcenkontrolle](view-resource-governor-properties.md) </span><span class="sxs-lookup"><span data-stu-id="62bc3-128">[View Resource Governor Properties](view-resource-governor-properties.md) </span></span>  
 <span data-ttu-id="62bc3-129">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="62bc3-129">[CREATE RESOURCE POOL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-resource-pool-transact-sql) </span></span>  
 <span data-ttu-id="62bc3-130">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="62bc3-130">[CREATE WORKLOAD GROUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-workload-group-transact-sql) </span></span>  
 <span data-ttu-id="62bc3-131">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="62bc3-131">[CREATE FUNCTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-function-transact-sql) </span></span>  
 [<span data-ttu-id="62bc3-132">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="62bc3-132">ALTER RESOURCE GOVERNOR &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-resource-governor-transact-sql)  
  
  
