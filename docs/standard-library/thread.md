---
title: "&lt; thread &gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<thread>"
dev_langs: 
  - "C++"
ms.assetid: 0c858405-4efb-449d-bf76-70d3693c9234
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt; thread &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Inclure l’en-tête standard \< thread> pour définir la classe `thread` et diverses fonctions de prise en charge.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
#include <thread>  
```  
  
## <a name="remarks"></a>Remarques  
  
> [!NOTE]
>  Dans le code compilé à l’aide de **/clr** ou **/clr : pure**, cet en-tête est bloqué.  
  
 Le `__STDCPP_THREADS__` macro est définie comme une valeur différente de zéro pour indiquer que les threads sont pris en charge par cet en-tête.  
  
## <a name="members"></a>Membres  
  
### <a name="public-classes"></a>Classes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[thread (classe)](../standard-library/thread-class.md)|Définit un objet qui sert à observer et à gérer un thread d’exécution dans une application.|  
  
### <a name="public-structures"></a>Structures publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[hash, Structure (STL)](../standard-library/hash-structure-stl.md)|Définit une fonction membre qui retourne une valeur qui est déterminée de manière unique par un `thread::id`. La fonction membre définit un [hachage](hash%20Class.md) (fonction) qui est appropriée pour les valeurs de mappage de type `thread::id` pour une distribution de valeurs d’index.|  
  
### <a name="public-functions"></a>Fonctions publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[get_id, fonction](../Topic/%3Cthread%3E%20functions.md#get_id_function)|Identifie le thread en cours d’exécution.|  
|[sleep_for, fonction](../Topic/%3Cthread%3E%20functions.md#sleep_for_function)|Bloque le thread appelant.|  
|[sleep_until, fonction](../Topic/%3Cthread%3E%20functions.md#sleep_until_function)|Bloque le thread appelant au moins jusqu'à l’heure spécifiée.|  
|[swap, fonction](../Topic/%3Cthread%3E%20functions.md#swap_function)|Échange les États de deux `thread` objets.|  
|[yield, fonction](../Topic/%3Cthread%3E%20functions.md#yield_function)|Indique le système d’exploitation pour exécuter d’autres threads, même si le thread actuel est normalement continuer à s’exécuter.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[opérateur > =, opérateur](../Topic/%3Cthread%3E%20operators.md#operator_gt__eq)|Détermine si un `thread::id` objet est supérieur ou égal à un autre.|  
|[opérateur > (opérateur)](../Topic/%3Cthread%3E%20operators.md#operator_gt_)|Détermine si un `thread::id` objet est supérieur à un autre.|  
|[opérateur < =, opérateur](../Topic/%3Cthread%3E%20operators.md#operator_lt__eq)|Détermine si un `thread::id` objet est inférieur ou égal à un autre.|  
|[opérateur < (opérateur)](../Topic/%3Cthread%3E%20operators.md#operator_lt_)|Détermine si un `thread::id` objet est inférieur à un autre.|  
|[opérateur ! =, opérateur](../Topic/%3Cthread%3E%20operators.md#operator_neq)|Compare deux objets `thread::id` pour déterminer s'ils sont différents.|  
|[opérateur ==, opérateur](../Topic/%3Cthread%3E%20operators.md#operator_eq_eq)|Compare deux objets `thread::id` pour déterminer s’ils sont égaux.|  
|[opérateur << (opérateur)](../Topic/%3Cthread%3E%20operators.md#operator_lt__lt_)|Insère une représentation textuelle d’un `thread::id` un objet en un flux de données.|  
  
## <a name="see-also"></a>Voir aussi  
 [Référence de fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque Standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)

