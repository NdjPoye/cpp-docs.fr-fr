---
title: max_unbounded, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::max_unbounded
- allocators/stdext::max_unbounded::allocated
- allocators/stdext::max_unbounded::deallocated
- allocators/stdext::max_unbounded::full
- allocators/stdext::max_unbounded::released
- allocators/stdext::max_unbounded::saved
dev_langs: C++
helpviewer_keywords:
- stdext::max_unbounded
- stdext::max_unbounded [C++], allocated
- stdext::max_unbounded [C++], deallocated
- stdext::max_unbounded [C++], full
- stdext::max_unbounded [C++], released
- stdext::max_unbounded [C++], saved
ms.assetid: e34627a9-c231-4031-a483-cbb0514fff46
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8518fbbb25eadb00a6cce68d687046ce8e344fed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="maxunbounded-class"></a>max_unbounded, classe
Décrit un objet de [classe max](../standard-library/allocators-header.md) qui ne limite pas la longueur maximale d’un objet [freelist](../standard-library/freelist-class.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```
class max_unbounded
```  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[allocated](#allocated)|Incrémente le nombre de blocs de mémoire alloués.|  
|[deallocated](#deallocated)|Décrémente le nombre de blocs de mémoire alloués.|  
|[full](#full)|Retourne une valeur qui indique si davantage de blocs de mémoire doivent être ajoutés à la liste libre.|  
|[released](#released)|Décrémente le nombre de blocs de mémoire dans la liste libre.|  
|[saved](#saved)|Incrémente le nombre de blocs de mémoire dans la liste libre.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<allocators>  
  
 **Espace de noms :** stdext  
  
##  <a name="allocated"></a>  max_unbounded::allocated  
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
  
##  <a name="deallocated"></a>  max_unbounded::deallocated  
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
  
##  <a name="full"></a>  max_unbounded::full  
 Retourne une valeur qui indique si davantage de blocs de mémoire doivent être ajoutés à la liste libre.  
  
```
bool full();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La fonction membre retourne toujours `false`.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre est appelée par `cache_freelist::deallocate`. Si l’appel retourne `true`, `deallocate` place le bloc de mémoire dans la liste libre ; s’il retourne false, `deallocate` appelle l’opérateur `delete` pour libérer le bloc.  
  
##  <a name="released"></a>  max_unbounded::released  
 Décrémente le nombre de blocs de mémoire dans la liste libre.  
  
```
void released();
```  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre ne fait rien. La fonction membre `released` de la classe max actuelle est appelée par `cache_freelist::allocate` chaque fois qu’elle supprime un bloc de mémoire de la liste libre.  
  
##  <a name="saved"></a>  max_unbounded::saved  
 Incrémente le nombre de blocs de mémoire dans la liste libre.  
  
```
void saved();
```  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre ne fait rien. Elle est appelée par `cache_freelist::deallocate` chaque fois qu’elle place un bloc de mémoire dans la liste libre.  
  
## <a name="see-also"></a>Voir aussi  
 [\<allocators>](../standard-library/allocators-header.md)


