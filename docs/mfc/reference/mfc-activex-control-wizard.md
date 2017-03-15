---
title: "Assistant contrôle ActiveX MFC | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.ctl.overview
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], MFC
- MFC ActiveX controls [C++], wizards
- OLE controls [C++], creating
- MFC ActiveX Control Wizard
- OLE controls [C++]
ms.assetid: f19d698c-bdc3-4c74-af97-3d6ccb441b75
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 734c8dfdef42a0de614e02197d8cefdf4adc1bf1
ms.lasthandoff: 02/24/2017

---
# <a name="mfc-activex-control-wizard"></a>Contrôle ActiveX MFC (Assistant)
Un contrôle ActiveX est un type spécifique de [serveur automation](../../mfc/automation-servers.md); c’est un composant réutilisable. L’application qui héberge le contrôle ActiveX est la [client automation](../../mfc/automation-clients.md) de ce contrôle. Si votre objectif est de créer un composant réutilisable, puis utiliser cet Assistant pour créer votre contrôle. Consultez la page [contrôles ActiveX MFC](../../mfc/mfc-activex-controls.md) pour plus d’informations.  
  
 Vous pouvez également créer une automatisation serveur MFC application à l’aide de la [Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md).  
  
 Un contrôle ActiveX créé avec cet Assistant peut avoir une interface utilisateur, ou bien être invisible. Vous pouvez indiquer cette option dans le [paramètres de contrôle](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) page de l’Assistant. Un contrôle timer est un exemple d’un contrôle ActiveX que vous ne souhaitez pas invisible.  
  
 Contrôles ActiveX peuvent posséder une interface utilisateur complexe. Certains contrôles d’avoir un aperçu des formulaires encapsulés : un seul contrôle contenant de nombreux champs, chacun un contrôle Windows à part entière. Par exemple, un objet de parties automatique implémenté comme un contrôle ActiveX MFC peut présenter une interface utilisateur de type formulaire par le biais duquel les utilisateurs pourrait lire et modifier le nom de la partie, le numéro de référence et d’autres informations. Consultez la page [contrôles ActiveX MFC](../../mfc/mfc-activex-controls.md) pour plus d’informations.  
  
 Si vous avez besoin créer un conteneur pour vos objets ActiveX, consultez [créer un conteneur de contrôles ActiveX](../../mfc/reference/creating-an-mfc-activex-control-container.md).  
  
 Le programme de démarrage MFC inclut des fichiers sources (.cpp) C++, les fichiers de ressources (.rc) et un fichier projet (.vcxproj). Le code généré dans ces fichiers de démarrage est basé sur MFC.  
  
 L’exemple de liste suivante affiche les tâches et les types d’améliorations pour votre contrôle ActiveX :  
  
-   [Optimisation d’un contrôle ActiveX](../../mfc/mfc-activex-controls-optimization.md)  
  
-   [Ajout d’événements Stock à un contrôle ActiveX](../../mfc/mfc-activex-controls-adding-stock-events-to-an-activex-control.md)  
  
-   [Ajout d’événements personnalisés](../../mfc/mfc-activex-controls-adding-custom-events.md)  
  
-   [Ajout de méthodes Stock](../../mfc/mfc-activex-controls-adding-stock-methods.md)  
  
-   [Ajout de méthodes personnalisées](../../mfc/mfc-activex-controls-adding-custom-methods.md)  
  
-   [Ajout de propriétés Stock](../../mfc/mfc-activex-controls-adding-stock-properties.md)  
  
-   [Ajout de propriétés personnalisées](../../mfc/mfc-activex-controls-adding-custom-properties.md)  
  
-   [Programmation de contrôles ActiveX dans un conteneur de contrôles ActiveX](../../mfc/programming-activex-controls-in-a-activex-control-container.md)  
  
## <a name="overview"></a>Vue d'ensemble  
 Cette page décrit les paramètres d’application en cours pour le projet de contrôle ActiveX MFC que vous créez. Par défaut, l’Assistant crée un projet comme suit :  
  
-   Le projet par défaut ne génère aucun fichier de licence ou à l’aide du runtime. Vous pouvez modifier ces paramètres par défaut sur le [paramètres de l’Application](../../mfc/reference/application-settings-mfc-activex-control-wizard.md) page. Seules les sélections effectuées sur cette page de l’Assistant contrôle ActiveX sont répercutées le **présentation** page.  
  
-   Le projet inclut une classe de contrôle et une classe de page de propriétés, en fonction du nom du projet. Vous pouvez modifier les noms de votre projet et les fichiers associés sur le [des noms de contrôle](../../mfc/reference/control-names-mfc-activex-control-wizard.md) page.  
  
-   Le contrôle est basé sur aucun contrôle Windows existant, active lorsqu’il devienne visible, possède une interface utilisateur et inclut une **sur** boîte de dialogue. Vous pouvez modifier ces paramètres par défaut sur le [paramètres de contrôle](../../mfc/reference/control-settings-mfc-activex-control-wizard.md) page.  
  
## <a name="see-also"></a>Voir aussi  
 [Création et gestion de projets Visual C++](../../ide/creating-and-managing-visual-cpp-projects.md)   
 [Types de projets Visual C++](../../ide/visual-cpp-project-types.md)   
 [Concepts](../../atl/active-template-library-atl-concepts.md)


