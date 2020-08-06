---
title: Kopieren eines Facet-Status der richtlinienbasierten Verwaltung in eine XML-Datei | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Policy-Based Management, copy facet state to XML file
ms.assetid: 7d604ab1-6dd6-4f8e-a79c-eba99ab106fd
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 7be2332d9a2507a079d85a3424bda3a387609ca7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699465"
---
# <a name="copy-a-policy-based-management-facet-state-to-an-xml-file"></a><span data-ttu-id="ad830-102">Kopieren eines Facet-Status der richtlinienbasierten Verwaltung in eine XML-Datei</span><span class="sxs-lookup"><span data-stu-id="ad830-102">Copy a Policy-Based Management Facet State to an XML File</span></span>
  <span data-ttu-id="ad830-103">In diesem Thema wird beschrieben, wie Sie den Status eines Facets der richtlinienbasierten Verwaltung mithilfe von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] in eine XML-Datei in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]kopieren.</span><span class="sxs-lookup"><span data-stu-id="ad830-103">This topic describes how to how to copy the state of a Policy-Based Management facet to an XML file in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ad830-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="ad830-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="ad830-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="ad830-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="ad830-106">Security</span><span class="sxs-lookup"><span data-stu-id="ad830-106">Security</span></span>](#Security)  
  
-   <span data-ttu-id="ad830-107">**Kopieren eines Facet-Status in eine XML-Datei mit:**</span><span class="sxs-lookup"><span data-stu-id="ad830-107">**To copy a facet state to an XML file, using:**</span></span>  
  
     [<span data-ttu-id="ad830-108">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad830-108">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="ad830-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="ad830-109">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="ad830-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ad830-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="ad830-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="ad830-111">Permissions</span></span>  
 <span data-ttu-id="ad830-112">Die Verfahren in diesem Thema erfordern die Mitgliedschaft in der PolicyAdministratorRole-Rolle in der msdb-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ad830-112">The procedures in this topic require membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ad830-113">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ad830-113">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-copy-a-facet-state-to-an-xml-file"></a><span data-ttu-id="ad830-114">So kopieren Sie einen Facet-Status in eine XML-Datei</span><span class="sxs-lookup"><span data-stu-id="ad830-114">To copy a facet state to an XML file</span></span>  
  
1.  <span data-ttu-id="ad830-115">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ein Instanzobjekt, eine Datenbank oder ein Datenbankobjekt, und klicken Sie dann auf **Facets**.</span><span class="sxs-lookup"><span data-stu-id="ad830-115">In Object Explorer, right-click an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], instance object, database, or database object, and then click **Facets**.</span></span>  
  
2.  <span data-ttu-id="ad830-116">Klicken Sie im Dialogfeld **Facetten anzeigen-**_object_name_ auf **aktuellen Status als Richtlinie exportieren**.</span><span class="sxs-lookup"><span data-stu-id="ad830-116">In the **View Facets -**_object_name_ dialog box, click **Export Current State as Policy**.</span></span>  
  
3.  <span data-ttu-id="ad830-117">Geben Sie im Dialogfeld **Als Richtlinie exportieren** den Pfad und den Namen der Datei ein, oder klicken Sie auf die Schaltfläche mit den drei Punkten (**...**), um die Datei zu suchen, und geben Sie dann den Namen der XML-Datei ein.</span><span class="sxs-lookup"><span data-stu-id="ad830-117">In the **Export as Policy** dialog box, type the path and name of the file; or use the Browse (**...**) button to locate the file, and then type the name of the XML file.</span></span> <span data-ttu-id="ad830-118">Weitere Informationen zu den Optionen in diesem Dialogfeld finden Sie unter [Export As Policy Dialog Box](export-as-policy-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="ad830-118">For more information on the available options in this dialog box, see [Export As Policy Dialog Box](export-as-policy-dialog-box.md)</span></span>  
  
4.  <span data-ttu-id="ad830-119">Wenn Sie fertig sind, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="ad830-119">When finished, click **OK**.</span></span>  
  
  
