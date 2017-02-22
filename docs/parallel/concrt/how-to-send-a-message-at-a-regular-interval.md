---
title: "Comment&#160;: envoyer un message &#224; intervalles r&#233;guliers | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "timer, classe, exemple"
  - "envoyer des messages à intervalles réguliers [Runtime d’accès concurrentiel]"
ms.assetid: 4b60ea6c-97c8-4d69-9f7b-ad79f3548026
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Comment&#160;: envoyer un message &#224; intervalles r&#233;guliers
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cet exemple montre comment utiliser l’accès concurrentiel ::[classe timer](../../parallel/concrt/reference/timer-class.md) pour envoyer un message à intervalles réguliers.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant utilise un `timer` objet pour signaler la progression pendant une longue opération. Cet exemple lie le `timer` de l’objet à un [concurrency::call](../../parallel/concrt/reference/call-class.md) objet. Le `call` objet imprime un indicateur de progression sur la console à intervalle régulier. Le [Concurrency::Timer :: Start](../Topic/timer::start%20Method.md) méthode exécute la minuterie sur un contexte distinct. Le `perform_lengthy_operation` les appels de fonction la [concurrency::wait](../Topic/wait%20Function.md) fonction sur le contexte principal pour simuler une longue opération.  
  
 [!code-cpp[concrt-report-progress#1](../../parallel/concrt/codesnippet/CPP/how-to-send-a-message-at-a-regular-interval_1.cpp)]  
  
 Cet exemple génère la sortie suivante :  
  
```Output  
Performing a lengthy operation..........done.  
```  
  
## <a name="compiling-the-code"></a>Compilation du code  
 Copiez l’exemple de code et collez-le dans un projet Visual Studio ou le coller dans un fichier nommé `report-progress.cpp` puis exécutez la commande suivante dans une fenêtre d’invite de commandes Visual Studio.  
  
 **CL.exe /EHsc report-progress.cpp**  
  
## <a name="see-also"></a>Voir aussi  
 [Bibliothèque d’Agents asynchrones](../../parallel/concrt/asynchronous-agents-library.md)   
 [Blocs de messages asynchrones](../../parallel/concrt/asynchronous-message-blocks.md)   
 [Fonctions de passage de message](../../parallel/concrt/message-passing-functions.md)
