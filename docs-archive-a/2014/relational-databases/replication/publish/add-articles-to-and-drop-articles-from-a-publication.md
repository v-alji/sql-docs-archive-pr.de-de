---
title: Hinzufügen von Artikeln zu einer Veröffentlichung und Löschen von Artikeln aus einer Veröffentlichung (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- articles [SQL Server replication], dropping
- deleting articles
- dropping articles
- adding articles
- articles [SQL Server replication], adding
ms.assetid: d5a3e536-62d2-4473-a178-877ba52f7d7f
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f7af1cac1f3ee8ecc9cb79632f8a4ef1e66ec82f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622567"
---
# <a name="add-articles-to-and-drop-articles-from-a-publication-sql-server-management-studio"></a><span data-ttu-id="f9252-102">Hinzufügen von Artikeln zu einer Veröffentlichung und Löschen von Artikeln aus einer Veröffentlichung (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f9252-102">Add Articles to and Drop Articles from a Publication (SQL Server Management Studio)</span></span>
  <span data-ttu-id="f9252-103">Sie können einer Veröffentlichung bereits bei Ihrer Erstellung im Assistenten für neue Veröffentlichung Artikel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f9252-103">Initially add articles to a publication when you create it in the New Publication Wizard.</span></span> <span data-ttu-id="f9252-104">Weitere Informationen zum Zugreifen auf diesen Assistenten finden Sie unter [Erstellen einer Veröffentlichung](create-a-publication.md).</span><span class="sxs-lookup"><span data-stu-id="f9252-104">For more information about using this wizard, see [Create a Publication](create-a-publication.md).</span></span>  
  
 <span data-ttu-id="f9252-105">Zum Hinzufügen und Löschen von Artikeln zu bzw. aus einer bereits erstellten Veröffentlichung steht Ihnen die Seite **Artikel** des Dialogfelds **Veröffentlichungseigenschaften - \<Publication>** zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f9252-105">After a publication is created, add and delete articles on the **Articles** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="f9252-106">Weitere Informationen zum Zugreifen auf dieses Dialogfeld finden Sie unter [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f9252-106">For more information about accessing this dialog box, see [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span> <span data-ttu-id="f9252-107">Informationen zu Überlegungen für das Hinzufügen und Löschen von Artikeln finden Sie unter [Hinzufügen und Löschen von Artikeln aus vorhandenen Veröffentlichungen](add-articles-to-and-drop-articles-from-existing-publications.md).</span><span class="sxs-lookup"><span data-stu-id="f9252-107">For information about the considerations for adding and dropping articles, see [Add Articles to and Drop Articles from Existing Publications](add-articles-to-and-drop-articles-from-existing-publications.md).</span></span>  
  
### <a name="to-add-an-article-after-a-publication-is-created"></a><span data-ttu-id="f9252-108">So fügen Sie einer bereits erstellten Veröffentlichung einen Artikel hinzu</span><span class="sxs-lookup"><span data-stu-id="f9252-108">To add an article after a publication is created</span></span>  
  
1.  <span data-ttu-id="f9252-109">Deaktivieren Sie auf der Seite **Artikel** des Dialogfelds **Veröffentlichungseigenschaften - \<Publication>** die Option **Nur aktivierte Objekte in der Liste anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f9252-109">On the **Articles** page of the **Publication Properties - \<Publication>** dialog box, clear the **Show only checked objects in the list** check box.</span></span> <span data-ttu-id="f9252-110">Auf diese Weise werden nur die nicht veröffentlichten Objekte in der Veröffentlichungsdatenbank angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f9252-110">This allows you to see the unpublished objects in the publication database.</span></span>  
  
2.  <span data-ttu-id="f9252-111">Markieren Sie die Kontrollkästchen für alle Artikel, die Sie der Veröffentlichung hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="f9252-111">Select the check box next to each article you want to add.</span></span>  
  
3.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
### <a name="to-delete-an-article"></a><span data-ttu-id="f9252-112">So löschen Sie einen Artikel</span><span class="sxs-lookup"><span data-stu-id="f9252-112">To delete an article</span></span>  
  
1.  <span data-ttu-id="f9252-113">Deaktivieren Sie auf der Seite **Artikel** des Dialogfelds **Veröffentlichungseigenschaften - \<Publication>** die Kontrollkästchen für alle Artikel, die aus der Veröffentlichung gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f9252-113">On the **Articles** page of the **Publication Properties - \<Publication>** dialog box, clear the check box next to each article you want to delete.</span></span>  
  
2.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f9252-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f9252-114">See Also</span></span>  
 <span data-ttu-id="f9252-115">[Define an Article](define-an-article.md) </span><span class="sxs-lookup"><span data-stu-id="f9252-115">[Define an Article](define-an-article.md) </span></span>  
 [<span data-ttu-id="f9252-116">Veröffentlichen von Daten und Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="f9252-116">Publish Data and Database Objects</span></span>](publish-data-and-database-objects.md)  
  
  
