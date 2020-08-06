---
title: Verwenden von Anmerkungen in Paketen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- self-documenting packages
- adding annotations
- annotations [Integration Services]
ms.assetid: 48c8ed9a-b10d-490c-9ba7-4b77aa44e3dd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 27c7df6afd894ea9730027da1d54786ed8397fad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630705"
---
# <a name="use-annotations-in-packages"></a><span data-ttu-id="a1be2-102">Verwenden von Anmerkungen in Paketen</span><span class="sxs-lookup"><span data-stu-id="a1be2-102">Use Annotations in Packages</span></span>
  <span data-ttu-id="a1be2-103">Der [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer stellt Anmerkungen bereit, damit Pakete selbsterklärend und leichter zu verstehen und zu verwalten sind.</span><span class="sxs-lookup"><span data-stu-id="a1be2-103">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer provides annotations, which you can use to make packages self-documenting and easier to understand and maintain.</span></span> <span data-ttu-id="a1be2-104">Anmerkungen können der Ablaufsteuerung, dem Datenfluss und Ereignishandler-Entwurfsoberflächen des [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designers hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a1be2-104">You can add annotations to the control flow, data flow, and event handler design surfaces of [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="a1be2-105">Anmerkungen können eine beliebige Art von Text enthalten. Sie sind hilfreich, um einem Paket Bezeichnungen, Hinweise und sonstige beschreibende Informationen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a1be2-105">The annotations can contain any type of text, and they are useful for adding labels, comments, and other descriptive information to a package.</span></span> <span data-ttu-id="a1be2-106">Anmerkungen sind eine reine Entwurfszeitfunktion.</span><span class="sxs-lookup"><span data-stu-id="a1be2-106">Annotations are a design-time feature only.</span></span> <span data-ttu-id="a1be2-107">Beispielsweise werden sie nicht in Protokolle geschrieben.</span><span class="sxs-lookup"><span data-stu-id="a1be2-107">For example, they are not written to logs.</span></span>  
  
 <span data-ttu-id="a1be2-108">Wenn Sie die EINGABETASTE drücken, wird der Text in die nächste Zeile umbrochen.</span><span class="sxs-lookup"><span data-stu-id="a1be2-108">When you press ENTER, the text wraps to the next line.</span></span> <span data-ttu-id="a1be2-109">Das Anmerkungsfeld wird automatisch vergrößert, wenn Sie weitere Textzeilen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a1be2-109">The annotation box automatically increases in size as you add additional lines of text.</span></span> <span data-ttu-id="a1be2-110">Paketanmerkungen werden als Klartext im CDATA-Abschnitt der Paketdatei beibehalten.</span><span class="sxs-lookup"><span data-stu-id="a1be2-110">Package annotations are persisted as clear text in the CDATA section of the package file.</span></span>  
  
 <span data-ttu-id="a1be2-111">Weitere Informationen zu Änderungen am Format der Paketdatei finden Sie unter [SSIS-Paketformat](../../2014/integration-services/ssis-package-format.md).</span><span class="sxs-lookup"><span data-stu-id="a1be2-111">For more information about changes to the format of the package file, see [SSIS Package Format](../../2014/integration-services/ssis-package-format.md).</span></span>  
  
 <span data-ttu-id="a1be2-112">Wenn Sie ein Paket speichern, speichert der [!INCLUDE[ssIS](../includes/ssis-md.md)] -Designer die Anmerkungen im Paket.</span><span class="sxs-lookup"><span data-stu-id="a1be2-112">When you save the package, [!INCLUDE[ssIS](../includes/ssis-md.md)] Designer saves the annotations in the package.</span></span>  
  
### <a name="to-add-an-annotation-to-a-package"></a><span data-ttu-id="a1be2-113">So fügen Sie einem Paket eine Anmerkung hinzu</span><span class="sxs-lookup"><span data-stu-id="a1be2-113">To add an annotation to a package</span></span>  
  
-   [<span data-ttu-id="a1be2-114">Hinzufügen einer Anmerkung zu einem Paket</span><span class="sxs-lookup"><span data-stu-id="a1be2-114">Add an Annotation to a Package</span></span>](../../2014/integration-services/add-an-annotation-to-a-package.md)  
  
  
