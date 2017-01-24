---
title: "Comment&#160;: fournir des fonctions de travail aux classes call et transformer | Microsoft Docs"
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
  - "call, classe, exemple"
  - "utiliser la classe transformer [Runtime d’accès concurrentiel]"
  - "utiliser la classe call [Runtime d’accès concurrentiel]"
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
caps.latest.revision: 15
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: fournir des fonctions de travail aux classes call et transformer
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique illustre plusieurs méthodes permettant de fournir des fonctions de travail aux classes [concurrency::call](../../parallel/concrt/reference/call-class.md) et [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md).  
  
 Le premier exemple montre comment passer une expression lambda à un objet `call`.  Le deuxième exemple montre comment passer un objet de fonction à un objet `call`.  Le troisième exemple montre comment lier une méthode de classe à un objet `call`.  
  
 À titre d'illustration, chaque exemple dans cette rubrique utilise la classe `call`.  Pour obtenir un exemple qui utilise la classe `transformer`, consultez [Comment : utiliser la classe transformer dans un pipeline de données](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).  
  
## Exemple  
 L'exemple suivant illustre une manière courante d'utiliser la classe `call`.  Cet exemple passe une fonction lambda au constructeur `call`.  
  
 [!code-cpp[concrt-call-lambda#1](../../parallel/concrt/codesnippet/CPP/how-to-provide-work-functions-to-the-call-and-transformer-classes_1.cpp)]  
  
 Cet exemple génère la sortie suivante.  
  
  **13 au carré vaut 169.**   
## Exemple  
 L'exemple suivant ressemble au précédent, mais il utilise la classe `call` avec un objet de fonction \(functor\).  
  
 [!code-cpp[concrt-call-functor#1](../../parallel/concrt/codesnippet/CPP/how-to-provide-work-functions-to-the-call-and-transformer-classes_2.cpp)]  
  
## Exemple  
 L'exemple suivant ressemble au précédent, mais il utilise les fonctions [std::bind1st](../Topic/bind1st%20Function.md) et [std::mem\_fun](../Topic/mem_fun%20Function.md) pour lier un objet `call` à une méthode de classe.  
  
 Utilisez cette technique si vous devez lier un objet `call` ou `transformer` à une méthode de classe spécifique au lieu de l'opérateur d'appel de fonction, `operator()`.  
  
 [!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/CPP/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]  
  
 Vous pouvez également assigner le résultat de la fonction `bind1st` à un objet [std::function](../../standard-library/function-class.md) ou utiliser le mot clé `auto`, comme indiqué dans l'exemple suivant.  
  
 [!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/CPP/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]  
  
## Compilation du code  
 Copiez l'exemple de code et collez\-le dans un projet Visual Studio , ou collez\-le dans un fichier nommé `call.cpp` puis exécutez la commande suivante dans une fenêtre d'invite de commandes Visual Studio.  
  
 **cl.exe \/EHsc call.cpp**  
  
## Voir aussi  
 [Bibliothèque d'agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md)   
 [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Comment : utiliser la classe transformer dans un pipeline de données](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)   
 [call, classe](../../parallel/concrt/reference/call-class.md)   
 [Classe transformer](../../parallel/concrt/reference/transformer-class.md)