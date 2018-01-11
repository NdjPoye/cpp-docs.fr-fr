---
title: "Comment : fournir des fonctions de travail aux Classes call et transformer | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- call class, example
- using the transformer class [Concurrency Runtime]
- using the call class [Concurrency Runtime]
ms.assetid: df715ce4-8507-41ca-b204-636d11707a73
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 52ab28a015fa0312a5d064401451640c2747e9db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-provide-work-functions-to-the-call-and-transformer-classes"></a>Comment : fournir des fonctions de travail aux classes call et transformer
Cette rubrique illustre plusieurs méthodes pour fournir des fonctions de travail pour le [concurrency::call](../../parallel/concrt/reference/call-class.md) et [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md) classes.  
  
 Le premier exemple montre comment passer une expression lambda à une `call` objet. Le deuxième exemple montre comment passer un objet de fonction à un `call` objet. Le troisième exemple montre comment lier une méthode de classe pour un `call` objet.  
  
 À titre d’illustration, tous les exemples dans cette rubrique utilise le `call` classe. Pour obtenir un exemple qui utilise le `transformer` de classe, consultez [Comment : utiliser la classe transformer dans un Pipeline de données](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre une façon courante d’utiliser la `call` classe. Cet exemple passe une fonction lambda à la `call` constructeur.  
  
 [!code-cpp[concrt-call-lambda#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_1.cpp)]  
  
 Cet exemple produit la sortie suivante.  
  
```Output  
13 squared is 169.  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant ressemble au précédent, sauf qu’elle utilise le `call` classe avec un objet de fonction (functor).  
  
 [!code-cpp[concrt-call-functor#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_2.cpp)]  
  
## <a name="example"></a>Exemple  

 L’exemple suivant ressemble au précédent, sauf qu’elle utilise le [std::bind1st](../../standard-library/functional-functions.md#bind1st) et [std::mem_fun](../../standard-library/functional-functions.md#mem_fun) fonctions pour lier un `call` objet à une méthode de classe.  

  
 Utilisez cette technique si vous avez besoin de lier un `call` ou `transformer` objet à une méthode de classe spécifique au lieu de l’opérateur d’appel de fonction `operator()`.  
  
 [!code-cpp[concrt-call-method#1](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_3.cpp)]  
  
 Vous pouvez également affecter le résultat de la `bind1st` de fonction à un [std::function](../../standard-library/function-class.md) ou d’utiliser le `auto` (mot clé), comme indiqué dans l’exemple suivant.  
  
 [!code-cpp[concrt-call-method#2](../../parallel/concrt/codesnippet/cpp/how-to-provide-work-functions-to-the-call-and-transformer-classes_4.cpp)]  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Copiez l’exemple de code et collez-le dans un projet Visual Studio ou collez-le dans un fichier nommé `call.cpp` , puis exécutez la commande suivante dans une fenêtre d’invite de commandes Visual Studio.  
  
 **CL.exe /EHsc call.cpp**  
  
## <a name="see-also"></a>Voir aussi  
 [Bibliothèque d’agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md)   
 [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Comment : utiliser la classe transformer dans un Pipeline de données](../../parallel/concrt/how-to-use-transformer-in-a-data-pipeline.md)   
 [Call, classe](../../parallel/concrt/reference/call-class.md)   
 [transformer, classe](../../parallel/concrt/reference/transformer-class.md)
