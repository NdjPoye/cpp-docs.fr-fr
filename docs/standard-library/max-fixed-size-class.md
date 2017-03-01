---
title: max_fixed_size, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::max_fixed_size
- max_fixed_size
- stdext::max_fixed_size
- stdext.max_fixed_size
dev_langs:
- C++
helpviewer_keywords:
- max_fixed_size class
ms.assetid: 8c8f4588-37e9-4579-8168-ba3553800914
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c1d83d147fc163a8747a68baff16b1fa1401902b
ms.lasthandoff: 02/24/2017

---
# <a name="maxfixedsize-class"></a>max_fixed_size, classe
Décrit un objet de [classe max](../standard-library/allocators-header.md) qui limite un objet [freelist](../standard-library/freelist-class.md) à une longueur maximale fixe.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <std::size_t Max>  
class max_fixed_size
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Max`|Classe maximale qui détermine le nombre maximal d’éléments à stocker dans la `freelist`.|  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[max_fixed_size](#max_fixed_size__max_fixed_size)|Construit un objet de type `max_fixed_size`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[allocated](#max_fixed_size__allocated)|Incrémente le nombre de blocs de mémoire alloués.|  
|[deallocated](#max_fixed_size__deallocated)|Décrémente le nombre de blocs de mémoire alloués.|  
|[full](#max_fixed_size__full)|Retourne une valeur qui indique si davantage de blocs de mémoire doivent être ajoutés à la liste libre.|  
|[released](#max_fixed_size__released)|Décrémente le nombre de blocs de mémoire dans la liste libre.|  
|[saved](#max_fixed_size__saved)|Incrémente le nombre de blocs de mémoire dans la liste libre.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<allocators>  
  
 **Espace de noms :** stdext  
  
##  <a name="a-namemaxfixedsizeallocateda--maxfixedsizeallocated"></a><a name="max_fixed_size__allocated"></a>  max_fixed_size::allocated  
 Incrémente le nombre de blocs de mémoire alloués.  
  
```
void allocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`_Nx`|Valeur d’incrément.|  
  
### <a name="remarks"></a>Notes  
 La fonction membre ne fait rien. Cette fonction membre est appelée après chaque appel réussi par `cache_freelist::allocate` à l’opérateur `new`. L’argument `_Nx` est le nombre de blocs de mémoire dans le bloc alloués par l’opérateur `new`.  
  
##  <a name="a-namemaxfixedsizedeallocateda--maxfixedsizedeallocated"></a><a name="max_fixed_size__deallocated"></a>  max_fixed_size::deallocated  
 Décrémente le nombre de blocs de mémoire alloués.  
  
```
void deallocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`_Nx`|Valeur d’incrément.|  
  
### <a name="remarks"></a>Notes  
 La fonction membre ne fait rien. Cette fonction membre est appelée après chaque appel par `cache_freelist::deallocate` à l’opérateur `delete`. L’argument `_Nx` est le nombre de blocs de mémoire dans le bloc libérés par l’opérateur `delete`.  
  
##  <a name="a-namemaxfixedsizefulla--maxfixedsizefull"></a><a name="max_fixed_size__full"></a>  max_fixed_size::full  
 Retourne une valeur qui indique si davantage de blocs de mémoire doivent être ajoutés à la liste libre.  
  
```
bool full();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si `Max <= _Nblocks` ; sinon, `false`.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre est appelée par `cache_freelist::deallocate`. Si l’appel retourne `true`, `deallocate` place le bloc de mémoire dans la liste libre ; s’il retourne false, `deallocate` appelle l’opérateur `delete` pour libérer le bloc.  
  
##  <a name="a-namemaxfixedsizemaxfixedsizea--maxfixedsizemaxfixedsize"></a><a name="max_fixed_size__max_fixed_size"></a>  max_fixed_size::max_fixed_size  
 Construit un objet de type `max_fixed_size`.  
  
```
max_fixed_size();
```  
  
### <a name="remarks"></a>Notes  
 Ce constructeur initialise la valeur stockée `_Nblocks` à zéro.  
  
##  <a name="a-namemaxfixedsizereleaseda--maxfixedsizereleased"></a><a name="max_fixed_size__released"></a>  max_fixed_size::released  
 Décrémente le nombre de blocs de mémoire dans la liste libre.  
  
```
void released();
```  
  
### <a name="remarks"></a>Notes  
 Décrémente la valeur stockée `_Nblocks`. La fonction membre `released` de la [classe max](../standard-library/allocators-header.md) actuelle est appelée par `cache_freelist::allocate` chaque fois qu’elle supprime un bloc de mémoire de la liste libre.  
  
##  <a name="a-namemaxfixedsizesaveda--maxfixedsizesaved"></a><a name="max_fixed_size__saved"></a>  max_fixed_size::saved  
 Incrémente le nombre de blocs de mémoire dans la liste libre.  
  
```
void saved();
```  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre incrémente la valeur stockée `_Nblocks`. Cette fonction membre est appelée par `cache_freelist::deallocate` chaque fois qu’elle place un bloc de mémoire dans la liste libre.  
  
## <a name="see-also"></a>Voir aussi  
 [\<allocators>](../standard-library/allocators-header.md)




