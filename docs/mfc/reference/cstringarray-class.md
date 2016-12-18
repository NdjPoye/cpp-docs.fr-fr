---
title: "CStringArray Class | Microsoft Docs"
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
  - "CStringArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tableaux (C++), chaînes"
  - "CStringArray class"
  - "string arrays"
  - "chaînes (C++), collections"
ms.assetid: 6c637e06-bba8-4c08-b0fc-cf8cb067ce34
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CStringArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prend en charge les tableaux d'objets [CString](../../atl-mfc-shared/using-cstring.md).  
  
## Syntaxe  
  
```  
class CStringArray : public CObject  
```  
  
## Membres  
 Les fonctions membres de `CStringArray` sont similaires aux fonctions membres de la classe [CObArray](../../mfc/reference/cobarray-class.md).  Ainsi, vous pouvez utiliser la documentation de référence de `CObArray` pour connaître les spécificités des fonctions membres.  Partout où vous voyez un pointeur `CObject` en tant que valeur de retour, remplacez un objet [CString](../../atl-mfc-shared/using-cstring.md) \(pas un pointeur [CString](../../atl-mfc-shared/using-cstring.md)\).  Partout où vous voyez un pointeur `CObject` en tant que paramètre de fonction, remplacez `LPCTSTR`.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 par exemple, se traduit par  
  
 `CString CStringArray::GetAt( int <nIndex> ) const;`  
  
 et  
  
 `void SetAt( int <nIndex>, CObject* <newElement> )`  
  
 se traduit par  
  
 `void SetAt( int <nIndex>, LPCTSTR <newElement> )`  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CObArray::CObArray](../Topic/CObArray::CObArray.md)|Construit un tableau vide.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CObArray::Add](../Topic/CObArray::Add.md)|Ajoute un élément à la fin du tableau ; étend le tableau si nécessaire.|  
|[CObArray::Append](../Topic/CObArray::Append.md)|Ajoute un autre tableau au tableau ; étend le tableau si nécessaire.|  
|[CObArray::Copy](../Topic/CObArray::Copy.md)|Copie un autre tableau dans le tableau ; étend le tableau si nécessaire.|  
|[CObArray::ElementAt](../Topic/CObArray::ElementAt.md)|Retourne une référence temporaire au pointeur d'élément dans le tableau.|  
|[CObArray::FreeExtra](../Topic/CObArray::FreeExtra.md)|Libère toute la mémoire inutilisée au\-dessus de la limite supérieure actuelle.|  
|[CObArray::GetAt](../Topic/CObArray::GetAt.md)|Retourne la valeur à un index donné.|  
|[CObArray::GetCount](../Topic/CObArray::GetCount.md)|Obtient le nombre d'éléments dans ce tableau.|  
|[CObArray::GetData](../Topic/CObArray::GetData.md)|Autorise l'accès aux éléments du tableau.  Peut avoir la valeur **NULL**.|  
|[CObArray::GetSize](../Topic/CObArray::GetSize.md)|Obtient le nombre d'éléments dans ce tableau.|  
|[CObArray::GetUpperBound](../Topic/CObArray::GetUpperBound.md)|Retourne le plus grand index valide.|  
|[CObArray::InsertAt](../Topic/CObArray::InsertAt.md)|Insère un élément \(ou tous les éléments d'un autre tableau\) à un index spécifique.|  
|[CObArray::IsEmpty](../Topic/CObArray::IsEmpty.md)|Détermine si le tableau est vide.|  
|[CObArray::RemoveAll](../Topic/CObArray::RemoveAll.md)|Supprime tous les éléments de ce tableau.|  
|[CObArray::RemoveAt](../Topic/CObArray::RemoveAt.md)|Supprime un élément à un index spécifique.|  
|[CObArray::SetAt](../Topic/CObArray::SetAt.md)|Définit la valeur d'un index donné. Le tableau n'est pas autorisé à s'étendre.|  
|[CObArray::SetAtGrow](../Topic/CObArray::SetAtGrow.md)|Définit la valeur d'un index donné. Le tableau est étendu si nécessaire.|  
|[CObArray::SetSize](../Topic/CObArray::SetSize.md)|Définit le nombre d'éléments que ce tableau doit contenir.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CObArray::operator](../Topic/CObArray::operator.md)|Définit ou obtient l'élément au niveau de l'index spécifié.|  
  
## Notes  
 `CStringArray` incorpore la macro `IMPLEMENT_SERIAL` pour prendre en charge la sérialisation et le vidage de ses éléments.  Si un tableau d'objets `CString` est stocké dans une archive, soit avec un opérateur d'insertion surchargé, soit avec la fonction membre `Serialize`, chaque élément est sérialisé l'un après l'autre.  
  
> [!NOTE]
>  Avant d'utiliser un tableau, utilisez `SetSize` pour définir sa taille et lui allouer la mémoire nécessaire.  Si vous n'utilisez pas `SetSize`, l'ajout d'éléments à votre tableau risque d'entraîner de fréquentes opérations de réallocation et de copie de ce dernier.  Les opérations fréquentes de réallocation et de copie sont inefficaces et peuvent fragmenter la mémoire.  
  
 Si vous avez besoin de vider des éléments de chaîne individuels dans le tableau, vous devez définir la profondeur du contexte de vidage à 1 ou plus.  
  
 Quand un tableau `CString` est supprimé, ou quand ses éléments sont retirés, la mémoire relative aux chaînes est libérée en fonction des besoins.  
  
 Pour plus d'informations sur l'utilisation de `CStringArray`, consultez l'article [Collections](../../mfc/collections.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CStringArray`  
  
## Configuration requise  
 **En\-tête :** afxcoll.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)