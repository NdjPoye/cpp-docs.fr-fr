---
title: "CUIntArray Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CUIntArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tableaux (C++), indexées"
  - "CUIntArray class"
  - "indexed arrays"
  - "INT"
  - "UINT"
  - "WORD data type"
ms.assetid: d71f3d8f-ef9f-4e48-9b69-7782c0e2ddf7
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CUIntArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prend en charge les tableau d'entiers non signés.  
  
## Syntaxe  
  
```  
class CUIntArray : public CObject  
```  
  
## Membres  
 Les fonctions membres d' `CUIntArray` sont semblables aux fonctions membres de la classe [CObArray](../../mfc/reference/cobarray-class.md).  En raison de cette ressemblance, vous pouvez utiliser la documentation de référence des `CObArray` pour les détails de la fonction membre.  Partout où vous consultez un pointeur d' `CObject` comme paramètre de fonction ou de valeur de retour, substituez **uint**.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 par exemple, traduit la valeur  
  
 `UINT CUIntArray::GetAt( int <nIndex> ) const;`  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CObArray::CObArray](../Topic/CObArray::CObArray.md)|Construit un tableau vide.|  
  
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
 Entier non signé, ou **uint**, diffère des mots et des mots doubles car la taille physique de **uint** peut varier selon l'environnement opérationnel cible.  **uint** Est la même taille qu'un mot double.  
  
 `CUIntArray` incorpore la macro d' [IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md) pour prendre en charge l'accès de type au moment de l'exécution et faire un dump à [CDumpContext](../../mfc/reference/cdumpcontext-class.md) un objet.  Si vous avez besoin d'un dump des éléments d'entier non signé, vous devez définir la profondeur du contexte de dump à 1 ou supérieur.  Les tableaux d'entiers non signés ne peuvent pas être sérialisées.  
  
> [!NOTE]
>  Avant d'utiliser d'un tableau, utilisez `SetSize` pour générer sa taille et pour allouer de la mémoire pour celui\-ci.  Si vous n'utilisez pas `SetSize`, ajouter des éléments à la matrice la cause d'être souvent réaffectée et copiée.  La réallocation et la copie fréquentes sont inefficaces et peuvent réduire la mémoire en fragments.  
  
 Pour plus d'informations sur l'utilisation `CUIntArray`, consultez l'article [collections](../../mfc/collections.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CUIntArray`  
  
## Configuration requise  
 **Header:** afxcoll.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)