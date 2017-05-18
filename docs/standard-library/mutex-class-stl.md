---
title: "mutex, classe (Bibliothèque standard C++)| Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::mutex
- mutex/std::mutex::mutex
- mutex/std::mutex::lock
- mutex/std::mutex::native_handle
- mutex/std::mutex::try_lock
- mutex/std::mutex::unlock
dev_langs:
- C++
ms.assetid: 7999d055-f74f-4303-810f-8d3c9cde2f69
caps.latest.revision: 11
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: e08c7c13d1e182bc3299f11769eddb699b03ab3f
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="mutex-class-c-standard-library"></a>mutex, classe (Bibliothèque standard C++)
Représente un *type mutex*. Vous pouvez utiliser des objets de ce type pour appliquer une exclusion mutuelle dans un programme.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class mutex;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[mutex](#mutex)|Construit un objet `mutex`.|  
|[mutex::~mutex, destructeur](#dtormutex_destructor)|Libère toutes les ressources qui étaient utilisées par l’objet `mutex`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[lock](#lock)|Bloque le thread appelant jusqu'à ce que le thread obtienne la propriété du `mutex`.|  
|[native_handle](#native_handle)|Retourne le type propre à l’implémentation qui représente le descripteur de mutex.|  
|[try_lock](#try_lock)|Tente d'obtenir la propriété de la référence `mutex` sans se bloquer.|  
|[unlock](#unlock)|Libère la propriété du `mutex`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<mutex >  
  
 **Espace de noms :** std  
  
##  <a name="lock"></a>mutex::lock
 Bloque le thread appelant jusqu'à ce que le thread obtienne la propriété du `mutex`.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>Remarques  
 Si le thread appelant possède déjà `mutex`, le comportement est indéfini.  
  
##  <a name="mutex"></a>  mutex::mutex, constructeur  
 Construit un objet `mutex` qui n’est pas verrouillé.  
  
```cpp  
constexpr mutex() noexcept;
```  
  
##  <a name="dtormutex_destructor"></a>  mutex::~mutex, destructeur  
 Libère les ressources utilisées par l’objet `mutex`.  
  
```cpp  
~mutex();
```  
  
### <a name="remarks"></a>Notes  
 Si l'objet est verrouillé lorsque le destructeur s'exécute, le comportement est indéfini.  
  
##  <a name="native_handle"></a>mutex::native_handle
 Retourne le type propre à l’implémentation qui représente le descripteur de mutex. Vous pouvez utiliser le descripteur de plusieurs manières propres à l’implémentation.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `native_handle_type` est défini comme un `Concurrency::critical_section *` converti en `void *`.  
  
##  <a name="try_lock"></a>mutex::try_lock
 Tente d'obtenir la propriété de la référence `mutex` sans se bloquer.  
  
```cpp  
bool try_lock();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la méthode obtient correctement la propriété du `mutex` ; sinon, `false`.  
  
### <a name="remarks"></a>Remarques  
 Si le thread appelant possède déjà `mutex`, le comportement est indéfini.  
  
##  <a name="unlock"></a>mutex::Unlock
 Libère la propriété du `mutex`.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>Remarques  
 Si le thread appelant ne possède pas `mutex`, le comportement est indéfini.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




