---
title: "CNoRowset, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CNoRowset"
  - "ATL::CNoRowset<TAccessor>"
  - "CNoRowset"
  - "ATL.CNoRowset<TAccessor>"
  - "ATL::CNoRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNoRowset (classe)"
ms.assetid: 55c6c7a4-9e3a-4775-a2dd-c8b333012fa6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CNoRowset, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Peut être utilisée comme un argument type \(`TRowset`\) pour [CCommand](../../data/oledb/ccommand-class.md) ou [CTable](../../data/oledb/ctable-class.md).  
  
## Syntaxe  
  
```  
template <class TAccessor = CAccessorBase>  
class CNoRowset  
```  
  
#### Paramètres  
 `TAccessor`  
 Un classe accesseur.  La valeur par défaut est `CAccessorBase`.  
  
## Notes  
 Utilisez `CNoRowset` comme argument type si la commande ne renvoie pas d'ensemble de lignes.  
  
 `CNoRowset` implémente les méthodes stub suivantes, qui correspondent aux autres méthodes de la classe d'accesseur :  
  
-   **BindFinished** indique si la liaison est terminée \(renvoie `S_OK`\).  
  
-   **Close** \- Lignes de versions et l'interface actuelle de IRowset.  
  
-   `GetIID` \- Récupère l'ID d'interface d'un point de connexion.  
  
-   **GetInterface** \- Récupère une interface.  
  
-   `GetInterfacePtr` \- Renvoie le pointeur d'interface encapsulée.  
  
-   **SetAccessor** \- définit un pointeur vers l'accesseur.  
  
-   **SetupOptionalRowsetInterfaces** \- installe les interfaces pour l'ensemble de lignes.  
  
## Configuration requise  
 **En\-tête :** : atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)