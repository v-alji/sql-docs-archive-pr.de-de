---
title: Löschen einer Version (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- versions [Master Data Services], deleting
- deleting versions [Master Data Services]
ms.assetid: 2a4eeffe-8379-4744-ad44-c27d8c8ac9a8
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f83a3bc396b2a13ac7ac03ef653b16a0d556189a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622187"
---
# <a name="delete-a-version-master-data-services"></a><span data-ttu-id="bbee2-102">Löschen einer Version (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="bbee2-102">Delete a Version (Master Data Services)</span></span>
  <span data-ttu-id="bbee2-103">Löschen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eine Version, wenn Sie sicher sind, dass Sie die der Version zugeordneten Masterdaten nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="bbee2-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete a version when you are sure you no longer need the master data associated with the version.</span></span> <span data-ttu-id="bbee2-104">Nachdem Sie eine Version gelöscht haben, können Sie die zugeordneten Masterdaten nicht abrufen.</span><span class="sxs-lookup"><span data-stu-id="bbee2-104">After you delete a version, you cannot retrieve the associated master data.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="bbee2-105">Wenn ein Modell nur über eine Version verfügt, und Sie diese löschen, wird das Modell unbrauchbar.</span><span class="sxs-lookup"><span data-stu-id="bbee2-105">If a model has only one version and you delete it, the model becomes unusable.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bbee2-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="bbee2-106">Prerequisites</span></span>  
 <span data-ttu-id="bbee2-107">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="bbee2-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="bbee2-108">Sie müssen berechtigt sein, die mdm.viw_SYSTEM_SCHEMA_VERSION-Sicht anzuzeigen und die gespeicherte Prozedur mds.udpVersionDelete in der [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Datenbank auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bbee2-108">You must have permission to view the mdm.viw_SYSTEM_SCHEMA_VERSION view and to execute the mds.udpVersionDelete stored procedure in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span> <span data-ttu-id="bbee2-109">Weitere Informationen finden Sie unter [Sicherheit von Datenbankobjekten &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="bbee2-109">For more information, see [Database Object Security &#40;Master Data Services&#41;](database-object-security-master-data-services.md).</span></span>  
  
### <a name="to-delete-a-version"></a><span data-ttu-id="bbee2-110">So löschen Sie eine Version</span><span class="sxs-lookup"><span data-stu-id="bbee2-110">To delete a version</span></span>  
  
1.  <span data-ttu-id="bbee2-111">Öffnen Sie [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] , und stellen Sie eine Verbindung mit der [!INCLUDE[ssDE](../includes/ssde-md.md)] -Instanz für die [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Datenbank her.</span><span class="sxs-lookup"><span data-stu-id="bbee2-111">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] instance for your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database.</span></span>  
  
2.  <span data-ttu-id="bbee2-112">Öffnen Sie die mdm.viw_SYSTEM_SCHEMA_VERSION-Sicht.</span><span class="sxs-lookup"><span data-stu-id="bbee2-112">Open the mdm.viw_SYSTEM_SCHEMA_VERSION view.</span></span>  
  
3.  <span data-ttu-id="bbee2-113">Suchen Sie die Version des Modells, die Sie löschen möchten, und kopieren Sie den Wert im Feld **ID** .</span><span class="sxs-lookup"><span data-stu-id="bbee2-113">Find the version of the model you want to delete and copy the value in the **ID** field.</span></span>  
  
4.  <span data-ttu-id="bbee2-114">Erstellen Sie eine neue Abfrage.</span><span class="sxs-lookup"><span data-stu-id="bbee2-114">Create a new query.</span></span>  
  
5.  <span data-ttu-id="bbee2-115">Geben Sie den folgenden Text ein, indem Sie *version_ID* durch den in Schritt 2 kopierten Wert ersetzen.</span><span class="sxs-lookup"><span data-stu-id="bbee2-115">Type the following text, replacing *version_ID* with the value you copied in step 2.</span></span>  
  
    ```  
    EXEC [mdm].[udpVersionDelete] @Version_ID='version_ID'  
    ```  
  
6.  <span data-ttu-id="bbee2-116">Führen Sie die Abfrage aus.</span><span class="sxs-lookup"><span data-stu-id="bbee2-116">Run the query.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="bbee2-117">Es kann einige Minuten dauern, bis die Änderung in der Webanwendung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="bbee2-117">You may have to wait a few minutes before the Web application reflects the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbee2-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bbee2-118">See Also</span></span>  
 <span data-ttu-id="bbee2-119">[Versionen &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="bbee2-119">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 [<span data-ttu-id="bbee2-120">Kopieren einer Version &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="bbee2-120">Copy a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/copy-a-version-master-data-services.md)  
  
  
