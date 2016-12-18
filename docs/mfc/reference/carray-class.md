---
title: "CArray Class | Microsoft Docs"
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
  - "CArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tableaux (C++), classes"
  - "CArray class"
  - "classes de collection, template-based"
  - "modèles, classes de collection"
ms.assetid: fead8b00-4cfd-4625-ad0e-251df62ba92f
caps.latest.revision: 33
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prend en charge les tableaux qui sont comme les tableaux C, mais peut dynamiquement réduire et développer si nécessaire.  
  
## Syntaxe  
  
```  
template < class TYPE, class ARG_TYPE = const TYPE& >   
class CArray :   
   public CObject  
```  
  
#### Paramètres  
 `TYPE`  
 Le paramètre de modèle qui spécifie le type d'objets stocker dans le tableau.  `TYPE` est un paramètre qui est retourné par `CArray`.  
  
 `ARG` *\_* `TYPE`  
 Le paramètre de modèle qui spécifie le type d'argument utilisé pour accéder à des objets stocker dans le tableau.  Souvent une référence à `TYPE`.  `ARG_TYPE` est un paramètre passé à `CArray`.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CArray::CArray](../Topic/CArray::CArray.md)|Construit un tableau vide.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CArray::Add](../Topic/CArray::Add.md)|Ajoute un élément à la fin du tableau ; élève le tableau si nécessaire.|  
|[CArray::Append](../Topic/CArray::Append.md)|Ajoute un autre tableau au tableau ; élève le tableau si nécessaire|  
|[CArray::Copy](../Topic/CArray::Copy.md)|Copie une autre tableau au tableau ; élève le tableau si nécessaire.|  
|[CArray::ElementAt](../Topic/CArray::ElementAt.md)|Retourne une référence temporaire au pointeur d'élément dans le tableau.|  
|[CArray::FreeExtra](../Topic/CArray::FreeExtra.md)|Libère toute la mémoire non utilisée au\-dessus de la limite supérieure actuelle.|  
|[CArray::GetAt](../Topic/CArray::GetAt.md)|Retourne la valeur à un index donné.|  
|[CArray::GetCount](../Topic/CArray::GetCount.md)|Obtient le nombre d'éléments dans ce tableau.|  
|[CArray::GetData](../Topic/CArray::GetData.md)|Permet l'accès aux éléments du tableau.  Peut être **NULL**.|  
|[CArray::GetSize](../Topic/CArray::GetSize.md)|Obtient le nombre d'éléments dans ce tableau.|  
|[CArray::GetUpperBound](../Topic/CArray::GetUpperBound.md)|Retourne le plus grand index valide.|  
|[CArray::InsertAt](../Topic/CArray::InsertAt.md)|Insère un élément \(ou les éléments dans un autre tableau\) à un index spécifié.|  
|[CArray::IsEmpty](../Topic/CArray::IsEmpty.md)|Détermine si le tableau est vide.|  
|[CArray::RemoveAll](../Topic/CArray::RemoveAll.md)|Supprime tous les éléments de ce tableau.|  
|[CArray::RemoveAt](../Topic/CArray::RemoveAt.md)|Supprime un élément à un index spécifique.|  
|[CArray::SetAt](../Topic/CArray::SetAt.md)|Définit la valeur pour un index donné ; tableau non \- autorisée pour développer.|  
|[CArray::SetAtGrow](../Topic/CArray::SetAtGrow.md)|Définit la valeur pour un index donné ; élève le tableau si nécessaire.|  
|[CArray::SetSize](../Topic/CArray::SetSize.md)|Définit le nombre d'éléments à inclure dans ce tableau.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CArray::operator](../Topic/CArray::operator.md)|Définit ou obtient l'élément à l'index spécifié.|  
  
## Notes  
 Les index de tableau commencent toujours à la position 0.  Vous pouvez choisir résoudre la limite supérieure lié ou laissez la matrice de développer lorsque vous ajoutez des éléments au delà de la limite actuelle.  La mémoire est allouée contigu à la limite supérieure, même si certains éléments sont null.  
  
> [!NOTE]
>  La plupart des méthodes qui se redimensionnent un objet d' `CArray` ou ajouter des éléments à l'aide [memcpy\_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) aux éléments de déplacement.  Il s'agit d'un problème car `memcpy_s` n'est pas compatible avec un objet qui nécessitent un constructeur d'être appelé.  Si les éléments dans `CArray` ne sont pas compatibles avec `memcpy_s`, vous devez créer nouvel `CArray` de la taille appropriée.  Vous devez ensuite utiliser [CArray::Copy](../Topic/CArray::Copy.md) et [CArray::SetAt](../Topic/CArray::SetAt.md) pour remplir un nouveau tableau car ces méthodes utilisent un opérateur d'assignation au lieu d' `memcpy_s`.  
  
 Comme avec la matrice c, le temps d'accès d'un élément indexé par `CArray` est constante et est indépendant de la taille du tableau.  
  
> [!TIP]
>  Avant d'utiliser d'un tableau, utilisez [SetSize](../Topic/CArray::SetSize.md) pour générer sa taille et pour allouer de la mémoire pour celui\-ci.  Si vous n'utilisez pas `SetSize`, ajouter des éléments à la matrice la cause d'être souvent réaffectée et copiée.  La réallocation et la copie fréquentes sont inefficaces et peuvent réduire la mémoire en fragments.  
  
 Si vous avez besoin d'un dump des éléments dans un tableau, vous devez définir la profondeur de l'objet de [CDumpContext](../../mfc/reference/cdumpcontext-class.md) à 1 ou supérieur.  
  
 Certaines fonctions membres de cette classe appelle les fonctions d'assistance globales qui doivent être personnalisées pour la plupart des fonctionnalités de la classe d' `CArray` .  Consultez la rubrique [programmes d'assistance de classe de collection](../../mfc/reference/collection-class-helpers.md) dans la section de macro MFC et Globals.  
  
 La dérivation de classe de tableau est semblable à la dérivation de liste.  
  
 Pour plus d'informations sur l'utilisation `CArray`, consultez l'article [collections](../../mfc/collections.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CArray`  
  
## Configuration requise  
 `Header:` afxtempl.h  
  
## Voir aussi  
 [L'exemple MFC COLLECTENT](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CObArray Class](../../mfc/reference/cobarray-class.md)   
 [Programmes d'assistance pour les classes de collection](../../mfc/reference/collection-class-helpers.md)