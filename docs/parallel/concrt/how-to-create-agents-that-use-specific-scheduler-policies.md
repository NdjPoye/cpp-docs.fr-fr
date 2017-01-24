---
title: "Comment&#160;: cr&#233;er des agents qui utilisent des strat&#233;gies de planificateur sp&#233;cifiques | Microsoft Docs"
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
  - "stratégies de planificateur, agents [Runtime d’accès concurrentiel]"
  - "créer des agents qui utilisent des stratégies spécifiques [Runtime d’accès concurrentiel]"
ms.assetid: 46a3e265-0777-4ec3-a142-967bafc49d67
caps.latest.revision: 14
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: cr&#233;er des agents qui utilisent des strat&#233;gies de planificateur sp&#233;cifiques
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Un agent est un composant d'application qui fonctionne de façon asynchrone avec d'autres composants en vue d'effectuer de plus grandes tâches de calcul.  Un agent a en général un cycle de vie fixe et conserve l'état.  
  
 Chaque agent peut avoir des spécifications d'application uniques.  Par exemple, un agent qui active l'intervention de l'utilisateur \(extraction de l'entrée ou affichage de la sortie\) peut nécessiter un accès à priorité plus élevée aux ressources de calcul.  Les stratégies du planificateur vous permettent de contrôler la stratégie utilisée par le planificateur lorsqu'il gère des tâches.  Cette rubrique explique comment créer des agents qui utilisent des stratégies de planificateur spécifiques.  
  
 Pour obtenir un exemple de base qui utilise des stratégies du planificateur personnalisées avec des blocs de messages asynchrones, consultez [Comment : spécifier des stratégies de planificateur](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md).  
  
 Cette rubrique utilise les fonctionnalités de la Bibliothèque d'agents asynchrones, telles que les agents, les blocs de messages et les fonctions de passage de messages, pour exécuter un travail.  Pour plus d'informations sur la bibliothèque d'agents asynchrones, consultez [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md).  
  
## Exemple  
 L'exemple suivant définit deux classes qui dérivent de [concurrency::agent](../../parallel/concrt/reference/agent-class.md): `permutor` et de `printer` La classe `permutor` calcule toutes les permutations d'une chaîne d'entrée donnée.  La classe `printer` imprime les messages de progression sur la console.  La classe `permutor` effectue une opération nécessitant de nombreuses ressources de calcul et qui risque d'utiliser toutes les ressources disponibles.  Pour être utile, la classe `printer` doit imprimer chaque message de progression en temps opportun.  
  
 Pour fournir à la classe `printer` un accès équitable aux ressources de calcul, cet exemple utilise les étapes décrites dans [Comment : gérer une instance de planificateur](../../parallel/concrt/how-to-manage-a-scheduler-instance.md) pour créer une instance du planificateur ayant une stratégie personnalisée.  La stratégie personnalisée affecte comme priorité de thread la classe de priorité la plus élevée.  
  
 Pour illustrer les avantages offerts par l'utilisation d'un planificateur ayant une stratégie personnalisée, cet exemple effectue la tâche totale à deux reprises.  L'exemple utilise tout d'abord le planificateur par défaut pour planifier les deux tâches.  L'exemple utilise ensuite le planificateur par défaut pour planifier l'objet `permutor`, et un planificateur ayant une stratégie personnalisée pour planifier l'objet `printer`.  
  
 [!code-cpp[concrt-permute-strings#1](../../parallel/concrt/codesnippet/CPP/how-to-create-agents-that-use-specific-scheduler-policies_1.cpp)]  
  
 Cet exemple génère la sortie suivante.  
  
  **Avec le planificateur par défaut :**  
**Calculant les permutations de « pamplemousse »…**  
**100% terminé.**  
**Avec une priorité de contexte plus élevée :**  
**Calculant les permutations de « pamplemousse »…**  
**100% terminé.** Bien que les deux ensembles de tâches produisent le même résultat, la version qui utilise une stratégie personnalisée permet à l'objet `printer` de s'exécuter avec une priorité élevée et donc une meilleure réactivité.  
  
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet `Visual Studio`, ou collez\-le dans un fichier nommé permute\-strings.cpp puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc permute\-strings.cpp**  
  
## Voir aussi  
 [Stratégies de planificateur](../../parallel/concrt/scheduler-policies.md)   
 [Agents asynchrones](../../parallel/concrt/asynchronous-agents.md)   
 