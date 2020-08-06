---
title: Zusätzliche Skriptkomponentenbeispiele | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- Script component [Integration Services], examples
ms.assetid: 849dd38a-abb5-4702-a413-882aae3980a5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 897ca075674f5c3dbaf355390fe8346580bf638a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619222"
---
# <a name="additional-script-component-examples"></a><span data-ttu-id="a6f5b-102">Zusätzliche Skriptkomponentenbeispiele</span><span class="sxs-lookup"><span data-stu-id="a6f5b-102">Additional Script Component Examples</span></span>
  <span data-ttu-id="a6f5b-103">Bei der Skriptkomponente handelt es sich um ein konfigurierbares Tool, das Sie im Datenfluss eines Pakets verwenden können, um nahezu allen Anforderungen gerecht zu werden, die von den Quellen, Transformationen und Zielen nicht erfüllt werden, die in [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="a6f5b-103">The Script component is a configurable tool that you can use in the data flow of a package to fill almost any requirement that is not met by the sources, transformations, and destinations that are included with [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)].</span></span> <span data-ttu-id="a6f5b-104">Dieser Abschnitt enthält Skriptkomponentencodebeispiele, in denen die verschiedenen verfügbaren Funktionsarten veranschaulicht werden.</span><span class="sxs-lookup"><span data-stu-id="a6f5b-104">This section contains Script component code samples that demonstrate the various types of functionality that are available.</span></span>  
  
 <span data-ttu-id="a6f5b-105">Beispiele, die das Konfigurieren der Skriptkomponente als grundlegende Quelle, Transformation oder Ziel zeigen, finden Sie unter [Entwickeln bestimmter Arten von Skriptkomponenten](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span><span class="sxs-lookup"><span data-stu-id="a6f5b-105">For samples that demonstrate how to configure the Script component as a basic source, transformation, or destination, see [Developing Specific Types of Script Components](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a6f5b-106">Wenn Sie Komponenten erstellen möchten, die Sie einfacher in mehreren Datenflusstasks und Paketen wiederverwenden können, empfiehlt es sich, den Code in diesen Skriptkomponentenbeispielen als Ausgangspunkt für benutzerdefinierte Datenflusskomponenten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a6f5b-106">If you want to create components that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in these Script component samples as the starting point for custom data flow components.</span></span> <span data-ttu-id="a6f5b-107">Weitere Informationen finden Sie unter [Entwickeln einer benutzerdefinierten Datenflusskomponente](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="a6f5b-107">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a6f5b-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a6f5b-108">In This Section</span></span>  
 [<span data-ttu-id="a6f5b-109">Simulieren einer Fehlerausgabe für die Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="a6f5b-109">Simulating an Error Output for the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/simulating-an-error-output-for-the-script-component.md)  
 <span data-ttu-id="a6f5b-110">Die Skriptkomponente unterstützt keine Standardfehlerausgabe. Sie können diese jedoch mit geringem zusätzlichem Konfigurations- und Codierungsaufwand simulieren.</span><span class="sxs-lookup"><span data-stu-id="a6f5b-110">The Script component does not support a standard error output, but you can simulate a standard error output with very little additional configuration and coding.</span></span>  
  
 [<span data-ttu-id="a6f5b-111">Erweitern einer Fehlerausgabe mit der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="a6f5b-111">Enhancing an Error Output with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/enhancing-an-error-output-with-the-script-component.md)  
 <span data-ttu-id="a6f5b-112">Erläutert und veranschaulicht, wie mithilfe der Skriptkomponente zusätzliche Informationen zu einer Standardfehlerausgabe hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a6f5b-112">Explains and demonstrates how to add additional information to a standard error output by using the Script component.</span></span>  
  
 [<span data-ttu-id="a6f5b-113">Erstellen eines ODBC-Ziels mit der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="a6f5b-113">Creating an ODBC Destination with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/creating-an-odbc-destination-with-the-script-component.md)  
 <span data-ttu-id="a6f5b-114">Erläutert und veranschaulicht, wie ein ODBC-Datenflussziel mithilfe der Skriptkomponente erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="a6f5b-114">Explains and demonstrates how to create an ODBC data flow destination by using the Script component.</span></span>  
  
 [<span data-ttu-id="a6f5b-115">Analysieren von nicht standardmäßigen Textdateiformaten mit der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="a6f5b-115">Parsing Non-Standard Text File Formats with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-examples/parsing-non-standard-text-file-formats-with-the-script-component.md)  
 <span data-ttu-id="a6f5b-116">Erklärt und veranschaulicht, wie zwei verschiedene nicht standardmäßige Textdateiformate in Zieltabellen analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="a6f5b-116">Explains and demonstrates how to parse two different non-standard text file formats into destination tables.</span></span>  
  
<span data-ttu-id="a6f5b-117">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="a6f5b-117">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a6f5b-118">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="a6f5b-118">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a6f5b-119">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="a6f5b-119">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a6f5b-120">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a6f5b-120">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
  
