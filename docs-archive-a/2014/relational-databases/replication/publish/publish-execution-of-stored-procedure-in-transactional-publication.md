---
title: Veröffentlichen der Ausführung einer gespeicherten Prozedur in einer Transaktions Veröffentlichung (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- publishing [SQL Server replication], stored procedure execution
- stored procedures [SQL Server replication], publishing
ms.assetid: 1d3a3525-0bc5-466f-b097-5359dc74432d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 44310d45a7049701a6aecfa73301b15b0021ac6f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609803"
---
# <a name="publish-the-execution-of-a-stored-procedure-in-a-transactional-publication-sql-server-management-studio"></a><span data-ttu-id="5538e-102">Veröffentlichen der Ausführung einer gespeicherten Prozedur in einer Transaktionsveröffentlichung (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="5538e-102">Publish the Execution of a Stored Procedure in a Transactional Publication (SQL Server Management Studio)</span></span>
  <span data-ttu-id="5538e-103">Im Dialogfeld **Artikeleigenschaften - \<Article>** können Sie angeben, dass die Ausführung einer gespeicherten Prozedur (und nicht nur ihre Definition) veröffentlicht werden soll.</span><span class="sxs-lookup"><span data-stu-id="5538e-103">Specify that the execution of a stored procedure (rather than just its definition) should be published in the **Article Properties - \<Article>** dialog box.</span></span> <span data-ttu-id="5538e-104">Dieses Dialogfeld ist im Assistenten für neue Veröffentlichungen sowie über das Dialogfeld **Veröffentlichungseigenschaften - \<Publication>** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5538e-104">This dialog box is available in the New Publication Wizard and the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="5538e-105">Weitere Informationen zum Verwenden des Assistenten sowie Zugriff auf das Dialogfeld finden Sie unter [Erstellen einer Veröffentlichung](create-a-publication.md) und [Anzeigen und Ändern von Veröffentlichungseigenschaften](view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="5538e-105">For more information about using the wizard and accessing the dialog box, see [Create a Publication](create-a-publication.md) and [View and Modify Publication Properties](view-and-modify-publication-properties.md).</span></span>  
  
 <span data-ttu-id="5538e-106">Die Definition der Prozedur (die CREATE PROCEDURE-Anweisung) wird beim Initialisieren des Abonnements auf den Abonnenten repliziert. Wenn die Prozedur dann auf dem Verleger ausgeführt wird, führt die Replikation auch die entsprechende Prozedur auf dem Abonnenten aus.</span><span class="sxs-lookup"><span data-stu-id="5538e-106">The definition of the procedure (the CREATE PROCEDURE statement) is replicated to the Subscriber when the subscription is initialized; when the procedure is executed at the Publisher, replication executes the corresponding procedure at the Subscriber.</span></span>  
  
### <a name="to-publish-the-execution-of-a-stored-procedure"></a><span data-ttu-id="5538e-107">So veröffentlichen Sie die Ausführung einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="5538e-107">To publish the execution of a stored procedure</span></span>  
  
1.  <span data-ttu-id="5538e-108">Wählen Sie auf der Seite **Artikel** des Assistenten für neue Veröffentlichungen oder im Dialogfeld **Veröffentlichungseigenschaften - \<Publication>** eine gespeicherte Prozedur aus.</span><span class="sxs-lookup"><span data-stu-id="5538e-108">On the **Articles** page of the New Publication Wizard or the **Publication Properties - \<Publication>** dialog box, select a stored procedure.</span></span>  
  
2.  <span data-ttu-id="5538e-109">Klicken Sie auf **Artikeleigenschaften**und anschließend auf **Eigenschaften des hervorgehobenen Gespeicherte Prozedur-Artikels festlegen**.</span><span class="sxs-lookup"><span data-stu-id="5538e-109">Click **Article Properties**, and then click **Set Properties of Highlighted Stored Procedure**.</span></span>  
  
3.  <span data-ttu-id="5538e-110">Geben Sie im Dialogfeld **Artikeleigenschaften - \<Article>** einen der folgenden Werte für die Option **Replizieren** an:</span><span class="sxs-lookup"><span data-stu-id="5538e-110">In the **Article Properties - \<Article>** dialog box, specify one of the following values for the **Replicate** option:</span></span>  
  
    -   <span data-ttu-id="5538e-111">**Ausführung der gespeicherten Prozedur**</span><span class="sxs-lookup"><span data-stu-id="5538e-111">**Execution of the stored procedure**</span></span>  
  
    -   <span data-ttu-id="5538e-112">**Ausführung in einer serialisierten Transaktion**</span><span class="sxs-lookup"><span data-stu-id="5538e-112">**Execution in a serialized transaction of the SP**</span></span>  
  
         <span data-ttu-id="5538e-113">Es handelt sich hierbei um die bevorzugte Option, da hier die Prozedurausführung nur repliziert wird, wenn die Prozedur im Kontext einer serialisierbaren Transaktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5538e-113">This is the recommended option, because it replicates the procedure execution only if the procedure is executed within the context of a serializable transaction.</span></span> <span data-ttu-id="5538e-114">Falls die gespeicherte Prozedur außerhalb einer serialisierbaren Transaktion ausgeführt wird, werden Änderungen an den Daten in veröffentlichten Tabellen als eine Reihe von DML-Anweisungen (Data Manipulation Language, Datenbearbeitungssprache) repliziert.</span><span class="sxs-lookup"><span data-stu-id="5538e-114">If the stored procedure is executed outside of a serializable transaction, changes to data in published tables are replicated as a series of data manipulation language (DML) statements.</span></span>  
  
4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)]  
  
5.  <span data-ttu-id="5538e-115">Wenn Sie sich im Dialogfeld **Veröffentlichungseigenschaften - \<Publication>** befinden, klicken Sie auf **OK**, um die Einstellungen zu speichern und das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="5538e-115">If you are in the **Publication Properties - \<Publication>** dialog box, click **OK** to save and close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5538e-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5538e-116">See Also</span></span>  
 [<span data-ttu-id="5538e-117">Veröffentlichen der Ausführung von gespeicherten Prozeduren in der Transaktionsreplikation</span><span class="sxs-lookup"><span data-stu-id="5538e-117">Publishing Stored Procedure Execution in Transactional Replication</span></span>](../transactional/publishing-stored-procedure-execution-in-transactional-replication.md)  
  
  
