---
title: Benutzerdefinierte Attribute für CLR-Routinen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- routines [CLR integration]
- SqlFacet attribute
- SqlTrigger attribute
- SqlProcedure attribute
- custom attributes [CLR integration]
- SqlUserDefinedAggregate attribute
- attributes [CLR integration]
- SqlMethod attribute
- SqlFunction attribute
- common language runtime [SQL Server], attributes
- SqlUserDefinedTypeAttribute attribute
ms.assetid: 95069d22-b05d-4670-b053-15ee2a664e33
author: rothja
ms.author: jroth
ms.openlocfilehash: 058bbec7f0f1f63fbd96258a0abe7a6c3d543d88
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607837"
---
# <a name="custom-attributes-for-clr-routines"></a><span data-ttu-id="54c2a-102">Benutzerdefinierte Attribute für CLR-Routinen</span><span class="sxs-lookup"><span data-stu-id="54c2a-102">Custom Attributes for CLR Routines</span></span>
  <span data-ttu-id="54c2a-103">Die aufgelisteten Attribute können auf Common Language Runtime (CLR)-Routinen, benutzerdefinierte Typen und benutzerdefinierte Aggregate angewendet werden, die in registriert sind [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="54c2a-103">The attributes listed can be applied to common language runtime (CLR) routines, user-defined types, and user-defined aggregates that are registered in [!INCLUDE[msCoName](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="54c2a-104">Wenn das Attribut nicht angewendet wird, nimmt [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] den Standardwert an.</span><span class="sxs-lookup"><span data-stu-id="54c2a-104">If the attribute is not applied, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] assumes the default value.</span></span> <span data-ttu-id="54c2a-105">Die aufgelisteten Attribute werden im `Microsoft.SqlServer.Server`-Namespace definiert.</span><span class="sxs-lookup"><span data-stu-id="54c2a-105">The attributes listed are defined in the `Microsoft.SqlServer.Server` namespace.</span></span>  
  
## <a name="the-sqluserdefinedaggregate-attribute"></a><span data-ttu-id="54c2a-106">Das 'SqlUserDefinedAggregate'-Attribut</span><span class="sxs-lookup"><span data-stu-id="54c2a-106">The SqlUserDefinedAggregate Attribute</span></span>  
 <span data-ttu-id="54c2a-107">Das `SqlUserDefinedAggregate`-Attribut gibt an, dass die Methode als benutzerdefiniertes Aggregat registriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="54c2a-107">The `SqlUserDefinedAggregate` attribute indicates that the method should be registered as a user-defined aggregate.</span></span> <span data-ttu-id="54c2a-108">Jedem benutzerdefinierten Aggregat muss dieses Attribut angefügt werden.</span><span class="sxs-lookup"><span data-stu-id="54c2a-108">Every user-defined aggregate must be annotated with this attribute.</span></span>  
  
 <span data-ttu-id="54c2a-109">Weitere Informationen finden Sie unter [SqlUserDefinedAggregateAttribute](https://go.microsoft.com/fwlink/?LinkId=124626).</span><span class="sxs-lookup"><span data-stu-id="54c2a-109">For more information, see [SqlUserDefinedAggregateAttribute](https://go.microsoft.com/fwlink/?LinkId=124626).</span></span>  
  
## <a name="the-sqlfunction-attribute"></a><span data-ttu-id="54c2a-110">Das 'SqlFunction'-Attribut</span><span class="sxs-lookup"><span data-stu-id="54c2a-110">The SqlFunction Attribute</span></span>  
 <span data-ttu-id="54c2a-111">Das `SqlFunction`-Attribut gibt an, dass die Methode als eine Funktion mit den entsprechend festgelegten Funktionsattributen registriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="54c2a-111">The `SqlFunction` attribute indicates the method should be registered as a function, with the appropriate function attributes set.</span></span>  
  
 <span data-ttu-id="54c2a-112">Weitere Informationen finden Sie unter [SqlFunctionAttribute](https://go.microsoft.com/fwlink/?LinkId=128019).</span><span class="sxs-lookup"><span data-stu-id="54c2a-112">For more information, see [SqlFunctionAttribute](https://go.microsoft.com/fwlink/?LinkId=128019).</span></span>  
  
## <a name="the-sqlfacet-attribute"></a><span data-ttu-id="54c2a-113">Das 'SqlFacet'-Attribut</span><span class="sxs-lookup"><span data-stu-id="54c2a-113">The SqlFacet Attribute</span></span>  
 <span data-ttu-id="54c2a-114">Das `SqlFacet`-Attribut wird verwendet, um Informationen über den Rückgabetyp eines UDT-Ausdrucks (Benutzerdefinierter Typ, User Defined Type) zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="54c2a-114">The `SqlFacet` attribute is used to return information about the return type of a user-defined type (UDT) expression.</span></span>  
  
 <span data-ttu-id="54c2a-115">Weitere Informationen finden Sie unter [sqlfaketattribute](https://go.microsoft.com/fwlink/?LinkId=128020).</span><span class="sxs-lookup"><span data-stu-id="54c2a-115">For more information, see [SqlFacetAttribute](https://go.microsoft.com/fwlink/?LinkId=128020).</span></span>  
  
## <a name="the-sqlprocedure-attribute"></a><span data-ttu-id="54c2a-116">Das 'SqlProcedure'-Attribut</span><span class="sxs-lookup"><span data-stu-id="54c2a-116">The SqlProcedure Attribute</span></span>  
 <span data-ttu-id="54c2a-117">Das `SqlProcedure`-Attribut gibt an, dass die Methode als gespeicherte Prozedur registriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="54c2a-117">The `SqlProcedure` attribute indicates the method should be registered as a stored procedure.</span></span> <span data-ttu-id="54c2a-118">Dieses Attribut wird nur von Visual Studio verwendet, um die angegebene Methode automatisch als gespeicherte Prozedur zu registrieren. Sie wird nicht von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] verwendet.</span><span class="sxs-lookup"><span data-stu-id="54c2a-118">This attribute is used only by Visual Studio to register the specified method as a stored procedure automatically; it is not used by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="54c2a-119">Weitere Informationen finden Sie unter [SqlProcedureAttribute](https://go.microsoft.com/fwlink/?LinkId=128021).</span><span class="sxs-lookup"><span data-stu-id="54c2a-119">For more information, see [SqlProcedureAttribute](https://go.microsoft.com/fwlink/?LinkId=128021).</span></span>  
  
## <a name="the-sqltrigger-attribute"></a><span data-ttu-id="54c2a-120">Das 'SqlTrigger'-Attribut</span><span class="sxs-lookup"><span data-stu-id="54c2a-120">The SqlTrigger Attribute</span></span>  
 <span data-ttu-id="54c2a-121">Das `SqlTrigger`-Attribut gibt an, dass die Methode als Trigger registriert werden soll.</span><span class="sxs-lookup"><span data-stu-id="54c2a-121">The `SqlTrigger` attribute indicates the method should be registered as a trigger.</span></span>  
  
 <span data-ttu-id="54c2a-122">Weitere Informationen finden Sie unter [SqlTriggerContext](https://go.microsoft.com/fwlink/?LinkId=128022) und [SqlTriggerAttribute](https://go.microsoft.com/fwlink/?LinkId=203898).</span><span class="sxs-lookup"><span data-stu-id="54c2a-122">For more information, see [SqlTriggerContext](https://go.microsoft.com/fwlink/?LinkId=128022) and [SqlTriggerAttribute](https://go.microsoft.com/fwlink/?LinkId=203898).</span></span>  
  
## <a name="the-sqluserdefinedtypeattribute"></a><span data-ttu-id="54c2a-123">Das 'SqlUserDefinedTypeAttribute'-Attribut</span><span class="sxs-lookup"><span data-stu-id="54c2a-123">The SqlUserDefinedTypeAttribute</span></span>  
 <span data-ttu-id="54c2a-124">Sie können das SqlUserDefinedTypeAttribute-Attribut in eine Klassendefinition in der Assembly übernehmen.</span><span class="sxs-lookup"><span data-stu-id="54c2a-124">You can apply the SqlUserDefinedTypeAttribute to a class definition in the assembly.</span></span> <span data-ttu-id="54c2a-125">Es bewirkt, dass [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] einen benutzerdefinierten Typ erstellt, der an die Klassendefinition mit diesem benutzerdefinierten Attribut gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="54c2a-125">It causes [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to create a user-defined type that is bound to the class definition which has this custom attribute.</span></span>  
  
 <span data-ttu-id="54c2a-126">Weitere Informationen finden Sie unter [SqlUserDefinedTypeAttribute](https://go.microsoft.com/fwlink/?LinkId=128024).</span><span class="sxs-lookup"><span data-stu-id="54c2a-126">For more information, see [SqlUserDefinedTypeAttribute](https://go.microsoft.com/fwlink/?LinkId=128024).</span></span>  
  
## <a name="the-sqlmethod-attribute"></a><span data-ttu-id="54c2a-127">Das 'SqlMethod'-Attribut</span><span class="sxs-lookup"><span data-stu-id="54c2a-127">The SqlMethod Attribute</span></span>  
 <span data-ttu-id="54c2a-128">Das `SqlMethod`-Attribut gibt die Verwendung und die Datenzugriffseigenschaften einer Methode oder Eigenschaft in einem benutzerdefinierten Typ (UDT) an.</span><span class="sxs-lookup"><span data-stu-id="54c2a-128">The `SqlMethod` attribute is used to indicate the determinism and data access properties of a method or a property on a UDT.</span></span>  
  
 <span data-ttu-id="54c2a-129">Weitere Informationen finden Sie unter [SqlMethodAttribute](https://go.microsoft.com/fwlink/?LinkId=128025).</span><span class="sxs-lookup"><span data-stu-id="54c2a-129">For more information, see [SqlMethodAttribute](https://go.microsoft.com/fwlink/?LinkId=128025).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54c2a-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="54c2a-130">See Also</span></span>  
 <span data-ttu-id="54c2a-131">[Benutzerdefinierte CLR-Aggregate](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md) </span><span class="sxs-lookup"><span data-stu-id="54c2a-131">[CLR User-Defined Aggregates](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-aggregates.md) </span></span>  
 <span data-ttu-id="54c2a-132">[Benutzerdefinierte CLR-Funktionen](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span><span class="sxs-lookup"><span data-stu-id="54c2a-132">[CLR User-Defined Functions](../../clr-integration-database-objects-user-defined-functions/clr-user-defined-functions.md) </span></span>  
 <span data-ttu-id="54c2a-133">[Benutzerdefinierte CLR-Typen](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span><span class="sxs-lookup"><span data-stu-id="54c2a-133">[CLR User-Defined Types](../../clr-integration-database-objects-user-defined-types/clr-user-defined-types.md) </span></span>  
 <span data-ttu-id="54c2a-134">[Gespeicherte CLR-Prozeduren](../../../database-engine/dev-guide/clr-stored-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="54c2a-134">[CLR Stored Procedures](../../../database-engine/dev-guide/clr-stored-procedures.md) </span></span>  
 [<span data-ttu-id="54c2a-135">CLR-Trigger</span><span class="sxs-lookup"><span data-stu-id="54c2a-135">CLR Triggers</span></span>](../../../database-engine/dev-guide/clr-triggers.md)  
  
  
