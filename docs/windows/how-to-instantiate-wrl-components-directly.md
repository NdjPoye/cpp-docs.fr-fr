---
title: "Comment&#160;: instancier directement les composants WRL | Microsoft Docs"
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
ms.assetid: 1a9fa011-0cee-4abf-bf83-49adf53ff906
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: instancier directement les composants WRL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Apprenez comment utiliser [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) [Microsoft::WRL::Make](../windows/make-function.md) et les fonctions [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md) pour instancier un composant du module qui le définit.  
  
 En instanciant des composants directement, réduisez la charge mémoire lorsque vous n'avez pas besoin de fabriques de classes ou d'autres mécanismes.  Instanciez un composant directement dans les deux applications [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] et dans les applications de bureau.  
  
 Pour apprendre à utiliser [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] pour créer un composant de base [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] et l'instancier d'une application externe [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], consultez [Procédure pas à pas : création d'un composant Windows Runtime de base](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md).  Pour apprendre à utiliser [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] pour créer un composant de base COM et l'instancier d'une application externe , consultez [Comment : créer un composant COM classique](../windows/how-to-create-a-classic-com-component-using-wrl.md).  
  
 Ce document affiche deux exemples.  Le premier exemple utilise la fonction `Make` pour instancier un composant.  Le deuxième exemple utilise la fonction `MakeAndInitialize` pour instancier un composant qui peut échouer pendant la construction. \(Comme COM utilise généralement des valeurs `HRESULT`, au lieu des exceptions, pour afficher les erreurs, un type COM en général ne lève pas de constructeur.  `MakeAndInitialize` permet à un composant de valider ses arguments de construction via la méthode `RuntimeClassInitialize` .\) Les deux exemples définissent une interface de journal et implémentent cette interface en définissant une classe qui écrit des messages dans la console.  
  
> [!IMPORTANT]
>  Vous ne pouvez pas utiliser l'opérateur `new` pour instancier des composants [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)].  Par conséquent, il est recommandé d'utiliser systématiquement `Make` ou `MakeAndInitialize` pour instancier un composant directement.  
  
### Pour créer et instancier un composant de base du journal  
  
1.  Dans Visual Studio, créez un projet **Win32 Application Console**.  Nommez le projet, par exemple, `WRLLogger`.  
  
2.  Ajoutez un fichier **Fichier Midl \(.idl\)** au projet, nommez le fichier `ILogger.idl`, puis ajoutez ce code :  
  
     [!code-cpp[wrl-logger-make#1](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_1.idl)]  
  
3.  Utilisez le code suivant pour remplacer le contenu de WRLLogger.cpp.  
  
     [!code-cpp[wrl-logger-make#2](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_2.cpp)]  
  
### Pour gérer l'échec de construction pour le composant de base du journal  
  
1.  Utilisez le code suivant pour remplacer la définition de la classe `CConsoleWriter`.  Cette version maintient une variable membre privée de chaîne et substitue la méthode `RuntimeClass::RuntimeClassInitialize`.  `RuntimeClassInitialize` échoue si l'appel à `SHStrDup` échoue.  
  
     [!code-cpp[wrl-logger-makeandinitialize#1](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_3.cpp)]  
  
2.  Utilisez le code suivant pour remplacer la définition de la classe `wmain`.  Cette version utilise `MakeAndInitialize` pour instancier l'objet `CConsoleWriter` et active le résultat de `HRESULT`.  
  
     [!code-cpp[wrl-logger-makeandinitialize#2](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_4.cpp)]  
  
## Voir aussi  
 [Bibliothèque de modèles Windows Runtime C\+\+ \(WRL\)](../windows/windows-runtime-cpp-template-library-wrl.md)   
 [Microsoft::WRL::Make](../windows/make-function.md)   
 [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md)