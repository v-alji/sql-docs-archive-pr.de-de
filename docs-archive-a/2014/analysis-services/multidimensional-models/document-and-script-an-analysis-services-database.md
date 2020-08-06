---
title: Dokumentieren und Erstellen eines Skripts für eine Analysis Services Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- XML for Analysis, scripts
- XMLA, scripts
- scripts [Analysis Services], databases
- documenting databases
- databases [Analysis Services], documenting
- databases [Analysis Services], scripts
ms.assetid: 125044e2-8d36-4733-8743-8bb68ff9aa4e
author: minewiskan
ms.author: owend
ms.openlocfilehash: cfe008b0d6903d7d012eb57d41d6e50240202ec8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621693"
---
# <a name="document-and-script-an-analysis-services-database"></a><span data-ttu-id="12767-102">Dokumentieren und Skripterstellung einer Analysis Services-Datenbank</span><span class="sxs-lookup"><span data-stu-id="12767-102">Document and Script an Analysis Services Database</span></span>
  <span data-ttu-id="12767-103">Nachdem eine [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank bereitgestellt ist, können Sie mithilfe von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] die Metadaten der Datenbank oder eines in der Datenbank enthaltenen Objekts als XML for Analysis-Skript (XMLA) ausgeben.</span><span class="sxs-lookup"><span data-stu-id="12767-103">After an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database is deployed, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to output the metadata of the database, or of an object contained in the database, as an XML for Analysis (XMLA) script.</span></span> <span data-ttu-id="12767-104">Sie können dieses Skript in ein neues **XMLA-Abfrage-Editor** -Fenster, in eine Datei oder die Zwischenablage exportieren.</span><span class="sxs-lookup"><span data-stu-id="12767-104">You can output this script to a new **XMLA Query Editor** window, to a file, or to the Clipboard.</span></span> <span data-ttu-id="12767-105">Weitere Informationen zu XMLA finden Sie unter [Analysis Services Skriptsprache &#40;ASSL&#41; Referenz](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla).</span><span class="sxs-lookup"><span data-stu-id="12767-105">For more information about XMLA, see [Analysis Services Scripting Language &#40;ASSL&#41; Reference](https://docs.microsoft.com/bi-reference/assl/analysis-services-scripting-language-assl-for-xmla).</span></span>  
  
 <span data-ttu-id="12767-106">Das generierte XMLA-Skript verwendet Elemente der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Skriptsprache (ASSL), um im Skript enthaltene Objekte zu definieren.</span><span class="sxs-lookup"><span data-stu-id="12767-106">The generated XMLA script uses [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Scripting Language (ASSL) elements to define the objects contained by the script.</span></span> <span data-ttu-id="12767-107">Wenn Sie ein CREATE-Skript generiert haben, enthält das entstandene XMLA-Skript einen XMLA **Create** -Befehl und ASSL-Elemente, die verwendet werden können, um die gesamte [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbankstruktur auf einer Instanz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="12767-107">If you generated a CREATE script, the resulting XMLA script contains an XMLA **Create** command and ASSL elements that can be used to create the entire [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database structure on an instance.</span></span> <span data-ttu-id="12767-108">Wenn Sie ein ALTER-Skript generiert haben, enthält das resultierende XMLA-Skript den XMLA-Befehl **Alter** und ASSL-Elemente, mit denen die Struktur einer vorhandenen [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank wieder in dem Zustand wiederhergestellt werden kann, den sie zum Zeitpunkt der Skripterstellung innehatte.</span><span class="sxs-lookup"><span data-stu-id="12767-108">If you generated an ALTER script, the resulting XMLA script contains an XMLA **Alter** command and ASSL elements that can be used to restore the structure of an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database to the state of the database at the time the script was created.</span></span>  
  
 <span data-ttu-id="12767-109">Sie können das aus einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank generierte XMLA-Skript auf viele verschiedene Weisen verwenden, so z. B. wie folgt:</span><span class="sxs-lookup"><span data-stu-id="12767-109">You can use the generated XMLA script from an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in many ways, including:</span></span>  
  
-   <span data-ttu-id="12767-110">Verwalten eines Sicherungsskripts, mit dem Sie alle Datenbankobjekte und -berechtigungen neu erstellen können.</span><span class="sxs-lookup"><span data-stu-id="12767-110">To maintain a backup script that allows you to recreate all the database objects and permissions.</span></span>  
  
-   <span data-ttu-id="12767-111">Erstellen oder Aktualisieren von Datenbankentwicklungscode.</span><span class="sxs-lookup"><span data-stu-id="12767-111">To create or update database development code.</span></span>  
  
-   <span data-ttu-id="12767-112">Erstellen eines Testes oder einer Entwicklungsumgebung aus einem vorhandenen Schema heraus.</span><span class="sxs-lookup"><span data-stu-id="12767-112">To create a test or development environment from an existing schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12767-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="12767-113">See Also</span></span>  
 <span data-ttu-id="12767-114">[Ändern oder Löschen einer Analysis Services Datenbank](modify-or-delete-an-analysis-services-database.md) </span><span class="sxs-lookup"><span data-stu-id="12767-114">[Modify or Delete an Analysis Services Database](modify-or-delete-an-analysis-services-database.md) </span></span>  
 <span data-ttu-id="12767-115">[Alter Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) </span><span class="sxs-lookup"><span data-stu-id="12767-115">[Alter Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/alter-element-xmla) </span></span>  
 [<span data-ttu-id="12767-116">Create-Element &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="12767-116">Create Element &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/create-element-xmla)  
  
  
