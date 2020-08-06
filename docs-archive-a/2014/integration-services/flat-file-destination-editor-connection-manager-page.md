---
title: Ziel-Editor für Flatfiles (Seite Verbindungs-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.flatfiledestadapter.connection.f1
helpviewer_keywords:
- Flat File Destination Editor
ms.assetid: b01571fa-bc19-4742-8eed-ac163172a919
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6997b72851c2b7bfc56445e6ddb01cfe6e9b04cd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609352"
---
# <a name="flat-file-destination-editor-connection-manager-page"></a><span data-ttu-id="800f9-102">Ziel-Editor für Flatfiles (Seite Verbindungs-Manager)</span><span class="sxs-lookup"><span data-stu-id="800f9-102">Flat File Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="800f9-103">Mithilfe der Seite **Verbindungs-Manager** des Dialogfelds **Ziel-Editor für Flatfiles** können Sie die Flatfile-Verbindung für das Ziel auswählen und angeben, ob die vorhandene Zieldatei überschrieben werden soll oder ob die Daten an die vorhandene Datei angehängt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="800f9-103">Use the **Connection Manager** page of the **Flat File Destination Editor** dialog box to select the flat file connection for the destination, and to specify whether to overwrite or append to the existing destination file.</span></span> <span data-ttu-id="800f9-104">Das Flatfileziel schreibt Daten in eine Textdatei.</span><span class="sxs-lookup"><span data-stu-id="800f9-104">The flat file destination writes data to a text file.</span></span> <span data-ttu-id="800f9-105">Als Format für diese Textdatei können Trennzeichen, feste Breite, feste Breite mit Zeilentrennzeichen oder rechter Flatterrand gewählt werden.</span><span class="sxs-lookup"><span data-stu-id="800f9-105">This text file can be in delimited, fixed width, fixed width with row delimiter, or ragged right format.</span></span>  
  
 <span data-ttu-id="800f9-106">Weitere Informationen zum Flatfileziel finden Sie unter [Flat File Destination](data-flow/flat-file-destination.md).</span><span class="sxs-lookup"><span data-stu-id="800f9-106">To learn more about the Flat File destination, see [Flat File Destination](data-flow/flat-file-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="800f9-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="800f9-107">Options</span></span>  
 <span data-ttu-id="800f9-108">**Verbindungs-Manager für Flatfiles**</span><span class="sxs-lookup"><span data-stu-id="800f9-108">**Flat File connection manager**</span></span>  
 <span data-ttu-id="800f9-109">Wählen Sie einen vorhandenen Verbindungs-Manager aus dem Listenfeld aus, oder erstellen Sie durch Klicken auf **Neu**eine neue Verbindung.</span><span class="sxs-lookup"><span data-stu-id="800f9-109">Select an existing connection manager by using the list box, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="800f9-110">**Neu**</span><span class="sxs-lookup"><span data-stu-id="800f9-110">**New**</span></span>  
 <span data-ttu-id="800f9-111">Erstellen Sie eine neue Verbindung mithilfe der Dialogfelder **Flatfileformat** und **Verbindungs-Manager-Editor für Flatfiles** .</span><span class="sxs-lookup"><span data-stu-id="800f9-111">Create a new connection by using the **Flat File Format** and **Flat File Connection Manager Editor** dialog boxes.</span></span>  
  
 <span data-ttu-id="800f9-112">Neben den standardmäßigen Flatfileformaten mit Trennzeichen, fester Breite oder rechtem Flatterrand verfügt das Dialogfeld **Flatfileformat** über eine vierte Option, **Feste Breite mit Zeilentrennzeichen**.</span><span class="sxs-lookup"><span data-stu-id="800f9-112">In addition to the standard flat file formats of delimited, fixed width, and ragged right, the **Flat File Format** dialog box has a fourth option, **Fixed width with row delimiters**.</span></span> <span data-ttu-id="800f9-113">Diese Option stellt einen Sonderfall des Formats mit rechtem Flatterrand dar, bei dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] eine Pseudospalte als letzte Datenspalte hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="800f9-113">This option represents a special case of the ragged-right format in which [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] adds a dummy column as the final column of data.</span></span> <span data-ttu-id="800f9-114">Diese Pseudospalte stellt sicher, dass die letzte Spalte über eine feste Breite verfügt.</span><span class="sxs-lookup"><span data-stu-id="800f9-114">This dummy column ensures that the final column has a fixed width.</span></span>  
  
 <span data-ttu-id="800f9-115">Die Option **Feste Breite mit Zeilentrennzeichen** ist im **Verbindungs-Manager-Editor für Flatfiles**nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="800f9-115">The **Fixed width with row delimiters** option is not available in the **Flat File Connection Manager Editor**.</span></span> <span data-ttu-id="800f9-116">Sofern erforderlich, können Sie diese Option im Editor emulieren.</span><span class="sxs-lookup"><span data-stu-id="800f9-116">If necessary, you can emulate this option in the editor.</span></span> <span data-ttu-id="800f9-117">Um diese Option zu emulieren, wählen Sie im **Verbindungs-Manager-Editor für Flatfiles** auf der Seite **Allgemein**für **Format**die Option **Rechter Flatterrand**aus.</span><span class="sxs-lookup"><span data-stu-id="800f9-117">To emulate this option, on the **General** page of the **Flat File Connection Manager Editor**, for **Format**, select **Ragged right**.</span></span> <span data-ttu-id="800f9-118">Fügen Sie dann im Editor auf der Seite **Erweitert** eine neue Pseudospalte als letzte Datenspalte hinzu.</span><span class="sxs-lookup"><span data-stu-id="800f9-118">Then on the **Advanced** page of the editor, add a new dummy column as the final column of data.</span></span>  
  
 <span data-ttu-id="800f9-119">**Daten in der Datei überschreiben**</span><span class="sxs-lookup"><span data-stu-id="800f9-119">**Overwrite data in the file**</span></span>  
 <span data-ttu-id="800f9-120">Gibt an, ob eine vorhandene Datei überschrieben, oder ob Daten angehängt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="800f9-120">Indicate whether to overwrite an existing file, or to append data to it.</span></span>  
  
 <span data-ttu-id="800f9-121">**Kopfzeile**</span><span class="sxs-lookup"><span data-stu-id="800f9-121">**Header**</span></span>  
 <span data-ttu-id="800f9-122">Geben Sie einen in die Datei einzufügenden Textblock ein, bevor Daten geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="800f9-122">Type a block of text to insert into the file before any data is written.</span></span> <span data-ttu-id="800f9-123">Mithilfe dieser Option können Sie zusätzliche Informationen wie Spaltenüberschriften hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="800f9-123">Use this option to include additional information, such as column headings.</span></span>  
  
 <span data-ttu-id="800f9-124">**Vorschau**</span><span class="sxs-lookup"><span data-stu-id="800f9-124">**Preview**</span></span>  
 <span data-ttu-id="800f9-125">Zeigen Sie mithilfe des Dialogfelds **Datenansicht** eine Vorschau der Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="800f9-125">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="800f9-126">In der Vorschau können bis zu 200 Zeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="800f9-126">Preview can display up to 200 rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="800f9-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="800f9-127">See Also</span></span>  
 <span data-ttu-id="800f9-128">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="800f9-128">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="800f9-129">Ziel-Editor für Flatfiles &#40;Seite „Zuordnungen“&#41;</span><span class="sxs-lookup"><span data-stu-id="800f9-129">Flat File Destination Editor &#40;Mappings Page&#41;</span></span>](../../2014/integration-services/flat-file-destination-editor-mappings-page.md)  
  
  
