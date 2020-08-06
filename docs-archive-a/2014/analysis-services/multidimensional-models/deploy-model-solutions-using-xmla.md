---
title: Bereitstellen von Modelllösungen mit XMLA | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- XML scripts [Analysis Services]
- scripts [Analysis Services], deployment
- deploying [Analysis Services], XML scripts
- Analysis Services deployments, XML scripts
ms.assetid: a8cb1837-fcac-4730-bea4-a72cf94d9f7c
author: minewiskan
ms.author: owend
ms.openlocfilehash: b78490c5ab6ad3ba5e52bb82d4be254e3f5f102b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725085"
---
# <a name="deploy-model-solutions-using-xmla"></a><span data-ttu-id="89652-102">Bereitstellen von Modelllösungen mit XMLA</span><span class="sxs-lookup"><span data-stu-id="89652-102">Deploy Model Solutions Using XMLA</span></span>
  <span data-ttu-id="89652-103">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]bewirkt die Option **CREATE in** des Befehls **Skript für Datenbank als** das Erstellen eines XML-Skripts für eine gesamte [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank oder für eines der in ihr enthaltenen Objekte.</span><span class="sxs-lookup"><span data-stu-id="89652-103">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], the **CREATE To** option of the **Script Database As** command creates an XML script of an entire [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or one of its constituent objects.</span></span> <span data-ttu-id="89652-104">Das dabei entstehende Skript kann dann auf einem anderen Computer ausgeführt werden, um das Schema (die Metadaten) der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="89652-104">The resulting script can then be run on another computer to recreate the schema (metadata) of the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span> <span data-ttu-id="89652-105">Das Skript generiert die gesamte Datenbank, und es gibt beim Verwenden des Skripts keine Mechanismen zum inkrementellen Aktualisieren bereits bereitgestellter Objekte.</span><span class="sxs-lookup"><span data-stu-id="89652-105">The script generates the entire database, and there is no mechanism for incrementally updating already deployed objects when using the script.</span></span> <span data-ttu-id="89652-106">Nach dem Ausführen des Skripts und dem Bereitstellen der Datenbank muss die neu erstellte Datenbank verarbeitet werden, bevor Benutzer diese Datenbank durchsuchen können.</span><span class="sxs-lookup"><span data-stu-id="89652-106">After running the script and deploying the database, the newly created database must be processed before users can browse it.</span></span>  
  
 <span data-ttu-id="89652-107">Weitere Informationen zum Befehl **Skript für Datenbank als** finden Sie unter [Dokumentieren und Skripterstellung einer Analysis Services-Datenbank](document-and-script-an-analysis-services-database.md).</span><span class="sxs-lookup"><span data-stu-id="89652-107">For more information about the **Script Database As** command, see [Document and Script an Analysis Services Database](document-and-script-an-analysis-services-database.md).</span></span>  
  
## <a name="modifying-object-properties-in-the-xml-script"></a><span data-ttu-id="89652-108">Ändern der Objekteigenschaften im XML-Skript</span><span class="sxs-lookup"><span data-stu-id="89652-108">Modifying Object Properties in the XML Script</span></span>  
 <span data-ttu-id="89652-109">Beim Verwenden des Befehls **Skript für Datenbank als** können Sie keine bestimmten Eigenschaften der Datenbankobjekte ändern (z.B. den Datenbanknamen, die Datenquellenverbindungszeichenfolgen und die Sicherheitseinstellungen).</span><span class="sxs-lookup"><span data-stu-id="89652-109">When using the **Script Database As** command, you cannot modify specific properties (such as the database name, data source connection strings, and security settings) of the database objects.</span></span> <span data-ttu-id="89652-110">Diese Eigenschaften müssen entweder manuell im Skript geändert werden, nachdem das Skript generiert wurde, oder sie müssen nach dem Ausführen des Skripts in der bereitgestellten Datenbank geändert werden.</span><span class="sxs-lookup"><span data-stu-id="89652-110">These properties must either be manually modified in the script after the script has been generated or modified in the deployed database after running the script.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="89652-111">Das XML-Skript enthält das Kennwort nicht, wenn dies in der Verbindungszeichenfolge für eine Datenquelle oder für Identitätswechsel angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="89652-111">The XML script will not contain the password if this is specified in either the connection string for a data source or for impersonation purposes.</span></span> <span data-ttu-id="89652-112">Da das Kennwort in diesem Szenario für Verarbeitungszwecke erforderlich ist, müssen Sie es dem XML-Skript entweder vor oder nach dem Ausführen des XML-Skripts manuell hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="89652-112">Since the password is required for processing purposes in this scenario, you will either need to add this manually to the XML script before it executes or add it after the XML script executes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89652-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89652-113">See Also</span></span>  
 <span data-ttu-id="89652-114">[Bereitstellen von Modelllösungen mithilfe des Bereitstellungs-Assistenten](deploy-model-solutions-using-the-deployment-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="89652-114">[Deploy Model Solutions Using the Deployment Wizard](deploy-model-solutions-using-the-deployment-wizard.md) </span></span>  
 [<span data-ttu-id="89652-115">Synchronisieren von Analysis Services-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="89652-115">Synchronize Analysis Services Databases</span></span>](synchronize-analysis-services-databases.md)  
  
  
