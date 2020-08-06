---
title: Aktivieren eines Remoteverlegers auf einem Verteiler (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- remote Distributors [SQL Server replication]
- Publishers [SQL Server replication]
ms.assetid: 6f8e2831-5c45-4e39-8e51-d37e2813cf3d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 06c85924731b79e8b3c79cfbcc354b5bedf69b62
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609108"
---
# <a name="enable-a-remote-publisher-at-a-distributor-sql-server-management-studio"></a><span data-ttu-id="f0ac9-102">Aktivieren eines Remoteverlegers auf einem Verteiler (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="f0ac9-102">Enable a Remote Publisher at a Distributor (SQL Server Management Studio)</span></span>
  <span data-ttu-id="f0ac9-103">Auf der Seite **Verleger** können Sie aktivieren, dass ein Verleger einen Remoteverteiler verwendet.</span><span class="sxs-lookup"><span data-stu-id="f0ac9-103">Enable a Publisher to use a remote Distributor on the **Publishers** page.</span></span> <span data-ttu-id="f0ac9-104">Diese Seite ist im Verteilungskonfigurations-Assistenten sowie über das Dialogfeld **Verteilereigenschaften – \<Distributor>** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f0ac9-104">This page is available in the Configure Distribution Wizard and the **Distributor Properties - \<Distributor>** dialog box.</span></span> <span data-ttu-id="f0ac9-105">Weitere Informationen zum Verwenden des Assistenten sowie zum Zugriff auf das Dialogfeld finden Sie unter [Konfigurieren der Veröffentlichung und der Verteilung](configure-publishing-and-distribution.md) und [Anzeigen und Ändern der Verteiler- und Verlegereigenschaften](view-and-modify-distributor-and-publisher-properties.md).</span><span class="sxs-lookup"><span data-stu-id="f0ac9-105">For more information about using the wizard and accessing the dialog box, see [Configure Publishing and Distribution](configure-publishing-and-distribution.md) and [View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md).</span></span>  
  
### <a name="to-enable-a-publisher-in-the-configure-distribution-wizard"></a><span data-ttu-id="f0ac9-106">So aktivieren Sie einen Verleger im Verteilungskonfigurations-Assistenten</span><span class="sxs-lookup"><span data-stu-id="f0ac9-106">To enable a Publisher in the Configure Distribution Wizard</span></span>  
  
1.  <span data-ttu-id="f0ac9-107">Klicken Sie im Verteilungskonfigurations-Assistenten auf der Seite **Verleger** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f0ac9-107">On the **Publishers** page of the Configure Distribution Wizard, click **Add**.</span></span>  
  
2.  <span data-ttu-id="f0ac9-108">Klicken Sie auf **SQL Server-Verleger hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f0ac9-108">Click **Add SQL Server Publisher**.</span></span> <span data-ttu-id="f0ac9-109">Informationen zum Aktivieren der Verwendung eines Verteilers auf einem Oracle-Verleger finden Sie unter [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="f0ac9-109">For information about enabling an Oracle Publisher to use a Distributor, see [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span></span>  
  
3.  <span data-ttu-id="f0ac9-110">Geben Sie im Dialogfeld **Verbindung mit Server herstellen** die Verbindungsinformationen für den Verleger an, der den Remoteverteiler verwenden soll, und klicken Sie anschließend auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="f0ac9-110">In the **Connect to Server** dialog box, specify connection information for the Publisher that will use the remote Distributor, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="f0ac9-111">Geben Sie auf der Seite **Verteilerkennwort** in den Textfeldern **Kennwort** und **Kennwort bestätigen** ein sicheres Kennwort für das **distributor_admin** -Konto an, das die Replikation zum Herstellen der Verbindung zwischen dem Verleger und dem Verteiler verwendet, um administrative Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f0ac9-111">On the **Distributor Password** page, in the **Password** and **Confirm password** text boxes, specify a strong password for the **distributor_admin** account, which replication uses to connect from the Publisher to the Distributor to perform administrative tasks.</span></span>  
  
5.  <span data-ttu-id="f0ac9-112">Klicken Sie auf die Schaltfläche mit den drei Punkten ( **…** ), um die Einstellungen eines Verlegers anzuzeigen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f0ac9-112">To view and modify settings for a Publisher, click the properties button (**...**).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-enable-a-publisher-in-the-distributor-properties-dialog-box"></a><span data-ttu-id="f0ac9-113">So aktivieren Sie einen Verleger im Dialogfeld "Verteilereigenschaften"</span><span class="sxs-lookup"><span data-stu-id="f0ac9-113">To enable a Publisher in the Distributor Properties dialog box</span></span>  
  
1.  <span data-ttu-id="f0ac9-114">Klicken Sie auf der Seite **Verleger** des Dialogfelds **Verteilereigenschaften – \<Distributor>** auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f0ac9-114">On the **Publishers** page of the **Distributor Properties - \<Distributor>** dialog box, click **Add**.</span></span>  
  
2.  <span data-ttu-id="f0ac9-115">Klicken Sie auf **SQL Server-Verleger hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f0ac9-115">Click **Add SQL Server Publisher**.</span></span> <span data-ttu-id="f0ac9-116">Informationen zum Aktivieren der Verwendung eines Verteilers auf einem Oracle-Verleger finden Sie unter [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="f0ac9-116">For information about enabling an Oracle Publisher to use a Distributor, see [Create a Publication from an Oracle Database](publish/create-a-publication-from-an-oracle-database.md).</span></span>  
  
3.  <span data-ttu-id="f0ac9-117">Geben Sie im Dialogfeld **Verbindung mit Server herstellen** die Verbindungsinformationen für den Verleger an, der den Remoteverteiler verwenden soll, und klicken Sie anschließend auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="f0ac9-117">In the **Connect to Server** dialog box, specify connection information for the Publisher that will use the remote Distributor, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="f0ac9-118">Geben Sie auf der Seite **Verleger** in den Textfeldern **Kennwort** und **Kennwort bestätigen** ein sicheres Kennwort für das **distributor_admin** -Konto an, das die Replikation zum Herstellen der Verbindung zwischen dem Verleger und dem Verteiler verwendet, um administrative Aufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f0ac9-118">On the **Publishers** page, in the **Password** and **Confirm password** text boxes, specify a strong password for the **distributor_admin** account, which replication uses to connect from the Publisher to the Distributor to perform administrative tasks.</span></span>  
  
5.  <span data-ttu-id="f0ac9-119">Klicken Sie auf die Schaltfläche mit den drei Punkten ( **…** ), um die Einstellungen eines Verlegers anzuzeigen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f0ac9-119">To view and modify settings for a Publisher, click the properties button (**...**).</span></span>  
  
6.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f0ac9-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0ac9-120">See Also</span></span>  
 <span data-ttu-id="f0ac9-121">[Konfigurieren der Veröffentlichung und der Verteilung](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="f0ac9-121">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="f0ac9-122">[Verteilung konfigurieren](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="f0ac9-122">[Configure Distribution](configure-distribution.md) </span></span>  
 [<span data-ttu-id="f0ac9-123">Schützen des Verteilers</span><span class="sxs-lookup"><span data-stu-id="f0ac9-123">Secure the Distributor</span></span>](security/secure-the-distributor.md)  
  
  
