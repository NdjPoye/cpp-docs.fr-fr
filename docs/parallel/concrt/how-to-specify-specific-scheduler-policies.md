---
title: "Comment&#160;: sp&#233;cifier des strat&#233;gies de planificateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "spécifier des stratégies de planificateur [Runtime d’accès concurrentiel]"
  - "stratégies de planificateur, spécifier [Runtime d’accès concurrentiel]"
ms.assetid: 9c5149f9-ac34-4ff3-9e79-0bad103e4e6b
caps.latest.revision: 17
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: sp&#233;cifier des strat&#233;gies de planificateur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stratégies de planificateur vous permettent de contrôler la stratégie utilisée par le planificateur lorsqu’il gère des tâches. Cette rubrique montre comment utiliser une stratégie du planificateur pour augmenter la priorité de thread d’une tâche qui imprime un indicateur de progression sur la console.  
  
 Pour obtenir un exemple qui utilise des stratégies du planificateur personnalisées avec des agents asynchrones, consultez [Comment : créer des Agents qui utiliser des stratégies de planificateur spécifiques](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant effectue deux tâches en parallèle. La première tâche calcule le n<sup>th</sup> nombre de Fibonacci. La deuxième tâche imprime un indicateur de progression sur la console.  
  
 La première tâche utilise la décomposition récursive pour calculer le nombre de Fibonacci. Autrement dit, chaque tâche de manière récursive crée des sous-tâches pour calculer le résultat global. Une tâche qui utilise la décomposition récursive peut utiliser toutes les ressources disponibles et ce qui retarde l’exécution d’autres tâches. Dans cet exemple, la tâche qui imprime l’indicateur de progression ne recevront pas accès aux ressources de calcul.  
  
 Pour que la tâche qui imprime un progression message juste l’accès aux ressources de calcul, cet exemple utilise les étapes décrites dans [Comment : gérer une Instance du planificateur](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) pour créer une instance du planificateur ayant une stratégie personnalisée. La stratégie personnalisée spécifie la priorité de thread pour la classe de priorité la plus élevée.  
  
 Cet exemple utilise le [concurrency::call](../../parallel/concrt/reference/call-class.md) et [concurrency::timer](../../parallel/concrt/reference/timer-class.md) classes pour imprimer l’indicateur de progression. Ces classes ont des versions de leurs constructeurs qui prennent une référence à un [concurrency::Scheduler](../../parallel/concrt/reference/scheduler-class.md) objet qui les planifie. L’exemple utilise le planificateur par défaut pour planifier la tâche qui calcule le nombre de Fibonacci et l’instance du planificateur pour planifier la tâche qui imprime l’indicateur de progression.  
  
 Pour illustrer les avantages de l’utilisation d’un planificateur ayant une stratégie personnalisée, cet exemple effectue la tâche totale à deux reprises. L’exemple utilise tout d’abord le planificateur par défaut pour planifier les deux tâches. L’exemple utilise ensuite le planificateur par défaut pour planifier la première tâche et un planificateur ayant une stratégie personnalisée pour planifier la deuxième tâche.  
  
 [!code-cpp[concrt-scheduler-policy#1](../../parallel/concrt/codesnippet/CPP/how-to-specify-specific-scheduler-policies_1.cpp)]  
  
 Cet exemple produit la sortie suivante.  
  
```Output  
Default scheduler:  
...........................................................................done  
Scheduler that has a custom policy:  
...........................................................................done  
```  
  
 Bien que les deux ensembles de tâches produisent le même résultat, la version qui utilise une stratégie personnalisée permet à la tâche qui imprime l’indicateur de progression afin d’exécuter avec une priorité élevée meilleure réactivité.  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Copiez l’exemple de code et collez-le dans un projet Visual Studio ou le coller dans un fichier nommé `scheduler-policy.cpp` puis exécutez la commande suivante dans une fenêtre d’invite de commandes Visual Studio.  
  
 **CL.exe /EHsc scheduler-Policy.cpp**  
  
## <a name="see-also"></a>Voir aussi  
 [Stratégies de planificateur](../../parallel/concrt/scheduler-policies.md)   
 [Comment : gérer une Instance du planificateur](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)   
 [Comment : créer des Agents qui utilisent des stratégies de planificateur spécifiques](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)

