---
title: "CUtlProps, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CUtlProps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUtlProps (classe)"
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUtlProps, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente les propriétés d'une série d'interfaces de propriété OLE DB \(par exemple, `IDBProperties`, `IDBProperties`, et `IRowsetInfo`\).  
  
## Syntaxe  
  
```  
template < class T >  
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase  
```  
  
#### Paramètres  
 `T`  
 La classe qui contient `BEGIN_PROPSET_MAP`.  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[GetPropValue](../../data/oledb/cutlprops-getpropvalue.md)|Obtient une propriété d'un ensemble de propriétés.|  
|[IsValidValue](../../data/oledb/cutlprops-isvalidvalue.md)|Utilisé pour valider une valeur avant de définir une propriété.|  
|[OnInterfaceRequested](../../data/oledb/cutlprops-oninterfacerequested.md)|Gère les requêtes pour une interface facultative lorsqu'un consommateur appelle une méthode sur l'interface de création d'un objet.|  
|[OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)|Appelé après avoir défini une propriété pour gérer les propriétés chaînées.|  
|[SetPropValue](../../data/oledb/cutlprops-setpropvalue.md)|Définit une propriété dans un jeu de propriétés.|  
  
## Notes  
 Une grande partie de cette classe est un ensemble d'implémentation.  
  
 `CUtlProps` contient deux membres pour définir les propriétés en interne : [GetPropValue](../../data/oledb/cutlprops-getpropvalue.md) et [SetPropValue](../../data/oledb/cutlprops-setpropvalue.md).  
  
 Pour plus d'informations sur les macros utilisées dans un mappage de propriété, consultez [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md) et [END\_PROPSET\_MAP](../../data/oledb/end-propset-map.md).  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)