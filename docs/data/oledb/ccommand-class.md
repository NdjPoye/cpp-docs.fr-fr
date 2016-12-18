---
title: "CCommand, classe | Microsoft Docs"
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
  - "ATL::CCommand"
  - "CCommand"
  - "ATL.CCommand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCommand (classe)"
ms.assetid: 0760bfc5-b9ee-4aee-8e54-31bd78714d3a
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCommand, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit des méthodes pour définir et exécuter une commande.  
  
## Syntaxe  
  
```  
template <  
   class TAccessor = CNoAccessor,  
   template < typename T > class TRowset = CRowset,  
   class TMultiple = CNoMultipleResults   
>  
class CCommand :   
   public CAccessorRowset <  
      TAccessor,   
      TRowset   
   >,  
   public CCommandBase,  
   public TMultiple  
```  
  
#### Paramètres  
 `TAccessor`  
 Type de classe d'accesseur \(par exemple `CDynamicParameterAccessor`, `CDynamicStringAccessor`, ou `CEnumeratorAccessor`\) que vous souhaitez que la commande utilise.  La valeur par défaut est `CNoAccessor`, qui indique que la classe ne prend pas en charge les paramètres ou les colonnes de sortie.  
  
 `TRowset`  
 Le type d'ensemble de lignes \(par exemple `CArrayRowset` ou `CNoRowset`\) que vous souhaitez que la commande utilise.  La valeur par défaut est `CRowset`.  
  
 `TMultiple`  
 Pour utiliser la commande OLE DB qui peut retourner des résultats, spécifiez [CMultipleResults](../../data/oledb/cmultipleresults-class.md).  Sinon, utilisez [CNoMultipleResults](../../data/oledb/cnomultipleresults-class.md).  Pour plus de détails, consultez [IMultipleResults](https://msdn.microsoft.com/en-us/library/ms721289.aspx).  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[Fermer](../../data/oledb/ccommand-close.md)|Ferme la commande active.|  
|[GetNextResult](../../data/oledb/ccommand-getnextresult.md)|Extrait le résultat suivant en utilisant plusieurs jeux de résultats.|  
|[Ouvrez .](../../data/oledb/ccommand-open.md)|Exécute et lie également la commande.|  
  
### Méthodes héritées  
  
|||  
|-|-|  
|[Créer](../../data/oledb/ccommand-create.md)|Crée une nouvelle commande pour la session spécifiée, puis définit le texte de la commande.|  
|[CreateCommand](../../data/oledb/ccommand-createcommand.md)|Crée une nouvelle commande.|  
|[GetParameterInfo](../../data/oledb/ccommand-getparameterinfo.md)|Obtient une liste des paramètres de commande, leurs noms, et leurs types.|  
|[Préparer](../../data/oledb/ccommand-prepare.md)|Valide et optimise la commande actuelle.|  
|[ReleaseCommand](../../data/oledb/ccommand-releasecommand.md)|Libère l'accesseur de paramètre si nécessaire, puis libère la commande.|  
|[SetParameterInfo](../../data/oledb/ccommand-setparameterinfo.md)|Spécifie le type natif de chaque paramètre de commande.|  
|[Unprepare](../../data/oledb/ccommand-unprepare.md)|Ignore le plan d'exécution actuel de la commande.|  
  
## Notes  
 Utilisez cette classe lorsque vous devez effectuer une opération basée sur un paramètre ou exécuter une commande.  Si vous devez simplement ouvrir un ensemble de lignes simple, utilisez [CTable](../../data/oledb/ctable-class.md) à la place.  
  
 La classe d'accesseur utilisée détermine la méthode de liaison des paramètres et des données.  
  
 Remarque que vous ne pouvez pas utiliser les procédures stockées avec le Fournisseur OLE DB pour Jet car ce fournisseur ne prend pas en charge les procédures stockées \(seules des constantes sont admises dans les chaînes de requêtes\).  
  
## Configuration requise  
 **En\-tête :** : atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)