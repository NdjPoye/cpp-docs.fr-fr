---
title: "Comment&#160;: terminer une op&#233;ration asynchrone &#224; l&#39;aide de WRL | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 02173eae-731b-49bc-b412-f1f69388b99d
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: terminer une op&#233;ration asynchrone &#224; l&#39;aide de WRL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ce document montre comment utiliser [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)]\([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) pour démarrer des opérations asynchrones et effectuer des actions lorsque les opérations se terminent.  
  
 Ce document affiche deux exemples.  Le premier exemple démarre une horloge asynchrone et attend que le temps expire.  Dans cet exemple, vous spécifiez l'action asynchrone lorsque vous créez l'objet du minuteur.  Le deuxième exemple lance un thread de travail en arrière\-plan.  Cet exemple montre comment utiliser une méthode [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] qui retourne une interface `IAsyncInfo`.  La fonction [Rappel](../windows/callback-function-windows-runtime-cpp-template-library.md) est une partie importante des deux exemples car elle leur permet de définir un gestionnaire d'événements pour traiter les résultats des opérations asynchrones.  
  
 Pour obtenir un exemple plus basique qui crée une instance de ce composant et récupère une valeur de propriété, consultez [Comment : activer et utiliser un composant Windows Runtime Component](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).  
  
> [!TIP]
>  Ces exemples utilisent des expressions lambda pour définir les rappels.  Vous pouvez également utiliser des objets de fonction \(foncteurs\), les pointeurs de fonction, ou les objets [std::function](../standard-library/function-class.md).  Pour plus d'informations sur les expressions lambda en C\+\+, consultez [Expressions lambda](../cpp/lambda-expressions-in-cpp.md).  
  
## Exemple : Travailler avec un minuteur  
 Les étapes suivantes lancent un minuteur asynchrone et attende que le temps expire.  Voici un exemple de code complet :  
  
> [!WARNING]
>  Bien que vous utilisiez généralement [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] dans une application [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], cet exemple utilise une application console à titre d'illustration.  Les fonctions telles que `wprintf_s` ne sont pas disponibles à partir d'une application [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)].  Pour plus d'informations sur les types et les fonctions que vous pouvez utiliser dans une application [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], consultez [Fonctions CRT non prises en charge par \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx) et [Win32 et COM pour les applications du  Windows Store](http://msdn.microsoft.com/library/windows/apps/br205757.aspx).  
  
