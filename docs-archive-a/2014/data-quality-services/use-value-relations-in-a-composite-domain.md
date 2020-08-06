---
title: Verwenden von Wertbeziehungen in einer Verbunddomäne | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.dm.cdvaluerelations.f1
ms.assetid: 5ee468f0-8538-4620-90e8-63f466c9000e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 135934ec99fed612609e5e1b962f08bb93b98ede
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726266"
---
# <a name="use-value-relations-in-a-composite-domain"></a><span data-ttu-id="577db-102">Verwenden von Wertbeziehungen in einer Verbunddomäne</span><span class="sxs-lookup"><span data-stu-id="577db-102">Use Value Relations in a Composite Domain</span></span>
  <span data-ttu-id="577db-103">In diesem Thema wird beschrieben, wie Wertkombinationen angezeigt werden, die während des Wissensermittlungsprozesses in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) für die Verbunddomäne gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="577db-103">This topic describes how to view value combinations found for the composite domain during the knowledge discovery process in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="577db-104">Auf dieser Seite wird angezeigt, wie oft die Wertkombinationen vorkommen.</span><span class="sxs-lookup"><span data-stu-id="577db-104">This page shows the number of occurrences of the value combinations.</span></span> <span data-ttu-id="577db-105">Die Wertverwaltung wird nicht für Verbunddomänen unterstützt. Deshalb können Sie für die Werte keine Vorgänge ausführen.</span><span class="sxs-lookup"><span data-stu-id="577db-105">Value management is not supported for composite domains, so you cannot perform any operations on these values.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="577db-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="577db-106">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="577db-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="577db-107">Prerequisites</span></span>  
 <span data-ttu-id="577db-108">Um Wertbeziehungen anzuzeigen, müssen Sie eine Verbunddomäne erstellt und geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="577db-108">To view value relations, you must have created and opened a composite domain.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="577db-109">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="577db-109">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="577db-110">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="577db-110">Permissions</span></span>  
 <span data-ttu-id="577db-111">Sie müssen über die dqs_kb_editor- oder dqs_administrator-Rolle in der DQS_MAIN-Datenbank verfügen, um Wertbeziehungen in einer Verbunddomäne anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="577db-111">You must have the dqs_kb_editor or the dqs_administrator role on the DQS_MAIN database to view value relations in a composite domain.</span></span>  
  
##  <a name="view-value-relations"></a><a name="Use"></a><span data-ttu-id="577db-112">Anzeigen von Wert Beziehungen</span><span class="sxs-lookup"><span data-stu-id="577db-112">View Value Relations</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="577db-113">[Führen Sie die Data Quality-Client Anwendung](../../2014/data-quality-services/run-the-data-quality-client-application.md)aus.</span><span class="sxs-lookup"><span data-stu-id="577db-113">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="577db-114">Öffnen oder erstellen Sie im [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Startbildschirm eine Wissensdatenbank.</span><span class="sxs-lookup"><span data-stu-id="577db-114">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, open or create a knowledge base.</span></span> <span data-ttu-id="577db-115">Wählen Sie **Domänenverwaltung** als Aktivität aus, und klicken Sie dann auf **Öffnen** oder **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="577db-115">Select **Domain Management** as the activity, and then click **Open** or **Create**.</span></span> <span data-ttu-id="577db-116">Weitere Informationen finden Sie unter [Erstellen einer Wissensdatenbank](../../2014/data-quality-services/create-a-knowledge-base.md) oder [Öffnen einer Wissensdatenbank](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="577db-116">For more information, see [Create a Knowledge Base](../../2014/data-quality-services/create-a-knowledge-base.md) or [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
3.  <span data-ttu-id="577db-117">Wählen Sie aus der **Domänenliste** auf der Seite **Domänenverwaltung** die Verbunddomäne aus, für die Sie eine Domänenregel erstellen möchten, oder erstellen Sie eine neue Verbunddomäne.</span><span class="sxs-lookup"><span data-stu-id="577db-117">From the **Domain list** on the **Domain Management** page, select the composite domain that you want to create a domain rule for, or create a new composite domain.</span></span> <span data-ttu-id="577db-118">Wenn Sie eine neue Domäne erstellen müssen, finden Sie unter [Create a Composite Domain](../../2014/data-quality-services/create-a-composite-domain.md)weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="577db-118">If you have to create a new domain, see [Create a Composite Domain](../../2014/data-quality-services/create-a-composite-domain.md).</span></span>  
  
