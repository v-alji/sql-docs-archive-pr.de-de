---
title: 'Lektion 2: Auswerten von Best Practices-Richtlinien auf einer geplanten Basis | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 37ffad63-d6db-4609-8deb-786200659554
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: a454e38ec2f07bf9867183a3894ac4ea001a942e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615723"
---
# <a name="lesson-2-evaluate-best-practices-policies-on-a-scheduled-basis"></a><span data-ttu-id="bf21f-102">Lektion 2: Auswerten von Best Practices-Richtlinien auf Basis eines Zeitplans</span><span class="sxs-lookup"><span data-stu-id="bf21f-102">Lesson 2: Evaluate Best Practices Policies on a Scheduled Basis</span></span>
  <span data-ttu-id="bf21f-103">Sie können geplante Auswertungen von Best Practices-Richtlinien für mindestens eine Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="bf21f-103">You can configure scheduled evaluations of best practices policies on one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="bf21f-104">Damit Best Practices-Richtlinien basierend auf einem Zeitplan ausgeführt werden können, müssen Sie die Richtlinien in die Zielinstanz importieren.</span><span class="sxs-lookup"><span data-stu-id="bf21f-104">To configure best practices policies to run on a scheduled basis, you must import the policies into the target instance.</span></span>  
  
 <span data-ttu-id="bf21f-105">Um geplante Richtlinien auf mehreren Servern bereitzustellen, können Sie die Richtlinien in eine Instanz importieren, die Zeitpläne für jede Richtlinie konfigurieren, die geplanten Richtlinien in einen Ordner exportieren und die geplanten Richtlinien dann über registrierte Server auf den Zielinstanzen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="bf21f-105">To deploy scheduled policies to multiple servers, you can import the policies to one instance, configure the schedules for each policy, export the scheduled policies to a folder, and then deploy the scheduled policies to target instances through Registered Servers.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="bf21f-106">Auf den Zielinstanzen muss [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] oder eine höhere Version ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bf21f-106">The target instances must be running [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] or a later version.</span></span> <span data-ttu-id="bf21f-107">Die Automatisierung erfordert, dass die Richtlinien lokal auf einer Instanz gespeichert werden. Dies wird von älteren [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Versionen vor [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)]nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bf21f-107">Automation requires the policies to be stored locally on the instance, which is not supported by versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that are earlier than [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="bf21f-108">In dieser Lektion führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="bf21f-108">In this lesson, you will do the following:</span></span>  
  
-   <span data-ttu-id="bf21f-109">Importieren der Best Practices-Richtlinien in eine Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf21f-109">Import the best practices policies into an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="bf21f-110">Konfigurieren der Richtlinien für die Ausführung auf Grundlage eines Zeitplans.</span><span class="sxs-lookup"><span data-stu-id="bf21f-110">Configure the policies to run on a schedule.</span></span>  
  
-   <span data-ttu-id="bf21f-111">Bereitstellen der geplanten Best Practices-Richtlinien auf mehreren Instanzen über registrierte Server.</span><span class="sxs-lookup"><span data-stu-id="bf21f-111">Deploy the scheduled best practices policies to multiple instances through Registered Servers.</span></span>  
  
 <span data-ttu-id="bf21f-112">Diese Lektion enthält die folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="bf21f-112">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="bf21f-113">Importieren der Richtlinien auf eine einzelne Instanz</span><span class="sxs-lookup"><span data-stu-id="bf21f-113">Import the Policies to a Single Instance</span></span>](../../2014/tutorials/import-the-policies-to-a-single-instance.md)  
  
-   [<span data-ttu-id="bf21f-114">Planen der Richtlinien</span><span class="sxs-lookup"><span data-stu-id="bf21f-114">Schedule the Policies</span></span>](../../2014/tutorials/schedule-the-policies.md)  
  
-   [<span data-ttu-id="bf21f-115">Bereitstellen geplanter Richtlinien auf mehreren Instanzen</span><span class="sxs-lookup"><span data-stu-id="bf21f-115">Deploy Scheduled Policies to Multiple Instances</span></span>](../../2014/tutorials/deploy-scheduled-policies-to-multiple-instances.md)  
  
## <a name="see-also"></a><span data-ttu-id="bf21f-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bf21f-116">See Also</span></span>  
 [<span data-ttu-id="bf21f-117">Verwalten mehrerer Server mithilfe von zentralen Verwaltungs Servern</span><span class="sxs-lookup"><span data-stu-id="bf21f-117">Administer Multiple Servers Using Central Management Servers</span></span>](../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
