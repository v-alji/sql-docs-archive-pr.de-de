---
title: Erstellen einer Domäne | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
f1_keywords:
- sql12.dqs.kb.createdomain.f1
ms.assetid: 5c4828f5-bd51-4c29-b3de-87b7d2f2d3e5
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fad6abd795aa9412bb71d251623d92d3e13b889c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609470"
---
# <a name="create-a-domain"></a><span data-ttu-id="9632d-102">Erstellen einer Domäne</span><span class="sxs-lookup"><span data-stu-id="9632d-102">Create a Domain</span></span>
  <span data-ttu-id="9632d-103">In diesem Thema wird beschrieben, wie Sie eine Domäne in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS) erstellen.</span><span class="sxs-lookup"><span data-stu-id="9632d-103">This topic describes how to create a domain in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="9632d-104">Die Werte in der Domäne sind eine semantische Darstellung der Daten in einem Feld.</span><span class="sxs-lookup"><span data-stu-id="9632d-104">The values in the domain are a semantic representation of the data in a field.</span></span> <span data-ttu-id="9632d-105">Weitere Informationen zu Domänen finden Sie unter [Verwalten einer Domäne](../../2014/data-quality-services/managing-a-domain.md).</span><span class="sxs-lookup"><span data-stu-id="9632d-105">For more information on domains, see [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md).</span></span>  
  
 <span data-ttu-id="9632d-106">Es gibt zwei Möglichkeiten, eine neue Domäne zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9632d-106">There are two ways to create a new domain.</span></span> <span data-ttu-id="9632d-107">Erstens während des Strukturschritts der Wissensermittlungsaktivität, wenn Sie gerade ein Datenbeispiel analysieren, um einer neuen oder vorhandenen Wissensdatenbank Wissen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9632d-107">The first is during the Map step of the knowledge discovery activity, when you are in the process of analyzing a data sample to add knowledge to a new or existing knowledge base.</span></span> <span data-ttu-id="9632d-108">Zweitens während der Domänenverwaltungsaktivität, wenn Sie eine neue Domäne erstellen, anstatt eine vorhandene zu ändern.</span><span class="sxs-lookup"><span data-stu-id="9632d-108">The second is during the domain management activity, when instead of changing an existing domain, you create a new one.</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9632d-109">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="9632d-109">Before You Begin</span></span>  
  
###  <a name="prerequisites"></a><a name="Prerequisites"></a> <span data-ttu-id="9632d-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="9632d-110">Prerequisites</span></span>  
 <span data-ttu-id="9632d-111">Um eine Domäne zu erstellen, müssen Sie eine Wissensdatenbank erstellt und geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="9632d-111">To create a domain, you must have created and opened a knowledge base.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9632d-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="9632d-112">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9632d-113">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="9632d-113">Permissions</span></span>  
 <span data-ttu-id="9632d-114">Sie müssen über die dqs_kb_editor- oder dqs_administrator-Rolle in der DQS_MAIN-Datenbank verfügen, um eine Domäne zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9632d-114">You must have the dqs_kb_editor role or the dqs_administrator on the DQS_MAIN database to create a domain.</span></span>  
  
##  <a name="create-a-domain-in-the-knowledge-discovery-activity"></a><a name="Discovery"></a><span data-ttu-id="9632d-115">Erstellen einer Domäne in der Wissens Ermittlungs Aktivität</span><span class="sxs-lookup"><span data-stu-id="9632d-115">Create a Domain in the Knowledge Discovery Activity</span></span>  
  
1.  [!INCLUDE[ssDQSInitialStep](../includes/ssdqsinitialstep-md.md)]<span data-ttu-id="9632d-116">[Führen Sie die Data Quality-Client Anwendung](../../2014/data-quality-services/run-the-data-quality-client-application.md)aus.</span><span class="sxs-lookup"><span data-stu-id="9632d-116">[Run the Data Quality Client Application](../../2014/data-quality-services/run-the-data-quality-client-application.md).</span></span>  
  
