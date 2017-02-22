---
title: "IRowsetInfoImpl, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetInfoImpl"
  - "IRowsetInfoImpl"
  - "ATL::IRowsetInfoImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetInfoImpl (classe)"
ms.assetid: 9c654155-7727-464e-bd31-143e68391a47
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IRowsetInfoImpl, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Assure l'implémentation pour une [IRowsetInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx) interface.  
  
## Syntaxe  
  
```  
template <class T, class PropClass = T>  
class ATL_NO_VTABLE IRowsetInfoImpl :   
   public IRowsetInfo,    
   public CUtlProps<PropClass>  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IRowsetInfoImpl`.  
  
 `PropClass`  
 Une classe de propriété définissable par l'utilisateur qui a par défaut la `T`.  
  
## Membres  
  
### Methodes d'interface  
  
|||  
|-|-|  
|[ObtenirPropriétés](../../data/oledb/irowsetinfoimpl-getproperties.md)|Retourne les paramètres actuels de toutes les propriétés prises en charge par le jeu de lignes.|  
|[Obtenir la référence d'un ensemble de rangées.](../../data/oledb/irowsetinfoimpl-getreferencedrowset.md)|Retourne un pointeur d'interface vers le jeu de lignes sur lequel un signet ou un chapitre est appliqué.|  
|[GetSpecification](../../data/oledb/irowsetinfoimpl-getspecification.md)|Retourne un pointeur d'interface sur l'objet \(commande ou session\) qui a créé ce jeu de lignes.|  
  
## Notes  
 Interface forcé sur les ensembles de lignes.  Cette classe implémente les propriétés d'ensemble de lignes à l'aide de [mappage de propriété](../../data/oledb/begin-propset-map.md) définies dans la classe de commande.  Bien que la classe d'ensemble de rangées semble s'utiliser avec la commande de la classe d'ensemble de propriétés, l'ensemble de lignes est fourni avec sa propre copie des propriétés d'exécution, lorsqu'il est créé par une commande ou un objet de session.  
  
## Configuration requise  
 **En\-tête :** altdb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)