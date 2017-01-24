---
title: "Comment&#160;: g&#233;rer les &#233;v&#233;nements &#224; l&#39;aide de WRL | Microsoft Docs"
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
ms.assetid: 1c77543f-7b0c-4a94-93bf-e3225885ed76
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: g&#233;rer les &#233;v&#233;nements &#224; l&#39;aide de WRL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ce document indique comment utiliser [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) pour s'abonner aux événements d'un objet [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] et les gérer.  
  
 Pour obtenir un exemple plus basique qui crée une instance de ce composant et récupère une valeur de propriété, consultez [Comment : activer et utiliser un composant Windows Runtime Component](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md).  
  
## S'abonner à des événements et les gérer  
 Les étapes suivantes démarrent un objet `ABI::Windows::System::Threading::IDeviceWatcher` et utilisent les gestionnaires d'événements pour surveiller la progression.  L'interface `IDeviceWatcher` vous permet d'énumérer les périphériques asynchrone, ou en arrière\-plan, et de recevoir la notification lorsque les périphériques sont ajoutés, supprimés ou modifiés.  La fonction [Rappel](../windows/callback-function-windows-runtime-cpp-template-library.md) est une partie importante de l'exemple car elle lui permet de spécifier les gestionnaires d'événements qui traitent les résultats de l'opération en arrière\-plan.  Voici un exemple de code complet :  
  
> [!WARNING]
>  Bien que vous utilisiez généralement [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] dans une application [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], cet exemple utilise une application console à titre d'illustration.  Les fonctions telles que `wprintf_s` ne sont pas disponibles à partir d'une application [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)].  Pour plus d'informations sur les types et les fonctions que vous pouvez utiliser dans une application [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], consultez [Fonctions CRT non prises en charge par \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx) et [Win32 et COM pour les applications du  Windows Store](http://msdn.microsoft.com/library/windows/apps/br205757.aspx).  
  
1.  Incluez \(`#include`\) tous les en\-têtes de bibliothèque C\+\+ [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] ou standard requis.  
  
     [!code-cpp[wrl-consume-event#2](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_1.cpp)]  
  
     Windows.Devices.Enumeration.h indique les types requis pour énumérer les périphériques.  
  
     Nous vous recommandons d'utiliser la directive `using namespace` dans votre fichier .cpp pour rendre le code plus lisible.  
  
2.  Déclarez les variables locales pour l'application.  Cet exemple contient le nombre de périphériques énumérés et des jetons d'alignement qui lui permettent d'annuler l'abonnement ultérieurement à ces événements.  
  
     [!code-cpp[wrl-consume-event#7](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_2.cpp)]  
  
3.  Initialise le[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
     [!code-cpp[wrl-consume-event#3](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_3.cpp)]  
  
4.  Créez un objet [Événement](../windows/event-class-windows-runtime-cpp-template-library.md) qui synchronise l'exécution du processus d'énumération avec l'application principale.  
  
     [!code-cpp[wrl-consume-event#4](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_4.cpp)]  
  
    > [!NOTE]
    >  Cet événement est là pour la démonstration uniquement en tant qu'application de console.  Cet exemple utilise l'événement pour garantir qu'une opération asynchrone se termine avant que l'application ne quitte.  Dans la plupart des applications, en général vous n'attendez pas la fin des opérations asynchrones.  
  
5.  Créez une fabrique d'activation pour l'interface `IDeviceWatcher`.  
  
     [!code-cpp[wrl-consume-event#5](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_5.cpp)]  
  
     Le [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]utilises des noms complétement qualifiés pour identifier les types.  Le paramètre `RuntimeClass_Windows_Devices_Enumeration_DeviceInformation` est une chaîne fournie par le[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] et contient le nom de classe runtime requis.  
  
6.  Créez les objets `IDeviceWatcher`.  
  
     [!code-cpp[wrl-consume-event#6](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_6.cpp)]  
  
7.  Utilisez la fonction `Callback` pour s'abonner aux évènements `Added`,  `EnumerationCompleted`, et `Stopped`.  
  
     [!code-cpp[wrl-consume-event#8](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_7.cpp)]  
  
     Le gestionnaire d'événements `Added` incrémente le nombre de périphériques énumérés.  Il arrête le processus d'énumération après que dix périphériques soient trouvés.  
  
     Le gestionnaire d'événements `Stopped` supprime les gestionnaires d'événements et définit l'événement de fin.  
  
     Le gestionnaire d'événements `EnumerationCompleted` arrête le processus d'énumération.  Nous gérons cet événement au cas où il y aura moins de dix de périphériques.  
  
    > [!TIP]
    >  Cet exemple utilise une expression lambda pour définir les rappels.  Vous pouvez également utiliser des objets de fonction \(foncteurs\), les pointeurs de fonction, ou les objets [std::function](../standard-library/function-class.md).  Pour plus d'informations sur les expressions lambda, consultez [Expressions lambda](../cpp/lambda-expressions-in-cpp.md).  
  
8.  Démarrez le processus d'énumération.  
  
     [!code-cpp[wrl-consume-event#9](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_8.cpp)]  
  
9. Attendque le processus d'énumération se termine et imprime un message.  Tous les objets `ComPtr` et RAII quittent la portée et sont libérés automatiquement.  
  
     [!code-cpp[wrl-consume-event#10](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_9.cpp)]  
  
 Voici l'exemple complet.  
  
 [!code-cpp[wrl-consume-event#1](../windows/codesnippet/CPP/how-to-handle-events-using-wrl_10.cpp)]  
  
## Compilation du code  
 Pour compiler le code, copiez\-le puis collez\-le dans un projet Visual Studio, ou collez\-le dans un fichier qui soit nommé`wrl-consume-async.cpp`,et lancez ensuite la commande suivante dans une fenetre Visual Studio de Commande.  
  
 **cl.exe wrl\-consume\-events.cpp runtimeobject.lib**  
  
## Voir aussi  
 [Bibliothèque de modèles Windows Runtime C\+\+ \(WRL\)](../windows/windows-runtime-cpp-template-library-wrl.md)