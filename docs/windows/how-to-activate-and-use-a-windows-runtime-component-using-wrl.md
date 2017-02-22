---
title: "Comment&#160;: activer et utiliser un composant Windows Runtime Component &#224; l&#39;aide de WRL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 54828f02-6af3-45d1-b965-d0104442f8d5
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Comment&#160;: activer et utiliser un composant Windows Runtime Component &#224; l&#39;aide de WRL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ce document indique comment utiliser [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\)pour initialiser le [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]et comment activer et utiliser un composant [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
> [!NOTE]
>  Cet exemple active un composant intégré [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  Pour apprendre à créer votre propre composant que vous pouvez activer de manière similaire, consultez [Procédure pas à pas : création d'un composant Windows Runtime de base](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md).  
  
 Pour utiliser un composant, vous devez obtenir un pointeur d'interface du type qui est implémenté par le composant.  Comme la technologie [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] sous\-jacente est le modèle COM \(component object model\), vous devez suivre les règles COM pour maintenir une instance de ce type.  Par exemple, vous devez maintenir *le nombre de références* qui détermine à quel moment le type est supprimé de la mémoire.  
  
 Pour simplifier l'utilisation de[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] fournit le modèle intelligent du pointeur, [ComPtr\<T\>](../windows/comptr-class.md), qui effectue automatiquement le décompte de références.  Lorsque vous déclarez une variable, spécifiez `ComPtr<`*interface\-name*`>` *identifier*.  Pour accéder à un membre de l'interface, appliquez l'opérateur d'accès aux membres \(`->`\) à l'identificateur.  
  
> [!IMPORTANT]
>  Lorsque vous appelez une fonction de l'interface, testez toujours la valeur de retour de`HRESULT`.  
  
## Activation et utilisation d'un composant d'exécution Windows  
 Les étapes suivantes utilisent l'interface `Windows::Foundation::IUriRuntimeClass` pour illustrer comment créer une fabrique d'activation pour un composant [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], créer une instance de ce composant, et récupérer une valeur de propriété.  Ils indiquent également comment initialiser [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  Voici un exemple de code complet :  
  
> [!IMPORTANT]
>  Bien que vous utilisiez généralement [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] dans une application [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], cet exemple utilise une application console à titre d'illustration.  Les fonctions telles que `wprintf_s` ne sont pas disponibles à partir d'une application [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)].  Pour plus d'informations sur les types et les fonctions que vous pouvez utiliser dans une application [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)], consultez [Fonctions CRT non prises en charge par \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx) et [Win32 et COM pour les applications du  Windows Store](http://msdn.microsoft.com/library/windows/apps/br205757.aspx).  
  
#### Pour activer et utiliser un composant Windows RunTime  
  
1.  Incluez \(`#include`\) tous les en\-têtes de bibliothèque C\+\+ [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] ou standard requis.  
  
     [!code-cpp[wrl-consume-component#2](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_1.cpp)]  
  
     Nous vous recommandons d'utiliser la directive `using namespace` dans votre fichier .cpp pour rendre le code plus lisible.  
  
2.  Initialisez le thread dans lequel l'application s'exécute.  Chaque application doit initialiser son thread et modèle de thread.  Cet exemple utilise la classe[Microsoft::WRL::Wrappers::RoInitializeWrapper](../windows/roinitializewrapper-class.md) pour initialiser [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] et spécifie [RO\_INIT\_MULTITHREADED](http://msdn.microsoft.com/library/windows/apps/br224661.aspx) en tant que modèle de thread.  La classe `RoInitializeWrapper` appelle `Windows::Foundation::Initialize` à la construction, et `Windows::Foundation::Uninitialize` et à la destruction.  
  
     [!code-cpp[wrl-consume-component#3](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_2.cpp)]  
  
     Dans la deuxième instruction, l'opérateur[RoInitializeWrapper::HRESULT](../windows/roinitializewrapper-hresult-parens-operator.md) retourne `HRESULT` de l'appel à `Windows::Foundation::Initialize`.  
  
3.  Créez une *fabrique d'activation* pour l'interface `ABI::Windows::Foundation::IUriRuntimeClassFactory` .  
  
     [!code-cpp[wrl-consume-component#4](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_3.cpp)]  
  
     Le [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]utilises des noms complétement qualifiés pour identifier les types.  Le paramètre `RuntimeClass_Windows_Foundation_Uri` est une chaîne fournie par le[!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] et contient le nom de classe runtime requis.  
  
4.  Initialise une variable [Microsoft::WRL::Wrappers::HString](../windows/hstring-class.md) qui représente l'URI `"http://www.microsoft.com"`.  
  
     [!code-cpp[wrl-consume-component#6](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_4.cpp)]  
  
     Dans [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], vous n'allouez pas la mémoire pour une chaîne qui utilisera [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  En revanche, [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] crée une copie de votre chaîne dans une mémoire tampon qu'il gère et utilise pour des opérations, puis retourne un descripteur de la mémoire tampon qu'il a créée.  
  
5.  Utilisez les méthodes de fabrique `IUriRuntimeClassFactory::CreateUri` pour créer un objet `ABI::Windows::Foundation::IUriRuntimeClass`.  
  
     [!code-cpp[wrl-consume-component#7](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_5.cpp)]  
  
6.  Appelez la méthode `IUriRuntimeClass::get_Domain` pour extraire la valeur de la propriété `Domain`.  
  
     [!code-cpp[wrl-consume-component#8](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_6.cpp)]  
  
7.  Imprimez le nom de domaine dans la console et retournez.  Tous les objets `ComPtr` et RAII quittent la portée et sont libérés automatiquement.  
  
     [!code-cpp[wrl-consume-component#9](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_7.cpp)]  
  
     [WindowsGetStringRawBuffer](http://msdn.microsoft.com/library/windows/apps/br224636.aspx) La fonction récupère la forme sous\-jacente Unicode de la chaîne d'URI.  
  
 Voici l'exemple complet:  
  
 [!code-cpp[wrl-consume-component#1](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_8.cpp)]  
  
## Compilation du code  
 Pour compiler le code, copiez\-le puis collez\-le dans un projet Visual Studio, ou collez\-le dans un fichier qui soit nommé`wrl-consume-async.cpp`,et lancez ensuite la commande suivante dans une fenetre Visual Studio de Commande.  
  
 **cl.exe wrl\-consume\-component.cpp runtimeobject.lib**  
  
## Voir aussi  
 [Bibliothèque de modèles Windows Runtime C\+\+ \(WRL\)](../windows/windows-runtime-cpp-template-library-wrl.md)