---
title: "Création d’une Interface COM (Visual C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.com.creating.interfaces
dev_langs: C++
helpviewer_keywords: COM interfaces, creating
ms.assetid: 1be84d3c-6886-4d1e-8493-56c4d38a96d4
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e7b5820686c3e6f01c37cbf527d0e631e5bcc25c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-a-com-interface-visual-c"></a>Création d'une interface COM (Visual C++)
Visual C++ fournit des Assistants et des modèles pour créer des projets qui utilisent des interfaces de définition COM et des dispinterfaces pour vos objets COM et les classes automation.  
  
 Vous pouvez utiliser ces Assistants pour effectuer les trois tâches courantes suivantes :  
  
-   [Ajout de la prise en charge ATL à votre projet MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md)  
  
     Ajouter la prise en charge ATL à une application MFC après avoir créé un projet MFC à l’aide du [Assistant Application MFC](../mfc/reference/mfc-application-wizard.md) , puis en exécutant la **ajouter la prise en charge ATL aux MFC** Assistant code. Cette prise en charge s’applique uniquement aux objets simples COM ajoutés à un projet DLL ou un exécutable MFC. Ces objets ATL peuvent posséder plusieurs interfaces.  
  
-   [Création d’un contrôle ActiveX MFC](../mfc/reference/creating-an-mfc-activex-control.md)  
  
     Ouvrez le [Assistant contrôle ActiveX MFC](../mfc/reference/mfc-activex-control-wizard.md) pour créer un contrôle ActiveX possédant une dispinterface et une table d’événements définies dans le fichier .idl et la classe du contrôle, respectivement.  
  
-   [Ajout d’un contrôle ATL](../atl/reference/adding-an-atl-control.md)  
  
     Utiliser une combinaison de la [Assistant Projet ATL](../atl/reference/atl-project-wizard.md) et [Assistant contrôle ATL](../atl/reference/atl-control-wizard.md) pour créer un contrôle ActiveX ATL.  
  
     Vous pouvez également ajouter un contrôle ATL à un projet MFC auquel vous avez ajouté la prise en charge ATL, comme décrit ci-dessus. En outre, si vous sélectionnez **contrôle ATL** dans les **ajouter une classe** boîte de dialogue et que vous n'avez pas encore ajouté prise en charge ATL à votre projet MFC, Visual Studio affiche une boîte de dialogue confirmant l’ajout de la prise en charge ATL à votre Projet MFC.  
  
     Cet Assistant génère source IDL et une table COM dans les classes du projet.  
  
 Une fois que vous avez un projet ATL ouvrir, le [ajouter une classe](../ide/add-class-dialog-box.md) boîte de dialogue vous donne la possibilité d’Assistants et modèles supplémentaires pour ajouter des interfaces COM à votre projet. Les Assistants suivants vous permettent d’établir une ou plusieurs interfaces de l’objet :  
  
-   [Assistant Composant COM+ 1.0 ATL](../atl/reference/atl-com-plus-1-0-component-wizard.md)  
  
-   [Assistant Objet simple ATL](../atl/reference/atl-simple-object-wizard.md)  
  
-   [Assistant Composant ASP ATL](../atl/reference/atl-active-server-page-component-wizard.md)  
  
-   [Assistant Contrôle ATL](../atl/reference/atl-control-wizard.md)  
  
 En outre, vous pouvez implémenter de nouvelles interfaces sur votre contrôle COM en cliquant sur la classe du contrôle de l’objet dans l’affichage de classes en cliquant sur [implémenter l’Interface](../ide/implement-interface-wizard.md).  
  
> [!NOTE]
>  Visual Studio ne fournit pas un Assistant permettant d’ajouter une interface à un projet. Vous pouvez ajouter une interface à un projet ATL ou à un [ajoutant la prise en charge ATL à votre projet MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md) en ajoutant un objet simple à l’aide de la [Assistant objet Simple ATL](../atl/reference/atl-simple-object-wizard.md). Vous pouvez également ouvrir le fichier du projet .idl et créer l’interface en tapant :  
  
```  
interface IMyInterface {  
};  
  
```  
  
 Consultez [implémentant une Interface](../ide/implementing-an-interface-visual-cpp.md) et [Ajout d’objets et des contrôles à un projet ATL](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) pour plus d’informations.  
  
 Visual C++ propose plusieurs moyens de consulter et [modifier les interfaces COM](../ide/editing-a-com-interface.md) définies pour vos projets. [Affichage de classes](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925) affiche des icônes pour les interfaces ou une dispinterface définie dans un fichier .idl de votre projet C++.  
  
 Pour les classes d’objets COM fondés sur ATL, affichage de classes lit la table COM dans la classe ATL pour afficher la relation entre la classe ATL et les interfaces qu’il implémente.  
  
 Dans l’affichage de classes et ses menus contextuels, vous pouvez travailler avec des interfaces comme suit :  
  
-   Ajouter des objets ATL à une application MFC.  
  
-   Ajoutez les méthodes, propriétés et événements.  
  
-   Accéder directement au code de l’interface d’un élément en double-cliquant sur l’élément.  
  
## <a name="see-also"></a>Voir aussi  
 [Création de projets du Bureau à l’aide des Assistants Application](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Ajout de fonctionnalités à l’aide des Assistants Code](../ide/adding-functionality-with-code-wizards-cpp.md)