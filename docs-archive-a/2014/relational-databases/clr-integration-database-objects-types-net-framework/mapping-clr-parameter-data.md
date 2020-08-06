---
title: Mapping von CLR-Parameter Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
helpviewer_keywords:
- SqlBinary data type
- SqlInt16 data type
- SqlMoney data type
- SqlString data type
- SqlSingle data type
- data types [CLR integration]
- SqlInt64 data type
- SqlDateTime data type
- SqlXml data type
- SqlBoolean data type
- SqlDecimal data type
- SqlBytes data type
- mapping data types [CLR integration]
- SqlChars data type
- SqlInt32 data type
ms.assetid: 89b43ee9-b9ad-4281-a4bf-c7c8d116daa2
author: rothja
ms.author: jroth
ms.openlocfilehash: 7025c5180eac793534961af63df9ac701c95c03f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725958"
---
# <a name="mapping-clr-parameter-data"></a><span data-ttu-id="98227-102">Zuordnen von CLR-Parameterdaten</span><span class="sxs-lookup"><span data-stu-id="98227-102">Mapping CLR Parameter Data</span></span>
  <span data-ttu-id="98227-103">In der folgenden Tabelle [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sind die-Datentypen, ihre Entsprechungen in der Common Language Runtime (CLR) für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] im `System.Data.SqlTypes` -Namespace und ihre systemeigenen CLR-Entsprechungen in der [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="98227-103">The following table lists [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, their equivalents in the common language runtime (CLR) for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the `System.Data.SqlTypes` namespace, and their native CLR equivalents in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework.</span></span>  
  
||||  
|-|-|-|  
|<span data-ttu-id="98227-104">**SQL Server-Datentyp**</span><span class="sxs-lookup"><span data-stu-id="98227-104">**SQL Server data type**</span></span>|<span data-ttu-id="98227-105">Typ (in System.Data.SqlTypes oder Microsoft.SqlServer.Types)</span><span class="sxs-lookup"><span data-stu-id="98227-105">Type (in System.Data.SqlTypes or Microsoft.SqlServer.Types)</span></span>|<span data-ttu-id="98227-106">**CLR-Datentyp (.NET Framework)**</span><span class="sxs-lookup"><span data-stu-id="98227-106">**CLR data type (.NET Framework)**</span></span>|  
|`bigint`|`SqlInt64`|<span data-ttu-id="98227-107">**Int64, NULL-Werte zulassen\<Int64>**</span><span class="sxs-lookup"><span data-stu-id="98227-107">**Int64, Nullable\<Int64>**</span></span>|  
|`binary`|`SqlBytes, SqlBinary`|`Byte[]`|  
|`bit`|`SqlBoolean`|<span data-ttu-id="98227-108">**Boolescher Wert, NULL-Werte zulassen\<Boolean>**</span><span class="sxs-lookup"><span data-stu-id="98227-108">**Boolean, Nullable\<Boolean>**</span></span>|  
|`char`|<span data-ttu-id="98227-109">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-109">None</span></span>|<span data-ttu-id="98227-110">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-110">None</span></span>|  
|`cursor`|<span data-ttu-id="98227-111">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-111">None</span></span>|<span data-ttu-id="98227-112">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-112">None</span></span>|  
|`date`|`SqlDateTime`|<span data-ttu-id="98227-113">**DateTime, NULL-Werte zulassen\<DateTime>**</span><span class="sxs-lookup"><span data-stu-id="98227-113">**DateTime, Nullable\<DateTime>**</span></span>|  
|`datetime`|`SqlDateTime`|<span data-ttu-id="98227-114">**DateTime, NULL-Werte zulassen\<DateTime>**</span><span class="sxs-lookup"><span data-stu-id="98227-114">**DateTime, Nullable\<DateTime>**</span></span>|  
|`datetime2`|<span data-ttu-id="98227-115">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-115">None</span></span>|<span data-ttu-id="98227-116">**DateTime, NULL-Werte zulassen\<DateTime>**</span><span class="sxs-lookup"><span data-stu-id="98227-116">**DateTime, Nullable\<DateTime>**</span></span>|  
|`DATETIMEOFFSET`|`None`|<span data-ttu-id="98227-117">**DateTimeOffset, NULL-Werte zulassen\<DateTimeOffset>**</span><span class="sxs-lookup"><span data-stu-id="98227-117">**DateTimeOffset, Nullable\<DateTimeOffset>**</span></span>|  
|`decimal`|`SqlDecimal`|<span data-ttu-id="98227-118">**Decimal, NULL-Werte zulassen\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="98227-118">**Decimal, Nullable\<Decimal>**</span></span>|  
|`float`|`SqlDouble`|<span data-ttu-id="98227-119">**Double, NULL-Werte zulassen\<Double>**</span><span class="sxs-lookup"><span data-stu-id="98227-119">**Double, Nullable\<Double>**</span></span>|  
|`geography`|`SqlGeography`<br /><br /> <span data-ttu-id="98227-120">`SqlGeography`wird in Microsoft.SqlServer.Types.dll definiert, das mit SQL Server installiert wird und aus dem [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Feature Pack](https://www.microsoft.com/download/details.aspx?id=53164)heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="98227-120">`SqlGeography` is defined in Microsoft.SqlServer.Types.dll, which is installed with SQL Server and can be downloaded from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][feature pack](https://www.microsoft.com/download/details.aspx?id=53164).</span></span>|<span data-ttu-id="98227-121">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-121">None</span></span>|  
|`geometry`|`SqlGeometry`<br /><br /> <span data-ttu-id="98227-122">`SqlGeometry`wird in Microsoft.SqlServer.Types.dll definiert, das mit SQL Server installiert wird und aus dem [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Feature Pack](https://www.microsoft.com/download/details.aspx?id=53164)heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="98227-122">`SqlGeometry` is defined in Microsoft.SqlServer.Types.dll, which is installed with SQL Server and can be downloaded from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][feature pack](https://www.microsoft.com/download/details.aspx?id=53164).</span></span>|<span data-ttu-id="98227-123">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-123">None</span></span>|  
|`hierarchyid`|`SqlHierarchyId`<br /><br /> <span data-ttu-id="98227-124">`SqlHierarchyId`wird in Microsoft.SqlServer.Types.dll definiert, das mit SQL Server installiert wird und aus dem [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] [Feature Pack](https://www.microsoft.com/download/details.aspx?id=53164)heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="98227-124">`SqlHierarchyId` is defined in Microsoft.SqlServer.Types.dll, which is installed with SQL Server and can be downloaded from the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)][feature pack](https://www.microsoft.com/download/details.aspx?id=53164).</span></span>|<span data-ttu-id="98227-125">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-125">None</span></span>|  
|`image`|<span data-ttu-id="98227-126">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-126">None</span></span>|<span data-ttu-id="98227-127">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-127">None</span></span>|  
|`int`|`SqlInt32`|<span data-ttu-id="98227-128">**Int32, NULL-Werte zulassen\<Int32>**</span><span class="sxs-lookup"><span data-stu-id="98227-128">**Int32, Nullable\<Int32>**</span></span>|  
|`money`|`SqlMoney`|<span data-ttu-id="98227-129">**Decimal, NULL-Werte zulassen\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="98227-129">**Decimal, Nullable\<Decimal>**</span></span>|  
|`nchar`|`SqlChars, SqlString`|`String, Char[]`|  
|`ntext`|<span data-ttu-id="98227-130">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-130">None</span></span>|<span data-ttu-id="98227-131">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-131">None</span></span>|  
|`numeric`|`SqlDecimal`|<span data-ttu-id="98227-132">**Decimal, NULL-Werte zulassen\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="98227-132">**Decimal, Nullable\<Decimal>**</span></span>|  
|`nvarchar`|`SqlChars, SqlString`<br /><br /> <span data-ttu-id="98227-133">`SQLChars` bietet eine bessere Übereinstimmung für Datenübertragungen und Datenzugriff, und `SQLString` bietet eine bessere Übereinstimmung für die Durchführung von Zeichenfolgenvorgängen.</span><span class="sxs-lookup"><span data-stu-id="98227-133">`SQLChars` is a better match for data transfer and access, and `SQLString` is a better match for performing String operations.</span></span>|`String, Char[]`|  
|`nvarchar(1), nchar(1)`|`SqlChars, SqlString`|<span data-ttu-id="98227-134">**Char, String, Char [], Nullable\<char>**</span><span class="sxs-lookup"><span data-stu-id="98227-134">**Char, String, Char[], Nullable\<char>**</span></span>|  
|`real`|<span data-ttu-id="98227-135">`SqlSingle` (der Bereich von `SqlSingle` ist jedoch größer als `real`)</span><span class="sxs-lookup"><span data-stu-id="98227-135">`SqlSingle` (the range of `SqlSingle`, however, is larger than `real`)</span></span>|<span data-ttu-id="98227-136">**Single, Nullable\<Single>**</span><span class="sxs-lookup"><span data-stu-id="98227-136">**Single, Nullable\<Single>**</span></span>|  
|`rowversion`|<span data-ttu-id="98227-137">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-137">None</span></span>|`Byte[]`|  
|`smallint`|`SqlInt16`|<span data-ttu-id="98227-138">**Int16, NULL-Werte zulassen\<Int16>**</span><span class="sxs-lookup"><span data-stu-id="98227-138">**Int16, Nullable\<Int16>**</span></span>|  
|`smallmoney`|`SqlMoney`|<span data-ttu-id="98227-139">**Decimal, NULL-Werte zulassen\<Decimal>**</span><span class="sxs-lookup"><span data-stu-id="98227-139">**Decimal, Nullable\<Decimal>**</span></span>|  
|`sql_variant`|<span data-ttu-id="98227-140">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-140">None</span></span>|`Object`|  
|`table`|<span data-ttu-id="98227-141">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-141">None</span></span>|<span data-ttu-id="98227-142">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-142">None</span></span>|  
|`text`|<span data-ttu-id="98227-143">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-143">None</span></span>|<span data-ttu-id="98227-144">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-144">None</span></span>|  
|`time`|<span data-ttu-id="98227-145">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-145">None</span></span>|<span data-ttu-id="98227-146">**TimeSpan, Nullable\<TimeSpan>**</span><span class="sxs-lookup"><span data-stu-id="98227-146">**TimeSpan, Nullable\<TimeSpan>**</span></span>|  
|`timestamp`|<span data-ttu-id="98227-147">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-147">None</span></span>|<span data-ttu-id="98227-148">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-148">None</span></span>|  
|`tinyint`|`SqlByte`|<span data-ttu-id="98227-149">**Byte, NULL-Werte zulassen\<Byte>**</span><span class="sxs-lookup"><span data-stu-id="98227-149">**Byte, Nullable\<Byte>**</span></span>|  
|`uniqueidentifier`|`SqlGuid`|<span data-ttu-id="98227-150">**GUID, NULL-Werte zulassen\<Guid>**</span><span class="sxs-lookup"><span data-stu-id="98227-150">**Guid, Nullable\<Guid>**</span></span>|  
|`User-defined type(UDT)`|<span data-ttu-id="98227-151">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-151">None</span></span>|<span data-ttu-id="98227-152">Dieselbe Klasse, die in derselben Assembly oder einer abhängigen Assembly an den benutzerdefinierten Typ gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="98227-152">The same class that is bound to the user-defined type in the same assembly or a dependent assembly.</span></span>|  
|<span data-ttu-id="98227-153">**varbinary**</span><span class="sxs-lookup"><span data-stu-id="98227-153">**varbinary**</span></span>|`SqlBytes, SqlBinary`|`Byte[]`|  
|`varbinary(1), binary(1)`|`SqlBytes, SqlBinary`|<span data-ttu-id="98227-154">**Byte, Byte [], NULL-Werte zulassen\<byte>**</span><span class="sxs-lookup"><span data-stu-id="98227-154">**byte, Byte[], Nullable\<byte>**</span></span>|  
|`varchar`|<span data-ttu-id="98227-155">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-155">None</span></span>|<span data-ttu-id="98227-156">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-156">None</span></span>|  
|`xml`|`SqlXml`|<span data-ttu-id="98227-157">Keine</span><span class="sxs-lookup"><span data-stu-id="98227-157">None</span></span>|  
  
## <a name="automatic-data-type-conversion-with-out-parameters"></a><span data-ttu-id="98227-158">Automatische Datentypkonvertierung mit Out-Parametern</span><span class="sxs-lookup"><span data-stu-id="98227-158">Automatic Data Type Conversion with Out Parameters</span></span>  
 <span data-ttu-id="98227-159">Eine CLR-Methode kann Informationen an den aufrufenden Code oder das aufrufende Programm zurückgeben, indem sie einen Eingabeparameter mit dem `out`-Modifizierer (Microsoft Visual C#) oder `<Out()> ByRef` (Microsoft Visual Basic) markiert. Wenn der Eingabeparameter ein CLR-Datentyp im `System.Data.SqlTypes`-Namespace ist und ein aufrufendes Programm seinen entsprechenden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentyp als Eingabeparameter angibt, wird automatisch eine Typkonvertierung durchgeführt, wenn die CLR-Methode den Datentyp zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="98227-159">A CLR method can return information to the calling code or program by marking an input parameter with the `out` modifier (Microsoft Visual C#) or `<Out()> ByRef` (Microsoft Visual Basic) If the input parameter is a CLR data type in the `System.Data.SqlTypes` namespace, and the calling program specifies its equivalent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type as the input parameter, a type conversion occurs automatically when the CLR method returns the data type.</span></span>  
  
 <span data-ttu-id="98227-160">Beispielsweise verfügt die folgende CLR-gespeicherte Prozedur über einen Eingabeparameter von `SqlInt32` und einen CLR-Datentyp, der mit `out` (C#) oder `<Out()> ByRef` (Visual Basic) markiert ist:</span><span class="sxs-lookup"><span data-stu-id="98227-160">For example, the following CLR stored procedure has an input parameter of `SqlInt32` CLR data type that is marked with `out` (C#) or `<Out()> ByRef` (Visual Basic):</span></span>  
  
```csharp  
[Microsoft.SqlServer.Server.SqlProcedure]  
public static void PriceSum(out SqlInt32 value)  
{ ... }  
```  
  
```vb  
<Microsoft.SqlServer.Server.SqlProcedure> _  
Public Shared Sub PriceSum( <Out()> ByRef value As SqlInt32)  
...  
End Sub  
```  
  
 <span data-ttu-id="98227-161">Nachdem die Assembly in der Datenbank erstellt wurde, wird die gespeicherte Prozedur in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit dem folgenden Transact-SQL erstellt, das einen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentyp von `int` als einen OUTPUT-Parameter angibt:</span><span class="sxs-lookup"><span data-stu-id="98227-161">After the assembly is built and created in the database, the stored procedure is created in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with the following Transact-SQL, which specifies a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type of `int` as an OUTPUT parameter:</span></span>  
  
```  
CREATE PROCEDURE PriceSum (@sum int OUTPUT)  
AS EXTERNAL NAME TestStoredProc.StoredProcedures.PriceSum  
```  
  
 <span data-ttu-id="98227-162">Wenn die CLR-gespeicherte Prozedur aufgerufen wird, wird der `SqlInt32`-Datentyp automatisch in einen `int`-Datentyp konvertiert und an das aufrufende Programm zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="98227-162">When the CLR stored procedure is called, the `SqlInt32` data type is automatically converted to an `int` data type, and returned to the calling program.</span></span>  
  
 <span data-ttu-id="98227-163">Allerdings können nicht alle CLR-Datentypen automatisch durch einen Out-Parameter in ihre entsprechenden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datentypen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="98227-163">Not all CLR data types can be automatically converted to their equivalent [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types through an out parameter, however.</span></span> <span data-ttu-id="98227-164">In der folgenden Tabelle werden diese Ausnahmen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="98227-164">The following table lists these exceptions.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="98227-165">**CLR-Datentyp (SQL Server)**</span><span class="sxs-lookup"><span data-stu-id="98227-165">**CLR data type (SQL Server)**</span></span>|<span data-ttu-id="98227-166">**SQL Server-Datentyp**</span><span class="sxs-lookup"><span data-stu-id="98227-166">**SQL Server data type**</span></span>|  
|`Decimal`|<span data-ttu-id="98227-167">SMALLMONEY</span><span class="sxs-lookup"><span data-stu-id="98227-167">smallmoney</span></span>|  
|`SqlMoney`|<span data-ttu-id="98227-168">SMALLMONEY</span><span class="sxs-lookup"><span data-stu-id="98227-168">smallmoney</span></span>|  
|`Decimal`|<span data-ttu-id="98227-169">money</span><span class="sxs-lookup"><span data-stu-id="98227-169">money</span></span>|  
|`DateTime`|<span data-ttu-id="98227-170">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="98227-170">smalldatetime</span></span>|  
|`SQLDateTime`|<span data-ttu-id="98227-171">smalldatetime</span><span class="sxs-lookup"><span data-stu-id="98227-171">smalldatetime</span></span>|  
  
## <a name="change-history"></a><span data-ttu-id="98227-172">Änderungsverlauf</span><span class="sxs-lookup"><span data-stu-id="98227-172">Change History</span></span>  
  
|<span data-ttu-id="98227-173">Aktualisierter Inhalt</span><span class="sxs-lookup"><span data-stu-id="98227-173">Updated content</span></span>|  
|---------------------|  
|<span data-ttu-id="98227-174">Die `SqlGeography`-, `SqlGeometry`- und `SqlHierarchyId`-Typen wurden der Zuordnungstabelle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="98227-174">Added `SqlGeography`, `SqlGeometry`, and `SqlHierarchyId` types to the mapping table.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="98227-175">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="98227-175">See Also</span></span>  
 [<span data-ttu-id="98227-176">SQL Server-Datentypen in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="98227-176">SQL Server Data Types in the .NET Framework</span></span>](sql-server-data-types-in-the-net-framework.md)  
  
  
