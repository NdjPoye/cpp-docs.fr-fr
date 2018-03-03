---
title: "Modèle de projet de bibliothèque de classes WRL | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 628b0852-89e5-44f8-bf58-a09762bda15c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 13fc476f696bdd2cb17ed58c496c63747db90322
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="wrl-class-library-project-template"></a>Modèle de projet de bibliothèque de classes WRL
Si vous utilisez Visual Studio pour écrire un projet de bibliothèque de modèles Windows Runtime C++ (WRL), vous pouvez simplifier considérablement votre tâche en téléchargeant le modèle de projet WRL Class Library.  
  
> [!NOTE]
>  Si vous devez mettre à jour manuellement les paramètres du projet pour un projet existant, consultez [DLL (C + c++ / CX)](http://msdn.microsoft.com/library/windows/apps/hh699881\(v=vs.110\).aspx).  
  
## <a name="download-the-wrl-project-template"></a>Téléchargez le modèle de projet WRL  
 Visual Studio ne fournit pas un modèle pour les projets de bibliothèque de modèles Windows Runtime C++. Voici comment télécharger un modèle de projet qui crée une bibliothèque de classes de base pour les applications de plateforme Windows universelle avec la bibliothèque de modèles Windows Runtime C++.  
  
#### <a name="to-download-the-wrl-project-template"></a>Pour télécharger le modèle de projet WRL  
  
1.  Dans la barre de menus, choisissez **fichier**, **nouveau projet**.  
  
2.  Dans le volet gauche de la **nouveau projet** boîte de dialogue, sélectionnez **Online**, puis sélectionnez **modèles**.  
  
3.  Dans le **recherche des modèles en ligne** zone dans le coin supérieur droit, type `WRL Class Library`. Lorsque le modèle s’affiche dans les résultats de recherche, sélectionnez le **OK** bouton.  
  
4.  Dans le **Téléchargez et installez** termes de la boîte de dialogue, si vous acceptez la licence, choisissez le **installer** bouton.  
  
5.  Une fois le modèle est installé, créez un projet en choisissant **fichier**, **nouveau projet**, puis en sélectionnant la `WRLClassLibrary` modèle. Le projet crée une DLL.  
  
## <a name="examples-that-use-the-project-template"></a>Exemples qui utilisent le modèle de projet  
 Lecture [procédure pas à pas : création d’un composant Windows Runtime base](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md) pour obtenir un exemple qui utilise ce modèle pour créer un composant Windows Runtime.  
  
## <a name="what-the-project-template-provides"></a>Ce que fournit le modèle de projet  
 Le modèle de projet fournit :  
  
-   un fichier .idl qui déclare les attributs MIDL pour une interface de base de son implémentation de la classe. Voici un exemple :  
  
     [!code-cpp[wrl-project-template#1](../windows/codesnippet/CPP/wrl-class-library-project-template_1.idl)]  
  
-   un fichier .cpp qui définit l’implémentation de classe. Voici un exemple :  
  
     [!code-cpp[wrl-project-template#2](../windows/codesnippet/CPP/wrl-class-library-project-template_2.cpp)]  
  
     Le [RuntimeClass](../windows/runtimeclass-class.md) vous permet de gérer la référence globale de tous les objets dans le module de classe de base et déclare les méthodes de la [IUnknown](http://msdn.microsoft.com/en-us/33f1d79a-33fc-4ce5-a372-e08bda378332) et [IInspectable](http://msdn.microsoft.com/en-us/0657e51f-d4c0-46c6-927d-b01e54b6846c) interfaces. Le [InspectableClass](../windows/inspectableclass-macro.md) macro implémente `IUnknown` et `IInspectable`. Le [ActivatableClass](../windows/activatableclass-macros.md) macro crée une fabrique de classe qui crée des instances de la classe.  
  
-   un fichier nommé module.cpp qui définit la bibliothèque exporte `DllMain`, `DllCanUnloadNow`, `DllGetActivationFactory`, et `DllGetClassObject`.  
  
## <a name="see-also"></a>Voir aussi  
 [Bibliothèque de modèles Windows Runtime C++ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)