2.  <span data-ttu-id="9632d-117">Klicken Sie im [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Startbildschirm auf **Wissensdatenbank öffnen** , und wählen Sie dann eine Wissensdatenbank aus, oder klicken Sie auf **Neue Wissensdatenbank** , und geben Sie Eigenschaften für die neue Wissensdatenbank ein.</span><span class="sxs-lookup"><span data-stu-id="9632d-117">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open knowledge base** and then select a knowledge base, or click **New knowledge base** and enter properties for the new knowledge base.</span></span>  
  
3.  <span data-ttu-id="9632d-118">Wählen Sie die Aktivität **Wissensermittlung** aus, und klicken Sie dann auf **Erstellen** , um die neue Wissensdatenbank zu erstellen, oder auf **Öffnen** , um eine vorhandene Wissensdatenbank zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9632d-118">Select **Knowledge Discovery** as the activity, and then click **Create** to create the new knowledge base or **Open** to open an existing knowledge base.</span></span>  
  
4.  <span data-ttu-id="9632d-119">Geben Sie auf der Seite **Zuordnen** eine Verbindung zur Datenquelle an.</span><span class="sxs-lookup"><span data-stu-id="9632d-119">On the **Map** page, specify a connection to the data source.</span></span> <span data-ttu-id="9632d-120">Weitere Informationen finden Sie unter [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="9632d-120">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md).</span></span>  
  
5.  <span data-ttu-id="9632d-121">Wählen Sie in der Tabelle **Zuordnungen** eine Quellspalte aus der Dropdownliste für die Spalte **Quellspalte** einer leeren Zeile aus.</span><span class="sxs-lookup"><span data-stu-id="9632d-121">In the **Mappings** table, select a source column from the drop-down list for the **Source Column** column of an empty row.</span></span> <span data-ttu-id="9632d-122">Wenn keine entsprechenden Domänen vorhanden ist, klicken Sie auf das Symbol **Domäne erstellen** .</span><span class="sxs-lookup"><span data-stu-id="9632d-122">If no corresponding domain exists, click the **Create a Domain** icon.</span></span>  
  
##  <a name="create-a-domain-in-the-domain-management-activity"></a><a name="DomainManagement"></a><span data-ttu-id="9632d-123">Erstellen einer Domäne in der Domänen Verwaltungs Aktivität</span><span class="sxs-lookup"><span data-stu-id="9632d-123">Create a Domain in the Domain Management Activity</span></span>  
  
1.  <span data-ttu-id="9632d-124">Klicken Sie im [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] -Startbildschirm auf **Wissensdatenbank öffnen** , und wählen Sie dann eine Wissensdatenbank aus, oder klicken Sie auf **Neue Wissensdatenbank** , und geben Sie Eigenschaften für die neue Wissensdatenbank ein.</span><span class="sxs-lookup"><span data-stu-id="9632d-124">In the [!INCLUDE[ssDQSClient](../includes/ssdqsclient-md.md)] home screen, click **Open knowledge base** and then select a knowledge base, or click **New knowledge base** and enter properties for the new knowledge base.</span></span>  
  
2.  <span data-ttu-id="9632d-125">Wählen Sie die Aktivität **Domänenverwaltung** aus, und klicken Sie dann auf **Erstellen** , um die neue Wissensdatenbank zu erstellen, oder auf **Öffnen** , um eine vorhandene Wissensdatenbank zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="9632d-125">Select **Domain Management** as the activity, and then click **Create** to create the new knowledge base or **Open** to open an existing knowledge base.</span></span>  
  
3.  <span data-ttu-id="9632d-126">Klicken Sie auf der Seite **Domänenverwaltung** über der Domänenliste auf das Symbol **Domäne erstellen** .</span><span class="sxs-lookup"><span data-stu-id="9632d-126">On the **Domain Management** page, click the **Create a Domain** icon above the Domain list.</span></span>  
  
##  <a name="set-domain-properties"></a><a name="Properties"></a><span data-ttu-id="9632d-127">Festlegen von Domänen Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9632d-127">Set Domain Properties</span></span>  
  
1.  <span data-ttu-id="9632d-128">Geben Sie im Dialogfeld **Domäne erstellen** einen eindeutigen Namen für die Wissensdatenbank und eine Beschreibung mit maximal 256 Zeichen ein.</span><span class="sxs-lookup"><span data-stu-id="9632d-128">In the **Create Domain** dialog box, enter a name that is unique to the knowledge base and a description up to 256 characters.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9632d-129"> Weitere Informationen zu den Domäneneigenschaften finden Sie unter [Set Domain Properties](../../2014/data-quality-services/set-domain-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9632d-129">For more information about domain properties, see [Set Domain Properties](../../2014/data-quality-services/set-domain-properties.md).</span></span>  
  
2.  <span data-ttu-id="9632d-130">Wählen Sie in der Liste **Datentyp** einen Datentyp für die Werte in der Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="9632d-130">From the **Data Type** list, select a data type for the values in the domain.</span></span> <span data-ttu-id="9632d-131">Der Datentyp kann **Zeichenfolge** (Standard), **Datum**, **Ganze Zahl**oder **Dezimal**sein.</span><span class="sxs-lookup"><span data-stu-id="9632d-131">The data type can be **String** (the default), **Date**, **Integer**, or **Decimal**.</span></span>  
  
3.  <span data-ttu-id="9632d-132">Wählen Sie **Führende Werte verwenden** aus, um anzugeben, dass der führende Wert in einer Gruppe von Synonymen statt eines Werts ausgegeben wird, der ein Synonym dafür ist.</span><span class="sxs-lookup"><span data-stu-id="9632d-132">Select **Use Leading Values** to specify that the leading value in a group of synonyms will be output instead of a value that is a synonym to it.</span></span> <span data-ttu-id="9632d-133">Deaktivieren Sie **Führende Werte verwenden** , um anzugeben, dass jeder Synonymwert in seinem richtigen oder korrigierten Format ausgegeben und nicht durch den führenden Wert für die zugehörige Gruppe ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="9632d-133">Deselect **Use Leading Values** to specify that each synonym value is output in its correct or corrected form, and is not replaced by the leading value for its group.</span></span>  
  
4.  <span data-ttu-id="9632d-134">Wenn der Datentyp **Zeichenfolge**angegeben ist, wählen Sie **Zeichenfolge normalisieren** aus, um Sonderzeichen in den Domänenwerten zu entfernen. Dies kann die Wahrscheinlichkeit von Übereinstimmungen erhöhen.</span><span class="sxs-lookup"><span data-stu-id="9632d-134">If the data type is **String**, select **Normalize String** to remove special characters in the domain values, which may improve the likelihood of matches.</span></span>  
  
5.  <span data-ttu-id="9632d-135">Wählen Sie in der Dropdownliste **Formatausgabe** die Formatierung aus, die beim Ausgeben der Datenwerte in der Domäne angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="9632d-135">From the **Format Output to** drop-down list, select the formatting that will be applied when the data values in the domain are output.</span></span> <span data-ttu-id="9632d-136">Die Formatierung ist für den in Schritt 2 ausgewählten Datentyp spezifisch, wie in der folgenden Liste gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9632d-136">The formatting is specific to the data type selected in step 2, as shown in the following list:</span></span>  
  
    -   <span data-ttu-id="9632d-137">Für einen Zeichenfolgenwert können Sie angeben, dass die Zeichenfolge in Großbuchstaben, in Kleinbuchstaben oder in Großschreibung ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="9632d-137">For a string value, you can specify that the string be output as upper case, lower case, or capitalized.</span></span>  
  
    -   <span data-ttu-id="9632d-138">Für einen Datumswert können Sie das Format von Tag, Monat und Jahr angeben.</span><span class="sxs-lookup"><span data-stu-id="9632d-138">For a date value, you can specify the format of the day, month, and year.</span></span>  
  
    -   <span data-ttu-id="9632d-139">Für einen ganzzahligen Wert können Sie den Typ der Formatmaske angeben, die angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9632d-139">For an integer value, you can specify the type of format mask to be applied.</span></span>  
  
    -   <span data-ttu-id="9632d-140">Für einen Dezimalwert können Sie die Genauigkeit und den Typ der Formatmaske angeben, die angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="9632d-140">For a decimal value, you can specify the accuracy and the type of format mask to be applied.</span></span>  
  
     <span data-ttu-id="9632d-141">Wenn Sie **Keine** in der Dropdownliste **Formatausgabe** auswählen, bedeutet dies, dass keines der Formate in der Liste angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="9632d-141">Selecting **None** in the **Format Output to** drop-down list means none of the formats in the list will be applied.</span></span>  
  
6.  <span data-ttu-id="9632d-142">Wenn der Datentyp **Zeichenfolge**angegeben ist, wählen Sie in der Dropdownliste **Sprache** die Sprachversion der Rechtschreibprüfung aus, die verwendet werden soll, wenn die Rechtschreibprüfung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9632d-142">If the data type is **String**, in the **Language** drop-down list, select which language version of the speller you want to apply if you enable the speller.</span></span>  
  
7.  <span data-ttu-id="9632d-143">Wählen Sie für den Datentyp **Zeichenfolge**die Option **Rechtschreibprüfung aktivieren** aus, um die Rechtschreibprüfung beim Auffüllen der Domäne für alle Zeichenfolgenwerte auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9632d-143">If the data type is **String**, select **Enable Speller** to run the Speller on all string values when populating the domain.</span></span>  
  
8.  <span data-ttu-id="9632d-144">Wählen Sie für den Datentyp **Zeichenfolge**die Option **Syntaxfehleralgorithmen deaktivieren** aus, um die Domäne aufzufüllen, ohne die Zeichenfolgenwerte auf Syntaxfehler zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9632d-144">If the data type is **String**, select **Disable Syntax Error Algorithms** to populate the domain without checking string values for syntax errors.</span></span>  
  
9. <span data-ttu-id="9632d-145">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9632d-145">Click **OK**.</span></span>  
  
10. <span data-ttu-id="9632d-146">Klicken Sie auf **Fertig stellen** , um die Domänenverwaltungsaktivität abzuschließen, wie in [Beenden der Domänenverwaltungsaktivität](../../2014/data-quality-services/end-the-domain-management-activity.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9632d-146">Click **Finish** to complete the domain management activity, as described in [End the Domain Management Activity](../../2014/data-quality-services/end-the-domain-management-activity.md).</span></span>  
  
##  <a name="follow-up-after-creating-a-domain"></a><a name="FollowUp"></a><span data-ttu-id="9632d-147">Nachverfolgung: nach dem Erstellen einer Domäne</span><span class="sxs-lookup"><span data-stu-id="9632d-147">Follow Up: After Creating a Domain</span></span>  
 <span data-ttu-id="9632d-148">Nachdem Sie eine Domäne erstellt haben, können Sie andere Domänenverwaltungsaufgaben in der Domäne ausführen. Sie können die Wissensermittlung durchführen, um der Domäne Wissen hinzuzufügen, oder Sie können der Domäne eine Abgleichsrichtlinie hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="9632d-148">After you create a domain, you can perform other domain management tasks on the domain, you can perform knowledge discovery to add knowledge to the domain, or you can add a matching policy to the domain.</span></span> <span data-ttu-id="9632d-149">Weitere Informationen finden Sie unter [Durchführen der Wissensermittlung](../../2014/data-quality-services/perform-knowledge-discovery.md), [Verwalten einer Domäne](../../2014/data-quality-services/managing-a-domain.md) oder [Erstellen einer Abgleichsrichtlinie](../../2014/data-quality-services/create-a-matching-policy.md).</span><span class="sxs-lookup"><span data-stu-id="9632d-149">For more information, see [Perform Knowledge Discovery](../../2014/data-quality-services/perform-knowledge-discovery.md), [Managing a Domain](../../2014/data-quality-services/managing-a-domain.md), or [Create a Matching Policy](../../2014/data-quality-services/create-a-matching-policy.md).</span></span>  
  
  
