---
title: "Modification d’une Interface COM | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.com.editing.interfaces
dev_langs: C++
helpviewer_keywords:
- methods [C++], adding to COM interfaces
- COM interfaces, editing
- properties [C++], adding to COM interfaces
ms.assetid: 6c2909e0-af2d-4a37-bb39-ed372e6129cf
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b8911f23ce8e28f2da13c3d8305f4f13a861bb60
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="editing-a-com-interface"></a>Modification d'une interface COM
À l’aide de commandes dans le menu Affichage de classes, vous pouvez définir les nouvelles méthodes et propriétés pour les interfaces COM dans vos projets Visual C++. En outre, à partir de la boîte à outils, vous pouvez définir des événements pour les contrôles ActiveX.  
  
 Pour les classes d’objet ATL et MFC basés sur COM, vous pouvez modifier l’implémentation de classe en même temps que vous modifiez l’interface.  
  
> [!NOTE]
>  Pour les interfaces que vous avez définis en dehors de la **ajouter une classe** boîte de dialogue, Visual C++ ajoute des méthodes ou propriétés au fichier .idl, et ajoute des stubs pour les classes qui implémentent les méthodes, même si les interfaces sont ajoutées manuellement.  
  
 Les trois Assistants suivants vous aider à personnaliser les interfaces existantes. Ils sont disponibles à partir de l’affichage de classes :  
  
|Assistant|Type de projet|  
|------------|------------------|  
|[Assistant Ajout de propriété](../ide/names-add-property-wizard.md)|Projets ATL ou MFC prenant en charge ATL. Cliquez sur l’interface à laquelle vous souhaitez ajouter la propriété.<br /><br /> Visual C++ détecte le type de projet et modifie en conséquence les options de l’Assistant Ajout de propriété :<br /><br /> -Pour les dispinterfaces de projets créés à l’aide de la [Assistant Application MFC](../mfc/reference/mfc-application-wizard.md), l’appel de l’Assistant Ajout de propriété propose des options spécifiques à MFC.<br />-Pour les interfaces de contrôle ActiveX MFC, l’Assistant Ajout de propriété fournit une liste de méthodes stock et les propriétés que vous pouvez utiliser telle quelle ou personnaliser pour votre contrôle.<br />-Pour toutes les autres interfaces, l’Assistant Ajout de propriété proposent des options utiles dans la plupart des situations.|  
|[Assistant Ajout de méthode](../ide/add-method-wizard.md)|Projets ATL ou MFC prenant en charge ATL. Cliquez sur l’interface à laquelle vous souhaitez ajouter la méthode.<br /><br /> Visual C++ détecte le type de projet et modifie en conséquence les options de l’Assistant Ajout de méthode :<br /><br /> -Pour les dispinterfaces de projets créés à l’aide de la [Assistant Application MFC](../mfc/reference/mfc-application-wizard.md), l’appel de l’Assistant Ajout de méthode propose des options spécifiques à MFC.<br />-Pour les interfaces de contrôle ActiveX MFC, l’Assistant Ajout de méthode fournit une liste de méthodes stock et les propriétés que vous pouvez utiliser telle quelle ou personnaliser pour votre contrôle.<br />-Pour toutes les autres interfaces, les **ajouter une méthode** Assistants proposent des options utiles dans la plupart des situations.|  
  
 En outre, vous pouvez implémenter de nouvelles interfaces sur votre contrôle COM en cliquant sur la classe du contrôle de l’objet dans l’affichage de classes en cliquant sur [implémenter l’Interface](../ide/implement-interface-wizard.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation des fichiers de ressources](../windows/working-with-resource-files.md)   
 [Ajout de fonctionnalités à l’aide des Assistants Code](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Types de projets Visual C++](../ide/visual-cpp-project-types.md)