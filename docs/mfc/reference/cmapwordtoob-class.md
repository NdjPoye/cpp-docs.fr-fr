---
title: "CMapWordToOb Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMapWordToOb"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "16-bit word mapping"
  - "CMapWordToOb class"
ms.assetid: 9c9bcd76-456f-4cf9-b03c-dd28b49d5e4f
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CMapWordToOb Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mappe prend en charge des pointeurs d' `CObject` indexé par un mot de 16 bits.  
  
## Syntaxe  
  
```  
class CMapWordToOb : public CObject  
```  
  
## Membres  
 Les fonctions membres d' `CMapWordToOb` sont semblables aux fonctions membres de la classe [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md).  En raison de cette ressemblance, vous pouvez utiliser la documentation de référence des `CMapStringToOb` pour les détails de la fonction membre.  Partout où vous consultez `CString` ou un pointeur de **const** à `char` comme paramètre de fonction ou de valeur de retour, **word**de remplacement.  
  
 `BOOL CMapStringToOb::Lookup( const char* <key>,`  
  
 `CObject*& <rValue> ) const;`  
  
 par exemple, traduit la valeur  
  
 `BOOL CMapWordToOb::Lookup( WORD <key>, CObject*& <rValue> ) const;`  
  
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
 `CMapWordToOb` incorpore la macro d' `IMPLEMENT_SERIAL` pour prendre en charge la sérialisation et faire un dump de ses éléments.  Chaque élément est sérialisé ensuite si une carte est stockée à une archive, avec \(\)**\<\<**l'opérateur surchargé d'insertion ou avec la fonction membre d' `Serialize` .  
  
 Si vous avez besoin d'un dump de **word**individuel \- les éléments d'`CObject` , vous devez définir la profondeur du contexte de dump à 1 ou supérieur.  
  
 Lorsqu'un objet d' `CMapWordToOb` est supprimé, ou lorsque ses éléments sont supprimés, les pointeurs d' `CObject` sont supprimés.  Les objets référencés par des pointeurs d' `CObject` ne sont pas détruits.  
  
 Pour plus d'informations sur `CMapWordToOb`, consultez l'article [collections](../../mfc/collections.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapWordToOb`  
  
## Configuration requise  
 **Header:** afxcoll.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)