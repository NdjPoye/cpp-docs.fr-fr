---
title: max_none, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::max_none
- allocators/stdext::max_none::allocated
- allocators/stdext::max_none::deallocated
- allocators/stdext::max_none::full
- allocators/stdext::max_none::released
- allocators/stdext::max_none::saved
dev_langs: C++
helpviewer_keywords:
- stdext::max_none
- stdext::max_none [C++], allocated
- stdext::max_none [C++], deallocated
- stdext::max_none [C++], full
- stdext::max_none [C++], released
- stdext::max_none [C++], saved
ms.assetid: 12ab5376-412e-479c-86dc-2c3d6a3559b6
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f7db35adf828d66ecf9b6474e45960d22466b444
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="maxnone-class"></a>max_none, classe
Décrit un objet de [classe max](../standard-library/allocators-header.md) qui limite un objet [freelist](../standard-library/freelist-class.md) à une longueur maximale de zéro.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <std::size_t Max>  
class max_none
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`Max`|Classe maximale qui détermine le nombre maximal d’éléments à stocker dans la `freelist`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[allocated](#allocated)|Incrémente le nombre de blocs de mémoire alloués.|  
|[deallocated](#deallocated)|Décrémente le nombre de blocs de mémoire alloués.|  
|[full](#full)|Retourne une valeur qui indique si davantage de blocs de mémoire doivent être ajoutés à la liste libre.|  
|[released](#released)|Décrémente le nombre de blocs de mémoire dans la liste libre.|  
|[saved](#saved)|Incrémente le nombre de blocs de mémoire dans la liste libre.|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<allocators>  
  
 **Espace de noms :** stdext  
  
##  <a name="allocated"></a>  max_none::allocated  
 Incrémente le nombre de blocs de mémoire alloués.  
  
```
void allocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`_Nx`|Valeur d’incrément.|  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre ne fait rien. Elle est appelée après chaque appel réussi par `cache_freelist::allocate` à l’opérateur `new`. L’argument `_Nx` est le nombre de blocs de mémoire dans le bloc alloués par l’opérateur `new`.  
  
##  <a name="deallocated"></a>  max_none::deallocated  
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
  
##  <a name="full"></a>  max_none::full  
 Retourne une valeur qui indique si davantage de blocs de mémoire doivent être ajoutés à la liste libre.  
  
```
bool full();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Cette fonction membre retourne toujours `true`.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre est appelée par `cache_freelist::deallocate`. Si l’appel retourne `true`, `deallocate` place le bloc de mémoire dans la liste libre ; s’il retourne false, `deallocate` appelle l’opérateur `delete` pour libérer le bloc.  
  
##  <a name="released"></a>  max_none::released  
 Décrémente le nombre de blocs de mémoire dans la liste libre.  
  
```
void released();
```  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre ne fait rien. La fonction membre `released` de la classe max actuelle est appelée par `cache_freelist::allocate` chaque fois qu’elle supprime un bloc de mémoire de la liste libre.  
  
##  <a name="saved"></a>  max_none::saved  
 Incrémente le nombre de blocs de mémoire dans la liste libre.  
  
```
void saved();
```  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre ne fait rien. Elle est appelée par `cache_freelist::deallocate` chaque fois qu’elle place un bloc de mémoire dans la liste libre.  
  
## <a name="see-also"></a>Voir aussi  
 [\<allocators>](../standard-library/allocators-header.md)



