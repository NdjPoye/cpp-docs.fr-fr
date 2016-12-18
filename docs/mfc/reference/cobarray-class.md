---
title: "CObArray Class | Microsoft Docs"
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
  - "CObArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tableaux (C++), de type Object"
  - "tableaux (C++), pointeurs"
  - "CObArray class"
  - "tableaux d'objets, CObArray class"
ms.assetid: 27894efd-2370-4776-9ed9-24a98492af17
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CObArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prend en charge les tableaux de pointeurs d' `CObject` .  
  
## Syntaxe  
  
```  
class CObArray : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CObArray::CObArray](../Topic/CObArray::CObArray.md)|Construit un tableau vide pour les pointeurs d' `CObject` .|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CObArray::Add](../Topic/CObArray::Add.md)|Ajoute un élément à la fin du tableau ; élève le tableau si nécessaire.|  
|[CObArray::Append](../Topic/CObArray::Append.md)|Ajoute un autre tableau au tableau ; élève le tableau si nécessaire.|  
|[CObArray::Copy](../Topic/CObArray::Copy.md)|Copie une autre tableau au tableau ; élève le tableau si nécessaire.|  
|[CObArray::ElementAt](../Topic/CObArray::ElementAt.md)|Retourne une référence temporaire au pointeur d'élément dans le tableau.|  
|[CObArray::FreeExtra](../Topic/CObArray::FreeExtra.md)|Libère toute la mémoire non utilisée au\-dessus de la limite supérieure actuelle.|  
|[CObArray::GetAt](../Topic/CObArray::GetAt.md)|Retourne la valeur à un index donné.|  
|[CObArray::GetCount](../Topic/CObArray::GetCount.md)|Obtient le nombre d'éléments dans ce tableau.|  
|[CObArray::GetData](../Topic/CObArray::GetData.md)|Permet l'accès aux éléments du tableau.  Peut être **NULL**.|  
|[CObArray::GetSize](../Topic/CObArray::GetSize.md)|Obtient le nombre d'éléments dans ce tableau.|  
|[CObArray::GetUpperBound](../Topic/CObArray::GetUpperBound.md)|Retourne le plus grand index valide.|  
|[CObArray::InsertAt](../Topic/CObArray::InsertAt.md)|Insère un élément \(ou les éléments dans un autre tableau\) à un index spécifié.|  
|[CObArray::IsEmpty](../Topic/CObArray::IsEmpty.md)|Détermine si le tableau est vide.|  
|[CObArray::RemoveAll](../Topic/CObArray::RemoveAll.md)|Supprime tous les éléments de ce tableau.|  
|[CObArray::RemoveAt](../Topic/CObArray::RemoveAt.md)|Supprime un élément à un index spécifique.|  
|[CObArray::SetAt](../Topic/CObArray::SetAt.md)|Définit la valeur pour un index donné ; tableau non \- autorisée pour développer.|  
|[CObArray::SetAtGrow](../Topic/CObArray::SetAtGrow.md)|Définit la valeur pour un index donné ; élève le tableau si nécessaire.|  
|[CObArray::SetSize](../Topic/CObArray::SetSize.md)|Définit le nombre d'éléments à inclure dans ce tableau.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CObArray::operator](../Topic/CObArray::operator.md)|Définit ou obtient l'élément à l'index spécifié.|  
  
## Notes  
 Ces tableaux d'objets sont similaires aux tableaux C, mais ils peuvent dynamiquement réduire et développer si nécessaire.  
  
 Les index de tableau commencent toujours à la position 0.  Vous pouvez choisir résoudre la limite supérieure lié ou laissez la matrice pour développer lorsque vous ajoutez des éléments au delà de la limite actuelle.  La mémoire est allouée contigu à la limite supérieure, même si certains éléments sont null.  
  
 Sous Win32, la taille d'un objet d' `CObArray` est limitée uniquement à la mémoire.  
  
 Comme avec la matrice c, le temps d'accès d'un élément indexé par `CObArray` est constante et est indépendant de la taille du tableau.  
  
 `CObArray` incorpore la macro d' `IMPLEMENT_SERIAL` pour prendre en charge la sérialisation et faire un dump de ses éléments.  Si un tableau de pointeurs d' `CObject` est stockée à une archive, avec l'opérateur surchargé d'insertion ou avec la fonction membre d' `Serialize` , chaque élément d' `CObject` est ensuite sérialisé avec son index de tableau.  
  
 Si vous avez besoin d'un dump des éléments d' `CObject` dans un tableau, vous devez définir la profondeur de l'objet d' `CDumpContext` à 1 ou supérieur.  
  
 Lorsqu'un objet d' `CObArray` est supprimé, ou lorsque ses éléments sont supprimés, seuls les pointeurs d' `CObject` sont supprimés, pas les objets qu'ils référencent.  
  
> [!NOTE]
>  Avant d'utiliser d'un tableau, utilisez `SetSize` pour générer sa taille et pour allouer de la mémoire pour celui\-ci.  Si vous n'utilisez pas `SetSize`, ajouter des éléments à la matrice la cause d'être souvent réaffectée et copiée.  La réallocation et la copie fréquentes sont inefficaces et peuvent réduire la mémoire en fragments.  
  
 La dérivation de classe de tableau est semblable à la dérivation de liste.  Pour plus d'informations sur la dérivation d'une classe ayant un usage spécial de liste, consultez l'article [collections](../../mfc/collections.md).  
  
> [!NOTE]
>  Vous devez utiliser la macro d' `IMPLEMENT_SERIAL` dans l'implémentation de votre classe dérivée si vous avez l'intention de sérialiser le tableau.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CObArray`  
  
## Configuration requise  
 **Header:** afxcoll.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CStringArray Class](../../mfc/reference/cstringarray-class.md)   
 [CPtrArray Class](../../mfc/reference/cptrarray-class.md)   
 [CByteArray Class](../../mfc/reference/cbytearray-class.md)   
 [CWordArray Class](../../mfc/reference/cwordarray-class.md)   
 [CDWordArray Class](../../mfc/reference/cdwordarray-class.md)