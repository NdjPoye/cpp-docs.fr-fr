---
title: freelist, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::freelist
- allocators/stdext::freelist::pop
- allocators/stdext::freelist::push
dev_langs:
- C++
helpviewer_keywords:
- stdext::freelist
- stdext::freelist [C++], pop
- stdext::freelist [C++], push
ms.assetid: 8ad7e35c-4c80-4479-8ede-1a2497b06d71
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: 7e4e636045d91cfaa4bc9532344cf73e68cec911
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="freelist-class"></a>freelist, classe
Gère une liste de blocs de mémoire.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <std::size_t Sz, class Max>  
class freelist
 : public Max
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Sz`|Nombre d’éléments du tableau à allouer.|  
|`Max`|Classe max représentant le nombre maximal d’éléments à stocker dans la liste de libération. La classe max peut être [max_none](../standard-library/max-none-class.md), [max_unbounded](../standard-library/max-unbounded-class.md), [max_fixed_size](../standard-library/max-fixed-size-class.md) ou[max_variable_size](../standard-library/max-variable-size-class.md).|  
  
## <a name="remarks"></a>Notes  
 Cette classe de modèle gère une liste de blocs de mémoire de taille `Sz` avec la longueur maximale de la liste déterminée par la classe max passée dans `Max`.  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[freelist](#freelist)|Construit un objet de type `freelist`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[pop](#pop)|Supprime le premier bloc de mémoire de la liste de libération.|  
|[push](#push)|Ajoute un bloc de mémoire à la liste.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<allocators>  
  
 **Espace de noms :** stdext  
  
##  <a name="freelist"></a>  freelist::freelist  
 Construit un objet de type `freelist`.  
  
```
freelist();
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="pop"></a>  freelist::pop  
 Supprime le premier bloc de mémoire de la liste de libération.  
  
```
void *pop();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers le bloc de mémoire supprimé de la liste.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne `NULL` si la liste est vide. Sinon, elle supprime le premier bloc de mémoire de la liste.  
  
##  <a name="push"></a>  freelist::push  
 Ajoute un bloc de mémoire à la liste.  
  
```
bool push(void* ptr);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`ptr`|Pointeur vers le bloc de mémoire à ajouter à la liste de libération.|  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la fonction `full` de la classe max retourne `false` ; sinon, la fonction `push` retourne `false`.  
  
### <a name="remarks"></a>Notes  
 Si la fonction `full` de la classe max retourne `false`, cette fonction membre ajoute le bloc de mémoire désigné par `ptr` au début de la liste.  
  
## <a name="see-also"></a>Voir aussi  
 [\<allocators>](../standard-library/allocators-header.md)




