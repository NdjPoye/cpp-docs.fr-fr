---
title: "&lt;variable_condition&gt; | Microsoft Docs"
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
  - "<condition_variable>"
dev_langs: 
  - "C++"
ms.assetid: 8567f7cc-20bd-42a7-9137-87c46f878009
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;variable_condition&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit les classes [condition\_variable](../standard-library/condition-variable-class.md) et [condition\_variable\_any](../standard-library/condition-variable-any-class.md) utilisées pour créer des objets qui attendent une condition pour être réunies.  
  
 Cet en\-tête utilise le runtime d'accès concurrentiel \(ConcRT\) pour pouvoir l'utiliser avec d'autres mécanismes de ConcRT.  Pour plus d'informations sur ConcRT, consultez [Concurrency Runtime](../parallel/concrt/concurrency-runtime.md).  
  
## Syntaxe  
  
```cpp  
#include <condition_variable>  
```  
  
> [!NOTE]
>  Dans le code compilé à l'aide de **\/clr** ou de **\/clr:pure**, cet en\-tête est bloqué.  
  
### Remarques  
 Le code qui les attentes une variable de condition doivent également utiliser `mutex`.  Un thread appelant doit verrouillage `mutex` avant d'appeler des fonctions qui attendent la variable de condition.  `mutex` est ensuite verrouillé lorsque la fonction appelée retourne.  `mutex` n'est pas verrouillée pendant que le thread attend la condition pour devenir la valeur true.  Afin qu'il n'existe aucun résultat imprévisible, chaque thread que les attentes une variable de condition doivent utiliser le même objet d'`mutex`.  
  
 Les objets de type `condition_variable_any` peuvent être utilisés avec un exclusion mutuelle de n'importe quel type.  Le mutex utilisé ne doit pas fournir la méthode d'`try_lock`.  Les objets de type `condition_variable` peuvent être utilisés avec un exclusion mutuelle de type `unique_lock<mutex>`.  Les objets de ce type peuvent être plus rapides que les objets de type `condition_variable_any<unique_lock<mutex>>`.  
  
 Pour attendre un événement, verrouillez d'abord le mutex, puis appelez ensuite une des méthodes de `wait` dans la variable de condition.  L'appel de `wait` bloque jusqu'à un autre thread signaux de la variable de condition.  
  
 *Les fausses commandes* se produisent lorsque le thread qui attendent des variables de condition sont débloqués sans notifications appropriées.  Pour identifier de ces commandes false, le code qui attend une condition à true doit être explicitement activer cette condition lorsque retourne le code d'une attente s'exécutent.  Ceci est généralement réalisée à l'aide d'une boucle ; vous pouvez utiliser `wait(unique_lock<mutex>& lock, Predicate pred)` pour effectuer cette boucle pour vous.  
  
```cpp  
while (condition is false)  
    wait for condition variable;  
```  
  
 `condition_variable_any` et `condition_variable` classe et a trois méthodes qui attendent une condition.  
  
-   `wait` attend une durée illimitée.  
  
-   attente d'`wait_until` jusqu'à `time`spécifié.  
  
-   `wait_for` attend `time interval`spécifié.  
  
 Chacune de ces méthodes deux versions surchargées.  Il attend que et peut se réactiver faussement.  L'autre accepte un argument supplémentaire TEMPLATE qui définit un attribut.  La méthode n'est pas retourné tant que l'attribut soit `true`.  
  
 Chaque classe a également deux méthodes utilisées pour indiquer une variable de condition que son état est `true`.  
  
-   `notify_one` réveille un thread qui attend la variable de condition.  
  
-   `notify_all` réveille tous les threads en attente de la variable de condition.  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [condition\_variable, classe](../standard-library/condition-variable-class.md)   
 [condition\_variable\_any, classe](../standard-library/condition-variable-any-class.md)   
 [cv\_status, énumération](../Topic/cv_status%20Enumeration.md)