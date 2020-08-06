---
title: So importieren Sie eine richtlinienbasierte Verwaltungsrichtlinie | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, import policy
ms.assetid: 850b7ef9-d2b7-4754-bf04-7cb419ffb776
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d83ed589e147c61b1692447aacb17535f18a5c9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609182"
---
# <a name="import-a-policy-based-management-policy"></a><span data-ttu-id="f9b43-102">Importieren einer Richtlinie der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="f9b43-102">Import a Policy-Based Management Policy</span></span>
  <span data-ttu-id="f9b43-103">In diesem Thema wird beschrieben, wie Sie eine Instanz einer Richtlinie der richtlinienbasierten Verwaltung mithilfe von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]importieren.</span><span class="sxs-lookup"><span data-stu-id="f9b43-103">This topic describes how to import a Policy-Based Management policy instance in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="f9b43-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="f9b43-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="f9b43-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="f9b43-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="f9b43-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f9b43-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="f9b43-107">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f9b43-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="f9b43-108">**Importieren einer Richtlinieninstanz mit:**</span><span class="sxs-lookup"><span data-stu-id="f9b43-108">**To import a policy instance, using:**</span></span>  
  
     [<span data-ttu-id="f9b43-109">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f9b43-109">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f9b43-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="f9b43-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f9b43-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f9b43-111">Limitations and Restrictions</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="f9b43-112">enthält Richtlinien, die verwendet werden können, um eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="f9b43-112">ships with policies that can be used to monitor an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f9b43-113">Diese Richtlinien sind standardmäßig nicht in [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]installiert, aber sie können aus ihrem Standardspeicherort C:\Programme\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033 importiert werden.</span><span class="sxs-lookup"><span data-stu-id="f9b43-113">By default, these policies are not installed on the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)], but they can be imported from the default location of C:\Program Files\Microsoft SQL Server\120\Tools\Policies\DatabaseEngine\1033.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f9b43-114">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f9b43-114">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f9b43-115">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f9b43-115">Permissions</span></span>  
 <span data-ttu-id="f9b43-116">Erfordert die Mitgliedschaft in der PolicyAdministratorRole-Rolle in der msdb-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="f9b43-116">Requires membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f9b43-117">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f9b43-117">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-import-a-policy-instance"></a><span data-ttu-id="f9b43-118">So importieren Sie eine Richtlinieninstanz</span><span class="sxs-lookup"><span data-stu-id="f9b43-118">To import a policy instance</span></span>  
  
1.  <span data-ttu-id="f9b43-119">Klicken Sie im **Objekt-Explorer**auf das Pluszeichen, um den Server zu erweitern, in dem sich die neu importierte Richtlinieninstanz befinden wird.</span><span class="sxs-lookup"><span data-stu-id="f9b43-119">In **Object Explorer**, click the plus sign to expand the server where the newly-imported policy instance will reside.</span></span>  
  
2.  <span data-ttu-id="f9b43-120">Klicken Sie auf das Pluszeichen, um den Ordner **Verwaltung** zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="f9b43-120">Click the plus sign to expand the **Management** folder.</span></span>  
  
3.  <span data-ttu-id="f9b43-121">Klicken Sie auf das Pluszeichen, um **Richtlinienverwaltung**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="f9b43-121">Click the plus sign to expand **Policy Management**.</span></span>  
  
4.  <span data-ttu-id="f9b43-122">Klicken Sie mit der rechten Maustaste auf den Ordner **Richtlinien** , und wählen Sie **Richtlinie importieren**aus.</span><span class="sxs-lookup"><span data-stu-id="f9b43-122">Right-click the **Policies** folder and select **Import Policy**.</span></span>  
  
5.  <span data-ttu-id="f9b43-123">Geben Sie im Dialogfeld **Importieren** den Pfad und den Namen der Datei ein, oder klicken Sie auf die Schaltfläche zum Durchsuchen ( **…** ), um die XML-Datei zu suchen, die die Richtlinie enthält, und wählen Sie dann die Datei aus.</span><span class="sxs-lookup"><span data-stu-id="f9b43-123">In the **Import** dialog box, type the path and name of the file; or use the Browse (**...**) button to locate the XML file that contains the policy, and then select the file.</span></span> <span data-ttu-id="f9b43-124">Weitere Informationen zu den Optionen im Dialogfeld **Importieren** finden Sie unter [Import Policies Dialog Box](import-policies-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="f9b43-124">For more information on the available options in the **Import** dialog box, see [Import Policies Dialog Box](import-policies-dialog-box.md).</span></span>  
  
6.  <span data-ttu-id="f9b43-125">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f9b43-125">When finished, click **OK**.</span></span>  
  
  