4.  <span data-ttu-id="577db-119">Klicken Sie auf die Registerkarte **Wertbeziehungen** .</span><span class="sxs-lookup"><span data-stu-id="577db-119">Click the **Value Relations** tab.</span></span>  
  
5.  <span data-ttu-id="577db-120">Zeigen Sie die Häufigkeit für jede Wertkombination an.</span><span class="sxs-lookup"><span data-stu-id="577db-120">View the frequencies displayed for each value combination.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="577db-121">In der Tabelle **Wert** wird jede Kombination von Werten angezeigt, die in der Verbunddomäne vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="577db-121">The **Value** table shows each combination of values that exists in the composite domain.</span></span> <span data-ttu-id="577db-122">Jeder Wert wird in der einzelnen Domäne angezeigt, für die er gilt.</span><span class="sxs-lookup"><span data-stu-id="577db-122">Each value is shown in the single domain that it applies to.</span></span> <span data-ttu-id="577db-123">Die Tabelle mit den Wertbeziehungen wird standardmäßig nach der Häufigkeit sortiert, aber Sie können auch auf eine andere Spalte klicken, um nach dieser Spalte zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="577db-123">The default sorting of the value relations table is by frequency, but you can click on another column to sort by that column.</span></span> <span data-ttu-id="577db-124">Nur Werte mit einer Frequenz größer gleich 20 werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="577db-124">Only those values with a frequency greater than or equal to 20 are displayed.</span></span>  
  
6.  <span data-ttu-id="577db-125">Sie können keine Werte in der Tabelle ändern.</span><span class="sxs-lookup"><span data-stu-id="577db-125">You cannot change any of the values in the table.</span></span> <span data-ttu-id="577db-126">Wenn Sie andere Vorgänge ausgeführt haben, klicken Sie auf **Fertig stellen** , um die Domänenverwaltungsaktivität abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="577db-126">If you have performed other operations, click **Finish** to complete the domain management activity.</span></span> <span data-ttu-id="577db-127">Klicken Sie andernfalls auf **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="577db-127">Otherwise, click **Cancel**.</span></span>  
  
##  <a name="follow-up-after-viewing-value-relations"></a><a name="FollowUp"></a><span data-ttu-id="577db-128">Nachverfolgung: nach dem Anzeigen von Wert Beziehungen</span><span class="sxs-lookup"><span data-stu-id="577db-128">Follow Up: After Viewing Value Relations</span></span>  
 <span data-ttu-id="577db-129">Nachdem Sie die Wertbeziehungen angezeigt haben, können Sie andere Domänenverwaltungsaufgaben in der Domäne ausführen. Sie können die Wissensermittlung durchführen, um der Domäne Wissen hinzuzufügen, oder Sie können der Domäne eine Abgleichsrichtlinie hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="577db-129">After you view value relations, you can perform other domain management tasks on the domain, you can perform knowledge discovery to add knowledge to the domain, or you can add a matching policy to the domain.</span></span> <span data-ttu-id="577db-130">Weitere Informationen finden Sie unter [Durchführen der Wissensermittlung](../../2014/data-quality-services/perform-knowledge-discovery.md), [Verwalten einer Domäne](../../2014/data-quality-services/managing-a-domain.md) oder [Erstellen einer Abgleichsrichtlinie](../../2014/data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="577db-130">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), or [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md).</span></span>  
  
  
