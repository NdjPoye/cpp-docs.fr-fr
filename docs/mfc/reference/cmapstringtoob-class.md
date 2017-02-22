---
title: "CMapStringToOb Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMapStringToOb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMapStringToOb class"
  - "classes de collection, string mapping"
  - "chaînes (C++), class for mapping"
ms.assetid: 09653980-b885-4f3a-8594-0aeb7f94c601
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CMapStringToOb Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une classe de collection de dictionnaires qui mappe unique `CString` des objets aux pointeurs d' `CObject` .  
  
## Syntaxe  
  
```  
class CMapStringToOb : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMapStringToOb::CMapStringToOb](../Topic/CMapStringToOb::CMapStringToOb.md)|Constructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMapStringToOb::GetCount](../Topic/CMapStringToOb::GetCount.md)|Retourne le nombre d'éléments dans ce mappage.|  
|[CMapStringToOb::GetHashTableSize](../Topic/CMapStringToOb::GetHashTableSize.md)|Détermine le nombre actuel d'éléments dans la table de hachage.|  
|[CMapStringToOb::GetNextAssoc](../Topic/CMapStringToOb::GetNextAssoc.md)|Obtient l'élément pour itérer.|  
|[CMapStringToOb::GetSize](../Topic/CMapStringToOb::GetSize.md)|Retourne le nombre d'éléments dans ce mappage.|  
|[CMapStringToOb::GetStartPosition](../Topic/CMapStringToOb::GetStartPosition.md)|Retourne la position du premier élément.|  
|[CMapStringToOb::HashKey](../Topic/CMapStringToOb::HashKey.md)|Calcule la valeur de hachage d'une clé spécifiée.|  
|[CMapStringToOb::InitHashTable](../Topic/CMapStringToOb::InitHashTable.md)|Initialise la table de hachage.|  
|[CMapStringToOb::IsEmpty](../Topic/CMapStringToOb::IsEmpty.md)|Tests de l'état de vide\- aucun mappage \(éléments\).|  
|[CMapStringToOb::Lookup](../Topic/CMapStringToOb::Lookup.md)|Recherche un pointeur void sur la clé de pointeur void.  La valeur de pointeur, pas l'entité qu'elle indique, est utilisée pour la comparaison principale.|  
|[CMapStringToOb::LookupKey](../Topic/CMapStringToOb::LookupKey.md)|Retourne une référence à la clé associée à la valeur de clé spécifiée.|  
|[CMapStringToOb::RemoveAll](../Topic/CMapStringToOb::RemoveAll.md)|Supprime tous les éléments de ce mappage.|  
|[CMapStringToOb::RemoveKey](../Topic/CMapStringToOb::RemoveKey.md)|Supprime un élément spécifié par une clé.|  
|[CMapStringToOb::SetAt](../Topic/CMapStringToOb::SetAt.md)|Insère un élément dans le mappage ; remplace un élément existant si une clé correspondante est trouvée.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMapStringToOb::operator](../Topic/CMapStringToOb::operator.md)|Insère un élément dans le mappage de remplacement d'opérateur pour `SetAt`.|  
  
## Notes  
 Une fois que vous avez inséré une paire d' `CString`\- d'`CObject*` \(élément\) dans le mappage, vous pouvez récupérer ou supprimer efficacement les paires à l'aide d'une chaîne ou une valeur d' `CString` comme clé.  Vous pouvez également itérer au sein de tous les éléments dans le mappage.  
  
 Une variable de type **position** est utilisée pour l'autre accès d'entrée dans toutes les variations de mappage.  Vous pouvez utiliser **position** « vous souvenez » une entrée et pour itérer mappage.  Vous pouvez penser que cette itération est séquentielle par valeur de clé ; il n'est pas.  La séquence d'éléments récupérés est indéterminée.  
  
 `CMapStringToOb` incorpore la macro d' `IMPLEMENT_SERIAL` pour prendre en charge la sérialisation et faire un dump de ses éléments.  Chaque élément est sérialisé ensuite si une carte est stockée à une archive, avec \(\)**\<\<**l'opérateur surchargé d'insertion ou avec la fonction membre d' `Serialize` .  
  
 Si vous avez besoin d'un dump de diagnostic des éléments individuels dans le mappage \(la valeur d' `CString` et le contenu d' `CObject` \), vous devez définir la profondeur du contexte de dump à 1 ou supérieur.  
  
 Lorsqu'un objet d' `CMapStringToOb` est supprimé, ou lorsque ses éléments sont supprimés, les objets d' `CString` et les pointeurs d' `CObject` sont supprimés.  Les objets référencés par des pointeurs d' `CObject` ne sont pas détruits.  
  
 La dérivation de classe de mappage est semblable à la dérivation de liste.  Consultez l'article [collections](../../mfc/collections.md) pour une illustration de dériver d'une classe ayant un usage spécial de liste.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToOb`  
  
## Configuration requise  
 **Header:** afxcoll.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr Class](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord Class](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapStringToPtr Class](../../mfc/reference/cmapstringtoptr-class.md)   
 [CMapStringToString Class](../../mfc/reference/cmapstringtostring-class.md)   
 [CMapWordToOb Class](../../mfc/reference/cmapwordtoob-class.md)   
 [CMapWordToPtr Class](../../mfc/reference/cmapwordtoptr-class.md)