---
title: "CMapStringToPtr Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMapStringToPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMapStringToPtr class"
  - "classes de collection, string mapping"
  - "chaînes (C++), class for mapping"
ms.assetid: 1ac11143-eb0a-4511-a662-2df0d1d9005b
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMapStringToPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le préfixe prend en charge des pointeurs indexés void par `CString` objets.  
  
## Syntaxe  
  
```  
class CMapStringToPtr : public CObject  
```  
  
## Membres  
 Les fonctions membres d' `CMapStringToPtr` sont semblables aux fonctions membres de la classe [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md).  En raison de cette ressemblance, vous pouvez utiliser la documentation de référence des `CMapStringToOb` pour les détails de la fonction membre.  Partout où vous consultez un pointeur d' `CObject` comme paramètre de fonction ou de valeur de retour, remplacez un pointeur vers `void`.  
  
 `BOOL CMapStringToOb::Lookup( const char* <key>,`  
  
 `CObject*& <rValue> ) const;`  
  
 par exemple, traduit la valeur  
  
 `BOOL CMapStringToPtr::Lookup( LPCTSTR <key>, void*& <rValue> )`  
  
 `const;`  
  
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
 `CMapStringToPtr` incorpore la macro d' `IMPLEMENT_DYNAMIC` pour prendre en charge l'accès de type au moment de l'exécution et faire un dump à `CDumpContext` un objet.  Si vous avez besoin d'un dump des éléments de table, vous devez définir la profondeur du contexte de dump à 1 ou supérieur.  
  
 Les mappages de chaîne en pointeur ne peuvent être sérialisées.  
  
 Lorsqu'un objet d' `CMapStringToPtr` est supprimé, ou lorsque ses éléments sont supprimés, la clé d' `CString` objets et les mots sont supprimés.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToPtr`  
  
## Configuration requise  
 **Header:** afxcoll.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)