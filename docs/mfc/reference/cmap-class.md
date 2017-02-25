---
title: "CMap Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMap class"
  - "classes de collection, dictionary mapping"
  - "dictionary mapping class"
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CMap Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une classe de collection de dictionnaires qui mappe des clés uniques aux valeurs.  
  
## Syntaxe  
  
```  
template< class KEY, class ARG_KEY, class VALUE, class ARG_VALUE >class CMap : public CObject  
```  
  
#### Paramètres  
 `KEY`  
 Classe de l'objet utilisé comme clé dans le mappage.  
  
 `ARG` *\_* `KEY`  
 Type de données utilisé pour les arguments d' `KEY` ; généralement une référence à `KEY`.  
  
 `VALUE`  
 Classe de l'objet stocké dans le mappage.  
  
 `ARG` *\_* `VALUE`  
 Type de données utilisé pour les arguments d' `VALUE` ; généralement une référence à `VALUE`.  
  
## Membres  
  
### Structures publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMap::CPair](../Topic/CMap::CPair.md)|Une structure imbriquée qui contient une valeur de clé et la valeur de l'objet associé.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMap::CMap](../Topic/CMap::CMap.md)|Construit une collection qui mappe les clés en valeurs.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMap::GetCount](../Topic/CMap::GetCount.md)|Retourne le nombre d'éléments dans ce mappage.|  
|[CMap::GetHashTableSize](../Topic/CMap::GetHashTableSize.md)|Retourne le nombre d'éléments dans la table de hachage.|  
|[CMap::GetNextAssoc](../Topic/CMap::GetNextAssoc.md)|Obtient l'élément pour itérer.|  
|[CMap::GetSize](../Topic/CMap::GetSize.md)|Retourne le nombre d'éléments dans ce mappage.|  
|[CMap::GetStartPosition](../Topic/CMap::GetStartPosition.md)|Retourne la position du premier élément.|  
|[CMap::InitHashTable](../Topic/CMap::InitHashTable.md)|Initialise la table de hachage et spécifie sa taille.|  
|[CMap::IsEmpty](../Topic/CMap::IsEmpty.md)|Tests de l'état de vide\- aucun mappage \(éléments\).|  
|[CMap::Lookup](../Topic/CMap::Lookup.md)|Recherche la valeur mappée à une clé donnée.|  
|[CMap::PGetFirstAssoc](../Topic/CMap::PGetFirstAssoc.md)|Retourne un pointeur vers le premier élément.|  
|[CMap::PGetNextAssoc](../Topic/CMap::PGetNextAssoc.md)|Obtient un pointeur vers l'élément pour itérer.|  
|[CMap::PLookup](../Topic/CMap::PLookup.md)|Retourne un pointeur vers une clé dont la valeur correspond à la valeur spécifiée.|  
|[CMap::RemoveAll](../Topic/CMap::RemoveAll.md)|Supprime tous les éléments de ce mappage.|  
|[CMap::RemoveKey](../Topic/CMap::RemoveKey.md)|Supprime un élément spécifié par une clé.|  
|[CMap::SetAt](../Topic/CMap::SetAt.md)|Insère un élément dans le mappage ; remplace un élément existant si une clé correspondante est trouvée.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMap::operator](../Topic/CMap::operator.md)|Insère un élément dans le mappage de remplacement d'opérateur pour `SetAt`.|  
  
## Notes  
 Une fois que vous avez inséré une paire clé\-valeur \(élément\) dans le mappage, vous pouvez récupérer ou supprimer efficacement les paires à l'aide de la clé pour y accéder.  Vous pouvez également itérer au sein de tous les éléments dans le mappage.  
  
 Une variable de type **position** est utilisée pour l'autre accès aux entrées.  Vous pouvez utiliser **position** « vous souvenez » une entrée et pour itérer mappage.  Vous pouvez penser que cette itération est séquentielle par valeur de clé ; il n'est pas.  La séquence d'éléments récupérés est indéterminée.  
  
 Certaines fonctions membres de cette classe appelle les fonctions d'assistance globales qui doivent être personnalisées pour la plupart des fonctionnalités de la classe d' `CMap` .  Consultez [programmes d'assistance de classe de collection](../../mfc/reference/collection-class-helpers.md) dans la section de macros et Globals d' `MFC``Reference`.  
  
 `CMap` remplace [CObject::Serialize](../Topic/CObject::Serialize.md) pour prendre en charge la sérialisation et faire un dump de ses éléments.  Si un mappage est stockée à une archive à l'aide de `Serialize`, chaque élément du tableau est sérialisé après.  L'implémentation par défaut de la fonction d'assistance d' `SerializeElements` fait de bits un écrire.  Pour plus d'informations sur la sérialisation des éléments de collection de pointeur dérivés d' `CObject` ou d'autres types définis par l'utilisateur, consultez [Comment : définir une collection de type sécurisé](../../mfc/how-to-make-a-type-safe-collection.md).  
  
 Si vous avez besoin d'un dump de diagnostic des éléments individuels dans le mappage \(les clés et les valeurs\), vous devez définir la profondeur du contexte de dump à 1 ou supérieur.  
  
 Lorsqu'un objet d' `CMap` est supprimé, ou lorsque ses éléments sont supprimés, les clés et les valeurs les deux sont supprimées.  
  
 La dérivation de classe de mappage est semblable à la dérivation de liste.  Consultez l'article [collections](../../mfc/collections.md) pour une illustration de dériver d'une classe ayant un usage spécial de liste.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMap`  
  
## Configuration requise  
 **Header:** afxtempl.h  
  
## Voir aussi  
 [L'exemple MFC COLLECTENT](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)