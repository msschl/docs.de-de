---
title: Angeben von Beziehungen zwischen Elementen ohne Verschachtelung
ms.date: 03/30/2017
ms.assetid: e31325da-7691-4d33-acf4-99fccca67006
ms.openlocfilehash: d04a3d946b87c7203497313c6e21a75ef69f50eb
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45609592"
---
# <a name="specify-relations-between-elements-with-no-nesting"></a>Angeben von Beziehungen zwischen Elementen ohne Verschachtelung
Wenn Elemente nicht geschachtelt sind, werden keine impliziten Beziehungen erstellt. Sie können jedoch explizit angeben von Beziehungen zwischen Elementen, die mit nicht geschachtelt sind die **msdata: Relationship** Anmerkung.  
  
 Das folgende Beispiel zeigt ein XML-Schema, in dem die **msdata: Relationship** -Anmerkung zwischen den **Reihenfolge** und **OrderDetail** Elemente, die nicht geschachtelt. Die **msdata: Relationship** -Anmerkung als untergeordnetes Element von der **Schema** Element.  
  
```xml  
<xs:schema id="MyDataSet" xmlns=""   
             xmlns:xs="http://www.w3.org/2001/XMLSchema"   
             xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
 <xs:element name="MyDataSet" msdata:IsDataSet="true">  
  <xs:complexType>  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="OrderDetail">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNo" type="xs:string" />  
           <xs:element name="ItemNo" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
      <xs:element name="Order">  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element name="OrderNumber" type="xs:string" />  
           <xs:element name="EmpNumber" type="xs:string" />  
         </xs:sequence>  
       </xs:complexType>  
      </xs:element>  
    </xs:choice>  
  </xs:complexType>  
  
  </xs:element>  
   <xs:annotation>  
     <xs:appinfo>  
       <msdata:Relationship name="OrdOrderDetailRelation"  
                            msdata:parent="Order"   
                            msdata:child="OrderDetail"   
                            msdata:parentkey="OrderNumber"   
                            msdata:childkey="OrderNo"/>  
     </xs:appinfo>  
  </xs:annotation>  
</xs:schema>  
```  
  
 Die XML-Schema Definition Language (XSD)-Schemazuordnungsprozess erstellt eine <xref:System.Data.DataSet> mit **Reihenfolge** und **OrderDetail** Tabellen und eine Beziehung zwischen diesen beiden Tabellen angegeben werden, wie unten dargestellt.  
  
```  
RelationName: OrdOrderDetailRelation  
ParentTable: Order  
ParentColumns: OrderNumber   
ChildTable: OrderDetail  
ChildColumns: OrderNo   
Nested: False  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 [Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
