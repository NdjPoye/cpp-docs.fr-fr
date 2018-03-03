---
title: "Comment : envoyer un Message à intervalles réguliers | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- timer class, example
- sending messages at regular intervals [Concurrency Runtime]
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f12d9f8af028d1e2e1fc149eeb77181c2f6b1730
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-send-a-message-at-a-regular-interval"></a>Comment : envoyer un message à intervalles réguliers
Cet exemple montre comment utiliser l’accès concurrentiel ::[classe timer](../../parallel/concrt/reference/timer-class.md) pour envoyer un message à intervalles réguliers.  
  
## <a name="example"></a>Exemple  

 L’exemple suivant utilise un `timer` objet pour signaler la progression pendant une longue opération. Cet exemple lie le `timer` de l’objet à un [concurrency::call](../../parallel/concrt/reference/call-class.md) objet. Le `call` objet imprime un indicateur de progression dans la console à intervalles réguliers. Le [Concurrency::Timer :: Start](reference/timer-class.md#start) méthode exécute la minuterie sur un contexte distinct. Le `perform_lengthy_operation` les appels de fonction le [concurrency::wait](reference/concurrency-namespace-functions.md#wait) fonction sur le contexte principal pour simuler une longue opération.  

  
 [!code-cpp[concrt-report-progress#1](../../parallel/concrt/codesnippet/cpp/how-to-send-a-message-at-a-regular-interval_1.cpp)]  
  
 Cet exemple génère la sortie suivante :  
  
```Output  
Performing a lengthy operation..........done.  
```  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Copiez l’exemple de code et collez-le dans un projet Visual Studio ou collez-le dans un fichier nommé `report-progress.cpp` , puis exécutez la commande suivante dans une fenêtre d’invite de commandes Visual Studio.  
  
 **CL.exe /EHsc report-progress.cpp**  
  
## <a name="see-also"></a>Voir aussi  
 [Bibliothèque d’agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md)   
 [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Fonctions de passage de messages](../../parallel/concrt/message-passing-functions.md)