1.  Incluez \(`#include`\) tous les en\-têtes de bibliothèque C\+\+ [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] ou standard requis.  
  
     [!code-cpp[wrl-consume-async#2](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_1.cpp)]  
  
     Windows.System.Threading.h indique les types requis pour utiliser une horloge asynchrone.  
  
     Nous vous recommandons d'utiliser la directive `using namespace` dans votre fichier .cpp pour rendre le code plus lisible.  
  
2.  Initialise le[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
     [!code-cpp[wrl-consume-async#3](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_2.cpp)]  
  
3.  Créez une fabrique d'activation pour l'interface `ABI::Windows::System::Threading::IThreadPoolTimer`.  
  
     [!code-cpp[wrl-consume-async#4](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_3.cpp)]  
  
     Le [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]utilises des noms complétement qualifiés pour identifier les types.  Le paramètre `RuntimeClass_Windows_System_Threading_ThreadPoolTimer` est une chaîne fournie par le[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] et contient le nom de classe runtime requis.  
  
4.  Créez un objet [Événement](../windows/event-class-windows-runtime-cpp-template-library.md) qui synchronise les rappels de l'horloge à l'application principale.  
  
     [!code-cpp[wrl-consume-async#5](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_4.cpp)]  
  
    > [!NOTE]
    >  Cet événement est là pour la démonstration uniquement en tant qu'application de console.  Cet exemple utilise l'événement pour garantir qu'une opération asynchrone se termine avant que l'application ne quitte.  Dans la plupart des applications, en général vous n'attendez pas la fin des opérations asynchrones.  
  
5.  Créez un objet `IThreadPoolTimer` qui expire après deux secondes.  Utilisez la fonction`Callback` pour créer le gestionnaire d'événements \(objet `ABI::Windows::System::Threading::ITimerElapsedHandler` \).  
  
     [!code-cpp[wrl-consume-async#6](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_5.cpp)]  
  
6.  Imprime un message à la console et attend que le rappel du minuteur soit terminé.  Tous les objets `ComPtr` et RAII quittent la portée et sont libérés automatiquement.  
  
     [!code-cpp[wrl-consume-async#7](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_6.cpp)]  
  
 Voici l'exemple complet.  
  
 [!code-cpp[wrl-consume-async#1](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_7.cpp)]  
  
### Compilation du code  
 Pour compiler le code, copiez\-le puis collez\-le dans un projet Visual Studio, ou collez\-le dans un fichier qui soit nommé`wrl-consume-async.cpp`,et lancez ensuite la commande suivante dans une fenetre Visual Studio de Commande.  
  
 **cl.exe wrl\-consume\-async.cpp runtimeobject.lib**  
  
## Exemple : Utilisation d'un thread d'arrière\-plan  
 Les étapes suivantes démarrent un thread de travail et définissent l'action qui est effectuée par ce thread.  Voici un exemple de code complet :  
  
> [!TIP]
>  Cet exemple montre comment utiliser l'interface `ABI::Windows::Foundation::IAsyncAction`.  Vous pouvez appliquer ce modèle à n'importe quelle interface qui implémente `IAsyncInfo`: `IAsyncAction`, `IAsyncActionWithProgress`, `IAsyncOperation`, et `IAsyncOperationWithProgress`.  
  
1.  Incluez \(`#include`\) tous les en\-têtes de bibliothèque C\+\+ [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] ou standard requis.  
  
     [!code-cpp[wrl-consume-asyncOp#2](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_8.cpp)]  
  
     Windows.System.Threading.h indique les types requis pour utiliser un thread de travail.  
  
     Nous vous recommandons d'utiliser la directive `using namespace` dans votre fichier .cpp pour rendre le code plus lisible.  
  
2.  Initialise le[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
     [!code-cpp[wrl-consume-asyncOp#3](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_9.cpp)]  
  
3.  Créez une fabrique d'activation pour l'interface `ABI::Windows::System::Threading::IThreadPoolStatics`.  
  
     [!code-cpp[wrl-consume-asyncOp#4](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_10.cpp)]  
  
4.  Créez un objet [Événement](../windows/event-class-windows-runtime-cpp-template-library.md) qui synchronise l'exécution du thread de travail avec l'application principale.  
  
     [!code-cpp[wrl-consume-asyncOp#5](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_11.cpp)]  
  
    > [!NOTE]
    >  Cet événement est là pour la démonstration uniquement en tant qu'application de console.  Cet exemple utilise l'événement pour garantir qu'une opération asynchrone se termine avant que l'application ne quitte.  Dans la plupart des applications, en général vous n'attendez pas la fin des opérations asynchrones.  
  
5.  Appelez la méthode `IThreadPoolStatics::RunAsync` pour créer un thread de travail.  Utilisez la fonction`Callback` pour définir l'action.  
  
     [!code-cpp[wrl-consume-asyncOp#6](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_12.cpp)]  
  
     La fonction `IsPrime` est définie dans l'exemple complet qui suit.  
  
6.  Imprime un message à la console et attend que le thread ait terminé.  Tous les objets `ComPtr` et RAII quittent la portée et sont libérés automatiquement.  
  
     [!code-cpp[wrl-consume-asyncOp#7](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_13.cpp)]  
  
 Voici l'exemple complet.  
  
 [!code-cpp[wrl-consume-asyncOp#1](../windows/codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_14.cpp)]  
  
### Compilation du code  
 Pour compiler le code, copiez\-le puis collez\-le dans un projet Visual Studio, ou collez\-le dans un fichier qui soit nommé`wrl-consume-async.cpp`,et lancez ensuite la commande suivante dans une fenetre Visual Studio de Commande.  
  
 **cl.exe wrl\-consume\-asyncOp.cpp runtimeobject.lib**  
  
## Voir aussi  
 [Bibliothèque de modèles Windows Runtime C\+\+ \(WRL\)](../windows/windows-runtime-cpp-template-library-wrl.md)