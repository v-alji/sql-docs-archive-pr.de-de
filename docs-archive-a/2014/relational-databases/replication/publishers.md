---
title: Verleger | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configuredistributionwizard.enablepublishers.f1
ms.assetid: 116cd6a5-32ac-4273-81a2-d184408e0f07
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 879fa3cc2ecadf56914928c6ae83600f513f6ddb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607638"
---
# <a name="publishers"></a><span data-ttu-id="09bfc-102">Herausgeber</span><span class="sxs-lookup"><span data-stu-id="09bfc-102">Publishers</span></span>
  <span data-ttu-id="09bfc-103">Sie können anderen Verlegern die Berechtigung zum Verwenden dieses Verteilers erteilen.</span><span class="sxs-lookup"><span data-stu-id="09bfc-103">You can give permission for other Publishers to use this Distributor.</span></span> <span data-ttu-id="09bfc-104">Beachten Sie, dass dieser Server nicht zu einem Verleger wird, wenn Sie es einem Verleger ermöglichen, diesen Server als Verteiler zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="09bfc-104">Be aware that enabling a Publisher to use this server as its remote Distributor does not make that server a Publisher.</span></span> <span data-ttu-id="09bfc-105">Sie müssen eine Verbindung mit dem Verleger herstellen, ihn für das Veröffentlichen konfigurieren und diesen Server als Verteiler auswählen.</span><span class="sxs-lookup"><span data-stu-id="09bfc-105">You must connect to the Publisher, configure it for publishing, and choose this server as the Distributor.</span></span> <span data-ttu-id="09bfc-106">Sie können den Verleger konfigurieren und mithilfe des Assistenten für neue Veröffentlichung einen Verteiler auswählen.</span><span class="sxs-lookup"><span data-stu-id="09bfc-106">You can configure the Publisher and choose a Distributor through the New Publication Wizard.</span></span>  
  
 <span data-ttu-id="09bfc-107">Die von Ihnen als Verleger ausgewählten Server verwenden die auf der Seite **Verteilungsdatenbank** dieses Assistenten ausgewählte Verteilungsdatenbank.</span><span class="sxs-lookup"><span data-stu-id="09bfc-107">The servers you select as Publishers will use the distribution database specified on the **Distribution Database** page of this wizard.</span></span> <span data-ttu-id="09bfc-108">Aktivieren Sie zu diesem Zeitpunkt nicht den Verleger, wenn Sie eine andere Verteilungsdatenbank verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="09bfc-108">If you want to use a different distribution database, do not enable the Publisher at this time.</span></span> <span data-ttu-id="09bfc-109">Verwenden Sie stattdessen das Dialogfeld **Verteilereigenschaften** , um Verleger nach dem Abschließen des Verteilungskonfigurations-Assistenten hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="09bfc-109">Instead, use the **Distributor Properties** dialog box to add Publishers after you complete the Configure Distribution Wizard.</span></span>  
  
## <a name="options"></a><span data-ttu-id="09bfc-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="09bfc-110">Options</span></span>  
 <span data-ttu-id="09bfc-111">**Verleger**</span><span class="sxs-lookup"><span data-stu-id="09bfc-111">**Publishers**</span></span>  
 <span data-ttu-id="09bfc-112">Wählen Sie die Server aus, die diesen Verteiler verwenden dürfen.</span><span class="sxs-lookup"><span data-stu-id="09bfc-112">Select the servers that are allowed to use this Distributor.</span></span> <span data-ttu-id="09bfc-113">Klicken Sie neben einem Verleger auf die Eigenschaftenschaltfläche(**die Schaltfläche mit den drei Punkten**), um zusätzliche Eigenschaften anzuzeigen und festzulegen.</span><span class="sxs-lookup"><span data-stu-id="09bfc-113">Click the properties button (**...**) next to a Publisher to view and set additional properties.</span></span>  
  
 <span data-ttu-id="09bfc-114">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="09bfc-114">**Add**</span></span>  
 <span data-ttu-id="09bfc-115">Wenn der von Ihnen gewünschte Server nicht in der Liste enthalten ist, klicken Sie auf **Hinzufügen**, um einen [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Verleger oder einen Oracle-Verleger zur Liste der verfügbaren Verleger hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="09bfc-115">If the server you want to allow is not listed, click **Add** to add a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Publisher or Oracle Publisher to the list of available Publishers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09bfc-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="09bfc-116">See Also</span></span>  
 <span data-ttu-id="09bfc-117">[Verteilung konfigurieren](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="09bfc-117">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="09bfc-118">[Konfigurieren der Veröffentlichung und der Verteilung](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="09bfc-118">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="09bfc-119">[Anzeigen und Ändern der Verteiler- und Verlegereigenschaften](view-and-modify-distributor-and-publisher-properties.md) </span><span class="sxs-lookup"><span data-stu-id="09bfc-119">[View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md) </span></span>  
 [<span data-ttu-id="09bfc-120">Erstellen einer Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="09bfc-120">Create a Publication</span></span>](publish/create-a-publication.md)  
  
  
