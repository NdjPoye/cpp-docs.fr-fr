---
title: "Comment&#160;: cr&#233;er un composant COM classique &#224; l&#39;aide de WRL | Microsoft Docs"
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
ms.assetid: 5efe7690-90d5-4c3c-9e53-11a14cefcb19
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Comment&#160;: cr&#233;er un composant COM classique &#224; l&#39;aide de WRL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser la [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] ([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]) pour créer des composants COM classiques de base destinés à des applications de bureau, en plus de vous en servir pour les applications du [!INCLUDE[win8_appstore_long](../build/reference/includes/win8_appstore_long_md.md)]. Pour la création de composants COM, la [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] peut nécessiter moins de code que l'ATL. Pour plus d’informations sur le sous-ensemble de COM qui le [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] prend en charge, consultez [bibliothèque de modèles Windows Runtime C++ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).  
  
 Ce document montre comment utiliser la [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] pour créer un composant COM de base. Bien que vous puissiez utiliser le mécanisme de déploiement qui correspond le mieux à vos besoins, ce document contient également une méthode de base pour inscrire et utiliser le composant COM à partir d'une application de bureau.  
  
### <a name="to-use-the-includecppwrlshorttokencppwrlshortmdmd-to-create-a-basic-classic-com-component"></a>Pour utiliser la [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] pour créer un composant COM classique de base  
  
1.  Dans Visual Studio, créez un **blanc** projet. Nommez le projet, par exemple, `WRLClassicCOM`.  
  
2.  Ajouter un **projet Win32** à la solution. Nommez le projet, par exemple, `CalculatorComponent`. Sur le **paramètres de l’Application** onglet, sélectionnez **DLL**.  
  
3.  Ajouter un **fichier Midl (.idl)** fichier au projet. Nommez le fichier, par exemple, `CalculatorComponent.idl`.  
  
4.  Ajoutez ce code à CalculatorComponent.idl :  
  
     [!code-cpp[wrl-classic-com-component#1](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_1.idl)]  
  
5.  Dans CalculatorComponent.cpp, définissez la classe `CalculatorComponent`. Le `CalculatorComponent` hérite de la classe [Microsoft::WRL::RuntimeClass](../windows/runtimeclass-class.md). [Microsoft::wrl::RuntimeClassFlags \< ClassicCom>](../windows/runtimeclassflags-structure.md) Spécifie que la classe dérive de [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509\(v=vs.85\).aspx) et non [IInspectable](http://msdn.microsoft.com/library/br205821\(v=vs.85\).aspx). (`IInspectable` est disponible uniquement pour [!INCLUDE[win8_appstore_short](../windows/includes/win8_appstore_short_md.md)] des composants de l’application.) `CoCreatableClass` crée une fabrique pour la classe qui peut être utilisée avec des fonctions telles que [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615\(v=vs.85\).aspx).  
  
     [!code-cpp[wrl-classic-com-component#2](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_2.cpp)]  
  
6.  Utilisez le code suivant pour remplacer le code dans dllmain.cpp. Ce fichier définit les fonctions d'exportation DLL. Ces fonctions utilisent la [Microsoft::WRL::Module](../windows/module-class.md) pour gérer les fabriques de classe du module de classe.  
  
     [!code-cpp[wrl-classic-com-component#3](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_3.cpp)]  
  
7.  Ajouter un **le fichier de définition de Module (.def)** fichier au projet. Nommez le fichier, par exemple, `CalculatorComponent.def`. Ce fichier fournit à l'éditeur de liens les noms des fonctions à exporter.  
  
8.  Ajoutez ce code à CalculatorComponent.def :  
  
     [!CODE [wrl-classic-com-component#4](../CodeSnippet/VS_Snippets_Misc/wrl-classic-com-component#4)]  
  
9. Ajoutez runtimeobject.lib à la ligne de l'éditeur de liens. Pour savoir comment procéder, consultez [. Fichiers lib en tant qu’entrée de l’éditeur de liens](../build/reference/dot-lib-files-as-linker-input.md).  
  
### <a name="to-consume-the-com-component-from-a-desktop-app"></a>Pour utiliser le composant COM à partir d'une application de bureau  
  
1.  Inscrivez le composant COM dans le Registre Windows. Pour ce faire, créez un fichier des entrées d’inscription, nommez-le `RegScript.reg`, et ajoutez le texte suivant. Remplacez *\< dll-path >* avec le chemin d’accès de votre DLL, par exemple, `C:\\temp\\WRLClassicCOM\\Debug\\CalculatorComponent.dll`.  
  
     [!CODE [wrl-classic-com-component#5](../CodeSnippet/VS_Snippets_Misc/wrl-classic-com-component#5)]  
  
2.  Exécutez RegScript.reg ou ajoutez-le à votre projet **événement post-Build**. Pour plus d’informations, consultez [pré-build/Post-build ligne de commande boîte de dialogue événement](../Topic/Pre-build%20Event-Post-build%20Event%20Command%20Line%20Dialog%20Box.md).  
  
3.  Ajouter un **Application Console Win32** projet à la solution. Nommez le projet, par exemple, `Calculator`.  
  
4.  Utilisez ce code pour remplacer le contenu de Calculator.cpp :  
  
     [!code-cpp[wrl-classic-com-component#6](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_6.cpp)]  
  
## <a name="robust-programming"></a>Programmation fiable  
 Ce document utilise des fonctions COM standard pour montrer que vous pouvez utiliser la [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] pour créer un composant COM et le rendre disponible pour n'importe quelle technologie compatible COM. Vous pouvez également utiliser [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] types tels que [Microsoft::wrl :: comptr](../windows/comptr-class.md) dans votre application de bureau pour gérer la durée de vie de COM et d’autres objets. Le code suivant utilise la [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] pour gérer la durée de vie du pointeur `ICalculatorComponent`. La classe `CoInitializeWrapper` est un wrapper RAII qui garantit que la bibliothèque COM est libérée et également que la durée de vie de la bibliothèque COM est supérieure à celle de l'objet pointeur intelligent de `ComPtr`.  
  
 [!code-cpp[wrl-classic-com-component#7](../windows/codesnippet/CPP/how-to-create-a-classic-com-component-using-wrl_7.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Windows Runtime bibliothèque de modèles C++ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)