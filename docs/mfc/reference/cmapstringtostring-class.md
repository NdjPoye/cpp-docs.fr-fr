---
title: "CMapStringToString Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMapStringToString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMapStringToString class"
  - "classes de collection, string mapping"
  - "chaînes (C++), class for mapping"
  - "chaînes (C++), mapper"
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CMapStringToString Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le préfixe prend en charge des objets d' `CString` indexé par `CString` objets.  
  
## Syntaxe  
  
```  
class CMapStringToString : public CObject  
```  
  
## Membres  
 Les fonctions membres d' `CMapStringToString` sont semblables aux fonctions membres de la classe [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md).  En raison de cette ressemblance, vous pouvez utiliser la documentation de référence des `CMapStringToOb` pour les détails de la fonction membre.  Partout où vous consultez un pointeur d' `CObject` comme paramètre de fonction de valeur de retour ou « exit », remplacez un pointeur vers `char`.  Partout où vous consultez un pointeur d' `CObject` comme paramètre de fonction « entrée », remplacez un pointeur vers `char`.  
  
 `BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`  
  
 par exemple, traduit la valeur  
  
 `BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`  
  
### Structures publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CMapStringToString::CPair](../Topic/CMapStringToString::CPair.md)|Une structure imbriquée qui contient une valeur de clé et la valeur de l'objet String associé.|  
  
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
|[CMapStringToString::PGetFirstAssoc](../Topic/CMapStringToString::PGetFirstAssoc.md)|Obtient un pointeur vers le premier `CString` dans le mappage.|  
|[CMapStringToString::PGetNextAssoc](../Topic/CMapStringToString::PGetNextAssoc.md)|Obtient un pointeur vers l' `CString` pour itérer.|  
|[CMapStringToString::PLookup](../Topic/CMapStringToString::PLookup.md)|Retourne un pointeur vers `CString` dont la valeur correspond à la valeur spécifiée.|  
|[CMapStringToOb::RemoveAll](../Topic/CMapStringToOb::RemoveAll.md)|Supprime tous les éléments de ce mappage.|  
|[CMapStringToOb::RemoveKey](../Topic/CMapStringToOb::RemoveKey.md)|Supprime un élément spécifié par une clé.|  
|[CMapStringToOb::SetAt](../Topic/CMapStringToOb::SetAt.md)|Insère un élément dans le mappage ; remplace un élément existant si une clé correspondante est trouvée.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMapStringToOb::operator](../Topic/CMapStringToOb::operator.md)|Insère un élément dans le mappage de remplacement d'opérateur pour `SetAt`.|  
  
## Notes  
 `CMapStringToString` incorpore la macro d' `IMPLEMENT_SERIAL` pour prendre en charge la sérialisation et faire un dump de ses éléments.  Chaque élément est sérialisé ensuite si une carte est stockée à une archive, avec \(\)**\<\<**l'opérateur surchargé d'insertion ou avec la fonction membre d' `Serialize` .  
  
 Si vous avez besoin d'un dump d' `CString`individuel \- les éléments d'`CString` , vous devez définir la profondeur du contexte de dump à 1 ou supérieur.  
  
 Lorsqu'un objet d' `CMapStringToString` est supprimé, ou lorsque ses éléments sont supprimés, les objets d' `CString` sont supprimés si nécessaire.  
  
 Pour plus d'informations sur `CMapStringToString`, consultez l'article [collections](../../mfc/collections.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToString`  
  
## Configuration requise  
 **Header:** afxcoll.h  
  
## Voir aussi  
 [L'exemple MFC COLLECTENT](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)