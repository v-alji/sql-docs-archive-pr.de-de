---
title: Erstellen von Skripts mit Vorlagen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: ed48014c-3fc9-48ff-8c0f-8d1822195f14
author: stevestein
ms.author: sstein
ms.openlocfilehash: b404ecc505e93c302e4c737f9c0b0161d9015519
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717149"
---
# <a name="create-scripts-using-templates"></a><span data-ttu-id="0016b-102">Erstellen von Skripts mit Vorlagen</span><span class="sxs-lookup"><span data-stu-id="0016b-102">Create Scripts Using Templates</span></span>
  <span data-ttu-id="0016b-103">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] stellt eine große Anzahl von Skriptvorlagen zur Verfügung, die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen für viele häufig ausgeführte Aufgaben umfassen.</span><span class="sxs-lookup"><span data-stu-id="0016b-103">Microsoft [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] provides a large number of script templates containing the [!INCLUDE[tsql](../../includes/tsql-md.md)] statements for many common tasks.</span></span> <span data-ttu-id="0016b-104">Diese Vorlagen enthalten Parameter für Werte, die vom Benutzer angegeben werden, wie z. B. der Tabellenname.</span><span class="sxs-lookup"><span data-stu-id="0016b-104">These templates contain parameters for the user-provided values such as a table name.</span></span> <span data-ttu-id="0016b-105">Wenn Sie Parameter verwenden, brauchen Sie den Namen nur einmal einzugeben, er wird dann automatisch an alle erforderlichen Stellen im Skript kopiert.</span><span class="sxs-lookup"><span data-stu-id="0016b-105">Using the parameters, you can type the name once and then automatically copy the name to all the necessary locations within the script.</span></span> <span data-ttu-id="0016b-106">Sie können auch eigene, benutzerspezifische Vorlagen für die Skripts erstellen, die Sie am häufigsten benötigen.</span><span class="sxs-lookup"><span data-stu-id="0016b-106">You can write your own custom templates to support the scripts that you write most often.</span></span> <span data-ttu-id="0016b-107">Sie können die Vorlagenstruktur neu anordnen, Vorlagen verschieben oder neue Ordner für Vorlagen anlegen.</span><span class="sxs-lookup"><span data-stu-id="0016b-107">You can also reorganize the template tree, moving templates or creating new folders to hold the templates.</span></span> <span data-ttu-id="0016b-108">In der folgenden Übung verwenden Sie eine Vorlage zum Anlegen einer Datenbank.</span><span class="sxs-lookup"><span data-stu-id="0016b-108">In the following practice, you will use a template to create a database, specifying collation template.</span></span>  
  
## <a name="using-templates"></a><span data-ttu-id="0016b-109">Verwenden von Vorlagen</span><span class="sxs-lookup"><span data-stu-id="0016b-109">Using Templates</span></span>  
  
#### <a name="to-create-a-script-using-a-template"></a><span data-ttu-id="0016b-110">So erstellen Sie ein Skript mithilfe einer Vorlage</span><span class="sxs-lookup"><span data-stu-id="0016b-110">To create a script using a template</span></span>  
  
1.  <span data-ttu-id="0016b-111">Klicken Sie in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)]im Menü **Ansicht** auf **Vorlagen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="0016b-111">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], on the **View** menu, click **Template Explorer**.</span></span>  
  
2.  <span data-ttu-id="0016b-112">Die Vorlagen im Vorlagen-Explorer sind in Gruppen angeordnet.</span><span class="sxs-lookup"><span data-stu-id="0016b-112">The templates in Template Explorer are organized into groups.</span></span> <span data-ttu-id="0016b-113">Erweitern Sie **Datenbank**, und doppelklicken Sie anschließend auf **Datenbank erstellen**.</span><span class="sxs-lookup"><span data-stu-id="0016b-113">Expand **Database**, and then double-click **Create Database**.</span></span>  
  
3.  <span data-ttu-id="0016b-114">Vervollständigen Sie im Dialogfeld **Verbindung mit Datenbank-Engine herstellen** die Verbindungseinstellungen, und klicken Sie anschließend auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="0016b-114">In the **Connect to Database Engine** dialog box, complete the connection information and then click **Connect**.</span></span> <span data-ttu-id="0016b-115">Ein neues Fenster des Abfrage-Editors wird geöffnet, in dem der Inhalt der Vorlage **Datenbank erstellen** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="0016b-115">A new Query Editor window opens, containing the contents of the **Create Database** template.</span></span>  
  
4.  <span data-ttu-id="0016b-116">Klicken Sie im Menü **Abfrage** auf **Werte für Vorlagenparameter angeben**.</span><span class="sxs-lookup"><span data-stu-id="0016b-116">On the **Query** menu, click **Specify Values for Template Parameters**.</span></span>  
  
5.  <span data-ttu-id="0016b-117">Im Dialogfeld **Werte für Vorlagenparameter angeben** enthält die **Wert** -Spalte einen empfohlenen Wert für den Parameter **Database_Name** .</span><span class="sxs-lookup"><span data-stu-id="0016b-117">In the **Specify Values for Template Parameters** dialog box, the **Value** column contains a suggested value for the **Database_Name** parameter.</span></span> <span data-ttu-id="0016b-118">Geben Sie im Feld des Parameters **Database_Name** den Begriff **Marketing**ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="0016b-118">In the **Database Name** parameter box, type **Marketing**, and then click **OK**.</span></span> <span data-ttu-id="0016b-119">"Marketing" wird jetzt im Skript an mehreren Stellen eingefügt.</span><span class="sxs-lookup"><span data-stu-id="0016b-119">Note how "Marketing" is inserted into the script in several locations.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="0016b-120">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="0016b-120">Next Task in Lesson</span></span>  
 [<span data-ttu-id="0016b-121">Erstellen von benutzerdefinierten Vorlagen</span><span class="sxs-lookup"><span data-stu-id="0016b-121">Create Custom Templates</span></span>](lesson-3-2-create-custom-templates.md)  
  
  
