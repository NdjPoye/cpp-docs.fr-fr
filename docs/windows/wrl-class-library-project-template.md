---
title: "Mod&#232;le de projet de biblioth&#232;que de classes WRL | Microsoft Docs"
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
ms.assetid: 628b0852-89e5-44f8-bf58-a09762bda15c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Mod&#232;le de projet de biblioth&#232;que de classes WRL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si vous utilisez Visual Studio pour écrire un projet [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\), vous pouvez simplifier considérablement votre tâche en téléchargeant le modèle de projet Bibliothèque de classes WRL.  
  
> [!NOTE]
>  Si vous devez mettre à jour manuellement les paramètres d'un projet existant, consultez [DLL \(C\+\+\/CX\)](http://msdn.microsoft.com/library/windows/apps/hh699881\(v=vs.110\).aspx).  
  
## Téléchargez le modèle de projet WRL.  
 Visual Studio ne fournit pas de modèle pour les projets [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)].  Voici comment télécharger un modèle de projet qui crée une bibliothèque de classes de base pour les applications [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] avec [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)].  
  
#### Pour télécharger le modèle de projet WRL.  
  
1.  Dans la barre de menus, choisissez **Fichier**, **Nouveau projet**.  
  
2.  Dans le volet gauche de la boîte de dialogue **Nouveau projet**, sélectionnez **En ligne**, puis **Modèles**.  
  
3.  Dans la zone **Recherche de modèles en ligne** dans l'angle supérieur droit, tapez `Bibliothèque de classe WRL`.  Lorsque le modèle s'affiche dans les résultats de la recherche, cliquez le bouton **OK**.  
  
4.  Dans la boîte de dialogue **Télécharger et installer**, si vous êtes d'accord avec les termes de licence, cliquez le bouton **Installer**.  
  
5.  Une fois que le modèle est installé, créez un projet en sélectionnant **Fichier**, **Nouveau projet**, puis en sélectionnant le modèle `WRLClassLibrary`.  Le projet crée une DLL.  
  
## Exemples qui utilisent le modèle de projet  
 Lisez [Procédure pas à pas : création d'un composant Windows Runtime de base](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md) pour obtenir un exemple utilisant ce modèle pour créer un composant de [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
## Ce que le modèle de projet fournit  
 Le modèle du projet fournit:  
  
-   un fichier .idl indique les attributs MIDL d'une interface de base de son implémentation de la classe.  Voici un exemple :  
  
     [!code-cpp[wrl-project-template#1](../windows/codesnippet/CPP/wrl-class-library-project-template_1.idl)]  
  
-   un fichier .cpp qui définit l'implémentation de la classe.  Voici un exemple :  
  
     [!code-cpp[wrl-project-template#2](../windows/codesnippet/CPP/wrl-class-library-project-template_2.cpp)]  
  
     La classe de base[RuntimeClass](../windows/runtimeclass-class.md) vous aide à gérer la référence globale de tous les objets du module et déclare les méthodes des interfaces[IUnknown](http://msdn.microsoft.com/fr-fr/33f1d79a-33fc-4ce5-a372-e08bda378332) et d'[IInspectable](http://msdn.microsoft.com/fr-fr/0657e51f-d4c0-46c6-927d-b01e54b6846c).  La macro [InspectableClass](../windows/inspectableclass-macro.md) implémente `IUnknown` et `IInspectable`.  La macro [ActivatableClass](../windows/activatableclass-macros.md) crée une classe de fabrique qui crée les instances de la classe.  
  
-   un fichier nommé module.cpp qui définit les exportations de bibliothèque `DllMain`, `DllCanUnloadNow`, `DllGetActivationFactory`, et `DllGetClassObject`.  
  
## Voir aussi  
 [Bibliothèque de modèles Windows Runtime C\+\+ \(WRL\)](../windows/windows-runtime-cpp-template-library-wrl.md)