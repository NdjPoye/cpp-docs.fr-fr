---
title: '&lt;thread&gt; | Documents Microsoft'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <thread>
dev_langs:
- C++
ms.assetid: 0c858405-4efb-449d-bf76-70d3693c9234
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
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 9b32de86d2ec84017157cccf1a05b9e9b6802e47
ms.lasthandoff: 02/24/2017

---
# <a name="ltthreadgt"></a>&lt;thread&gt;
Inclure l’en-tête standard \<thread > pour définir la classe `thread` et diverses fonctions de prise en charge.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
#include <thread>  
```  
  
## <a name="remarks"></a>Remarques  
  
> [!NOTE]
>  Dans le code compilé à l’aide de **/clr**, cet en-tête est bloqué.  
  
 Le `__STDCPP_THREADS__` macro est définie comme une valeur différente de zéro pour indiquer que les threads sont pris en charge par cet en-tête.  
  
## <a name="members"></a>Membres  
  
### <a name="public-classes"></a>Classes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[thread, classe](../standard-library/thread-class.md)|Définit un objet qui sert à observer et à gérer un thread d’exécution dans une application.|  
  
### <a name="public-structures"></a>Structures publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[hash, structure (bibliothèque standard C++)](../standard-library/hash-structure-stl.md)|Définit une fonction membre qui retourne une valeur qui est déterminée de manière unique par un `thread::id`. La fonction membre définit un [hachage](../standard-library/hash-class.md) (fonction) qui est appropriée pour les valeurs de mappage de type `thread::id` pour une distribution de valeurs d’index.|  
  
### <a name="public-functions"></a>Fonctions publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[get_id, fonction](../standard-library/thread-functions.md#get_id_function)|Identifie de façon unique le thread d’exécution en cours.|  
|[sleep_for, fonction](../standard-library/thread-functions.md#sleep_for_function)|Bloque le thread appelant.|  
|[sleep_until, fonction](../standard-library/thread-functions.md#sleep_until_function)|Bloque le thread appelant au moins jusqu’à l’heure spécifiée.|  
|[swap, fonction](../standard-library/thread-functions.md#swap_function)|Échange les États de deux `thread` objets.|  
|[yield, fonction](../standard-library/thread-functions.md#yield_function)|Indique au système d’exploitation d’exécuter d’autres threads, même si le thread actuel continuerait normalement à s’exécuter.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[opérateur > =, opérateur](../standard-library/thread-operators.md#operator_gt__eq)|Détermine si un objet `thread::id` est supérieur ou égal à un autre.|  
|[opérateur > (opérateur)](../standard-library/thread-operators.md#operator_gt_)|Détermine si un objet `thread::id` est supérieur à un autre.|  
|[(opérateur)<=></=>](../standard-library/thread-operators.md#operator_lt__eq)|Détermine si un objet `thread::id` est inférieur ou égal à un autre.|  
|[(opérateur)<>](../standard-library/thread-operators.md#operator_lt_)|Détermine si un objet `thread::id` est inférieur à un autre.|  
|[opérateur ! =, opérateur](../standard-library/thread-operators.md#operator_neq)|Compare deux objets `thread::id` pour déterminer s'ils sont différents.|  
|[opérateur ==, opérateur](../standard-library/thread-operators.md#operator_eq_eq)|Compare deux objets `thread::id` pour déterminer s’ils sont égaux.|  
|[(opérateur)<>](../standard-library/thread-operators.md#operator_lt__lt_)|Insère une représentation textuelle d’un objet `thread::id` dans un flux.|  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)


