---
title: "&lt;future&gt; | Microsoft Docs"
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
  - "<future>"
dev_langs: 
  - "C++"
ms.assetid: 2f5830fc-455d-44f9-9e3d-94ea051596a2
caps.latest.revision: 23
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;future&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Incluez l'entête standard \<future\> pour définir des classes de modèle et les modèles de prise en charge qui simplifient l'exécution d'une fonction \- possible dans un thread séparé \- et l'extraction de son résultat.  Le résultat est soit la valeur retournée par la fonction ou une exception qui est émise par la fonction mais n'est pas interceptée dans la fonction.  
  
 Cet en\-tête utilise le runtime d'accès concurrentiel \(ConcRT\) pour pouvoir l'utiliser avec d'autres mécanismes de ConcRT.  Pour plus d'informations sur ConcRT, consultez [Concurrency Runtime](../parallel/concrt/concurrency-runtime.md).  
  
## Syntaxe  
  
```cpp  
#include <future>  
```  
  
## Notes  
  
> [!NOTE]
>  Dans le code compilé à l'aide de **\/clr** ou de **\/clr:pure**, cet en\-tête est bloqué.  
  
 Un *fournisseur asynchrone* stocke le résultat d'un appel de fonction.  Un *Objet de retour asynchrone* est utilisé pour récupérer le résultat d'un appel de fonction.  Un *état asynchrone associé* fournit la communication entre un fournisseur asynchrone et un ou plusieurs objets de retour asynchrones.  
  
 Un programme ne crée directement aucun objet d'état asynchrone associé.  Le programme crée un fournisseur asynchrone chaque fois qu'il en a besoin et crée un objet de retour asynchrone qui partage son état asynchrone associé au fournisseur.  Les fournisseurs asynchrones et les retours des objets asynchrones gèrent les objets qui conservent leur état asynchrone associé partagé.  Lorsque le dernier objet qui référence l'état asynchrone associé le libère, l'objet qui conserve l'état asynchrone associé est détruit.  
  
 Un fournisseur asynchrone ou un objet de retour asynchrone sans état asynchrone associé est *vide*.  
  
 Un état asynchrone associé est *prêt* uniquement si son fournisseur asynchrone a stocké une valeur de retour ou une exception.  
  
 La fonction de modèle `async` et les classes de modèles `promise` et `packaged_task` sont les fournisseurs asynchrones.  Les classes de modèle `future` et `shared_future` décrivent les objets de retour asynchrones.  
  
 Chacune des classes de modèle `promise`, `future`, et `shared_future` a une spécialisation du type `void` et une spécialisation partielle pour stocker et récupérer une valeur par référence.  Ces spécialisations diffèrent du modèle principal uniquement dans les signatures et la sémantique des fonctions qui enregistrent et récupèrent la valeur retournée.  
  
 Les classes de modèle `future` et `shared_future` ne se bloquent jamais dans leurs destructeurs, sauf dans un cas qui est conservé pour la compatibilité descendante : Contrairement à tous les autres tâches futures, car d'`future`\(ou dernier `shared_future`— ceci est attaché à une tâche qui commence avec `std::async`, les blocs de destructeur si la tâche ne s'est pas terminée ; autrement dit, il bloque si ce thread n'a pas encore `.get()` ou `.wait()` et la tâche s'exécute toujours.  Remarque suivante d'utilisation a été ajoutée à la description d'`std::async` dans le projet de norme : « \[Remarque : Si un futur obtenu à partir du std::async est déplacé à l'extérieur de la portée locale, un code qui utilise l'avenir doit savoir que le futur du destructeur peut bloquer pour que l'état partagé soit prêt. Autrement terminent la remarque\] » Dans tous les autres cas, l'`future` et les destructeurs d'`shared_future` doivent et sont garantis pour ne jamais bloquer.  
  
## Membres  
  
### Classes  
  
|Nom|Description|  
|---------|-----------------|  
|[future, classe](../standard-library/future-class.md)|Décrit un objet de retour asynchrone.|  
|[future\_error, classe](../standard-library/future-error-class.md)|Décrit un objet exception pouvant être levé par des méthodes de types qui gèrent les objets `future`.|  
|[packaged\_task, classe](../standard-library/packaged-task-class.md)|Décrit un fournisseur asynchrone qui est un wrapper d'appel et dont la signature d'appel est `Ty(ArgTypes...)`.  Son état asynchrone associé contient une copie de l'objet appelé en plus du résultat potentiel.|  
|[promise, classe](../standard-library/promise-class.md)|Décrit un fournisseur asynchrone.|  
|[shared\_future, classe](../standard-library/shared-future-class.md)|Décrit un objet de retour asynchrone.  Contrairement à un objet `future`, un fournisseur asynchrone peut être associé à plusieurs objets `shared_future`.|  
  
### Structures  
  
|Nom|Description|  
|---------|-----------------|  
|[is\_error\_code\_enum, structure](../standard-library/is-error-code-enum-structure.md)|La spécialisation qui pointe vers cet `future_errc` convient pour stocker `error_code`.|  
|[uses\_allocator, structure](../standard-library/uses-allocator-structure.md)|Spécialisation qui est toujours vrai.|  
  
### Fonctions  
  
|Nom|Description|  
|---------|-----------------|  
|[async, fonction](../Topic/async%20Function.md)|Représente un fournisseur asynchrone.|  
|[future\_category, fonction](../Topic/future_category%20Function.md)|Retourne une référence à l'objet `error_category` qui caractérise les erreurs associées aux objets `future`.|  
|[make\_error\_code, fonction](../Topic/make_error_code%20Function.md)|Crée un `error_code` qui a l'objet `error_category` qui caractérise des erreurs d'`future`.|  
|[make\_error\_condition, fonction](../Topic/make_error_condition%20Function.md)|Crée un `error_condition` qui a l'objet `error_category` qui caractérise des erreurs d'`future`.|  
|[Fonction swap \(\<future\>\)](../Topic/swap%20Function%20\(%3Cfuture%3E\).md)|Échange l'état asynchrone associé d'un objet `promise` et celui des autres.|  
  
### Énumérations  
  
|Nom|Description|  
|---------|-----------------|  
|[future\_errc, énumération](../Topic/future_errc%20Enumeration.md)|Fournit des noms symboliques pour les erreurs signalées via la classe `future_error`.|  
|[future\_status, énumération](../Topic/future_status%20Enumeration.md)|Fournit des noms symboliques pour les raisons qu'une fonction d'attente temporisée peut renvoyer.|  
|[launch, énumération](../Topic/launch%20Enumeration.md)|Représente un type de masque de bits qui décrit les modes possibles pour la fonction de modèle `async`.|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)