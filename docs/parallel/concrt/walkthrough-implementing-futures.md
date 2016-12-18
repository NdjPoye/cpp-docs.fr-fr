---
title: "Proc&#233;dure pas &#224; pas&#160;: impl&#233;mentation d’objets future | Microsoft Docs"
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
  - "implémenter des objets future [Runtime d’accès concurrentiel]"
  - "future (objets), implémenter [Runtime d’accès concurrentiel]"
ms.assetid: 82ea75cc-aaec-4452-b10d-8abce0a87e5b
caps.latest.revision: 25
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Proc&#233;dure pas &#224; pas&#160;: impl&#233;mentation d’objets future
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique montre comment implémenter des tâches futures dans votre application. La rubrique illustre comment combiner les fonctionnalités existantes du runtime d’accès concurrentiel en quelque chose de plus.  
  
> [!IMPORTANT]
>  Cette rubrique illustre le concept de futures à des fins de démonstration. Nous vous recommandons d’utiliser [std::future](../../standard-library/future-class.md) ou [concurrency::task](../../parallel/concrt/reference/task-class-concurrency-runtime.md) lorsque vous avez besoin d’une tâche asynchrone qui calcule une valeur pour une utilisation ultérieure.  
  
 Un *tâche* est un calcul qui peut être décomposé en plusieurs calculs affinés. Un *futures* est une tâche asynchrone qui calcule une valeur pour une utilisation ultérieure.  
  
 Pour implémenter des tâches futures, cette rubrique définit la `async_future` classe. La `async_future` classe utilise ces composants du Runtime d’accès concurrentiel : le [concurrency::task_group](../Topic/task_group%20Class.md) classe et [concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md) classe. La `async_future` classe utilise le `task_group` classe pour calculer une valeur de façon asynchrone et la `single_assignment` classe pour stocker le résultat du calcul. Le constructeur de la `async_future` classe accepte une fonction de travail qui calcule le résultat, et le `get` méthode extrait le résultat.  
  
### <a name="to-implement-the-asyncfuture-class"></a>Pour implémenter la classe async_future  
  
1.  Déclarez une classe de modèle nommée `async_future` qui est paramétrée sur le type du calcul résultant. Ajouter `public` et `private` sections à cette classe.  
  
 [!code-cpp[concrt-futures#2](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_1.cpp)]  
  
2.  Dans la `private` section de la `async_future` classe, déclarez un `task_group` et un `single_assignment` membre de données.  
  
 [!code-cpp[concrt-futures#3](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_2.cpp)]  
  
3.  Dans la `public` section de la `async_future` de classe, implémentez le constructeur. Le constructeur est un modèle paramétrable sur la fonction de travail qui calcule le résultat. Le constructeur exécute de façon asynchrone la fonction de travail dans le `task_group` membre de données et utilise le [concurrency::send](../Topic/send%20Function.md) fonction pour écrire le résultat à le `single_assignment` membre de données.  
  
 [!code-cpp[concrt-futures#4](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_3.cpp)]  
  
4.  Dans la `public` section de la `async_future` de classe, implémentez le destructeur. Le destructeur attend que la tâche se termine.  
  
 [!code-cpp[concrt-futures#5](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_4.cpp)]  
  
5.  Dans la `public` section de la `async_future` classe, implémentez la `get` méthode. Cette méthode utilise le [concurrency::receive](../Topic/receive%20Function.md) fonction pour récupérer le résultat de la fonction de travail.  
  
 [!code-cpp[concrt-futures#6](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_5.cpp)]  
  
## <a name="example"></a>Exemple  
  
### <a name="description"></a>Description  
 L’exemple suivant montre la version complète `async_future` classe et un exemple de son utilisation. Le `wmain` fonction crée un std ::[vecteur](vector%20Class.md) objet qui contient 10 000 valeurs entières aléatoires. Il utilise ensuite `async_future` objets pour rechercher les valeurs minimale et maximale qui figurent dans la `vector` objet.  
  
### <a name="code"></a>Code  
 [!code-cpp[concrt-futures#1](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_6.cpp)]  
  
### <a name="comments"></a>Commentaires  
 Cet exemple génère la sortie suivante :  
  
```Output  
smallest: 0  
largest:  9999  
average:  4981  
```  
  
 L’exemple utilise le `async_future::get` méthode pour récupérer les résultats du calcul. Le `async_future::get` méthode attend que le calcul se termine si le calcul est toujours actif.  
  
## <a name="robust-programming"></a>Programmation fiable  
 Pour étendre la `async_future` classe pour gérer les exceptions levées par la fonction de travail, modifiez le `async_future::get` méthode à appeler le [Concurrency::task_group :: wait](../Topic/task_group::wait%20Method.md) méthode. Le `task_group::wait` méthode lève des exceptions générées par la fonction de travail.  
  
 L’exemple suivant montre la version modifiée de la `async_future` classe. Le `wmain` fonction utilise un `try`-`catch` bloc pour imprimer le résultat de la `async_future` objet ou pour imprimer la valeur de l’exception qui est générée par la fonction de travail.  
  
 [!code-cpp[concrt-futures-with-eh#1](../../parallel/concrt/codesnippet/CPP/walkthrough-implementing-futures_7.cpp)]  
  
 Cet exemple génère la sortie suivante :  
  
```Output  
caught exception: error  
```  
  
 Pour plus d’informations sur le modèle de gestion des exceptions dans le Runtime d’accès concurrentiel, consultez [la gestion des exceptions](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md).  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Copiez l’exemple de code et collez-le dans un projet Visual Studio ou le coller dans un fichier nommé `futures.cpp` puis exécutez la commande suivante dans une fenêtre d’invite de commandes Visual Studio.  
  
 **CL.exe /EHsc futures.cpp**  
  
## <a name="see-also"></a>Voir aussi  
 [Procédures pas à pas Runtime d’accès concurrentiel](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [Gestion des exceptions](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [task_group, classe](../Topic/task_group%20Class.md)   
 [Classe single_assignment](../../parallel/concrt/reference/single-assignment-class.md)
