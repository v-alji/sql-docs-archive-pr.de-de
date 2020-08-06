---
title: Editor für den Task ' SQL ausführen ' (Seite Parameter Zuordnung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executesqltask.parametermapping.f1
helpviewer_keywords:
- Execute SQL Task Editor
ms.assetid: 8ebe020a-7921-46b2-8823-398748f379b2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cfbb4468cb69947dfa54fb519b7698286393d578
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616123"
---
# <a name="execute-sql-task-editor-parameter-mapping-page"></a><span data-ttu-id="fa7a6-102">Editor für den Task 'SQL ausführen' (Seite Parameterzuordnung)</span><span class="sxs-lookup"><span data-stu-id="fa7a6-102">Execute SQL Task Editor (Parameter Mapping Page)</span></span>
  <span data-ttu-id="fa7a6-103">Mithilfe der Seite **Parameterzuordnung** des Dialogfelds **Editor für den Task 'SQL ausführen'** können Sie Parametern in der SQL-Anweisung Variablen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="fa7a6-103">Use the **Parameter Mapping** page of the **Execute SQL Task Editor** dialog box to map variables to parameters in the SQL statement.</span></span>  
  
 <span data-ttu-id="fa7a6-104">Weitere Informationen zu diesem Task finden Sie unter [SQL ausführen (Task)](control-flow/execute-sql-task.md) und [Parameter und Rückgabecodes im Task „SQL ausführen“](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="fa7a6-104">To learn about this task, see [Execute SQL Task](control-flow/execute-sql-task.md) and [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="fa7a6-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="fa7a6-105">Options</span></span>  
 <span data-ttu-id="fa7a6-106">**Variablenname**</span><span class="sxs-lookup"><span data-stu-id="fa7a6-106">**Variable Name**</span></span>  
 <span data-ttu-id="fa7a6-107">Nachdem Sie auf **Hinzufügen** geklickt und damit eine neue Parameterzuordnung hinzugefügt haben, wählen Sie in der Liste eine Systemvariable oder eine benutzerdefinierte Variable aus, oder klicken Sie auf \<**New variable...**>, um mithilfe des Dialogfelds **Variable hinzufügen** eine neue Variable hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fa7a6-107">After you have added a parameter mapping by clicking **Add**, select a system or user-defined variable from the list or click \<**New variable...**> to add a new variable by using the **Add Variable** dialog box.</span></span>  
  
 <span data-ttu-id="fa7a6-108">**Verwandte Themen:** [Integration Services-Variablen &#40;SSIS&#41;](integration-services-ssis-variables.md)</span><span class="sxs-lookup"><span data-stu-id="fa7a6-108">**Related Topics:** [Integration Services &#40;SSIS&#41; Variables](integration-services-ssis-variables.md)</span></span>  
  
 <span data-ttu-id="fa7a6-109">**Richtung**</span><span class="sxs-lookup"><span data-stu-id="fa7a6-109">**Direction**</span></span>  
 <span data-ttu-id="fa7a6-110">Wählen Sie die Richtung des Parameters aus.</span><span class="sxs-lookup"><span data-stu-id="fa7a6-110">Select the direction of the parameter.</span></span> <span data-ttu-id="fa7a6-111">Ordnen Sie jede Variable einem Eingabeparameter, einem Ausgabeparameter oder einem Rückgabecode zu.</span><span class="sxs-lookup"><span data-stu-id="fa7a6-111">Map each variable to an input parameter, output parameter, or a return code.</span></span>  
  
 <span data-ttu-id="fa7a6-112">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="fa7a6-112">**Data Type**</span></span>  
 <span data-ttu-id="fa7a6-113">Wählen Sie den Datentyp des Parameters aus.</span><span class="sxs-lookup"><span data-stu-id="fa7a6-113">Select the data type of the parameter.</span></span> <span data-ttu-id="fa7a6-114">Die Liste der verfügbaren Datentypen hängt von dem Anbieter ab, den Sie in dem vom Task verwendeten Verbindungs-Manager ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="fa7a6-114">The list of available data types is specific to the provider selected in the connection manager used by the task.</span></span>  
  
 <span data-ttu-id="fa7a6-115">**Parametername**</span><span class="sxs-lookup"><span data-stu-id="fa7a6-115">**Parameter Name**</span></span>  
 <span data-ttu-id="fa7a6-116">Geben Sie einen Parameternamen an.</span><span class="sxs-lookup"><span data-stu-id="fa7a6-116">Provide a parameter name.</span></span>  
  
 <span data-ttu-id="fa7a6-117">Je nachdem, welchen Verbindungs-Manager-Typ der Task verwendet, müssen Sie Zahlen oder Parameternamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa7a6-117">Depending on the connection manager type that the task uses, you must use numbers or parameter names.</span></span> <span data-ttu-id="fa7a6-118">Einige Verbindungs-Manager-Typen erfordern, dass Parameternamen mit dem \@-Zeichen beginnen oder bestimmte Namen (z. B. \@Param1) bzw. Spaltennamen als Parameternamen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fa7a6-118">Some connection manager types require that the first character of the parameter name is the \@ sign , specific names like \@Param1, or column names as parameter names.</span></span>  
  
 <span data-ttu-id="fa7a6-119">**Verwandte Themen:** [Parameter und Rückgabecodes im Task „SQL ausführen“](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md)</span><span class="sxs-lookup"><span data-stu-id="fa7a6-119">**Related Topics:** [Parameters and Return Codes in the Execute SQL Task](../../2014/integration-services/parameters-and-return-codes-in-the-execute-sql-task.md)</span></span>  
  
 <span data-ttu-id="fa7a6-120">**Parametergröße**</span><span class="sxs-lookup"><span data-stu-id="fa7a6-120">**Parameter Size**</span></span>  
 <span data-ttu-id="fa7a6-121">Geben Sie die Größe von Parametern mit variabler Länge an, z. B. Zeichenfolgen und binäre Felder.</span><span class="sxs-lookup"><span data-stu-id="fa7a6-121">Provide the size of parameters that have variable length, such as strings and binary fields.</span></span>  
  
 <span data-ttu-id="fa7a6-122">Durch diese Einstellung wird sichergestellt, dass der Anbieter genügend Speicherplatz für Parameterwerte variabler Länge zuordnet.</span><span class="sxs-lookup"><span data-stu-id="fa7a6-122">This setting ensures that the provider allocates sufficient space for variable-length parameter values.</span></span>  
  
 <span data-ttu-id="fa7a6-123">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="fa7a6-123">**Add**</span></span>  
 <span data-ttu-id="fa7a6-124">Klicken Sie auf diese Option, um eine Parameterzuordnung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fa7a6-124">Click to add a parameter mapping.</span></span>  
  
 <span data-ttu-id="fa7a6-125">**Remove**</span><span class="sxs-lookup"><span data-stu-id="fa7a6-125">**Remove**</span></span>  
 <span data-ttu-id="fa7a6-126">Wählen Sie in der Liste eine Parameterzuordnung aus, und klicken Sie anschließend auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="fa7a6-126">Select a parameter mapping in the list and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa7a6-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fa7a6-127">See Also</span></span>  
 <span data-ttu-id="fa7a6-128">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="fa7a6-128">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="fa7a6-129">[Editor für den Task ' SQL ausführen ' &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="fa7a6-129">[Execute SQL Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="fa7a6-130">[Editor für den Task "SQL ausführen" &#40;resultsetseite&#41;](../../2014/integration-services/execute-sql-task-editor-result-set-page.md) </span><span class="sxs-lookup"><span data-stu-id="fa7a6-130">[Execute SQL Task Editor &#40;Result Set Page&#41;](../../2014/integration-services/execute-sql-task-editor-result-set-page.md) </span></span>  
 [<span data-ttu-id="fa7a6-131">Transact-SQL-Referenz &#40;Datenbank-Engine&#41;</span><span class="sxs-lookup"><span data-stu-id="fa7a6-131">Transact-SQL Reference &#40;Database Engine&#41;</span></span>](/sql/t-sql/language-reference)  
  
  
