---
title: "Modification d&#39;une interface COM | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.com.editing.interfaces"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interfaces COM, modifier"
  - "méthodes (C++), ajouter aux interfaces COM"
  - "propriétés (C++), ajouter aux interfaces COM"
ms.assetid: 6c2909e0-af2d-4a37-bb39-ed372e6129cf
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Modification d&#39;une interface COM
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

À l'aide des commandes du menu contextuel de l'Affichage de classes, vous pouvez définir de nouvelles méthodes et propriétés pour les interfaces COM de vos projets Visual C\+\+.  En outre, à partir de la boîte à outils, vous pouvez définir des événements pour des contrôles ActiveX.  
  
 En ce qui concerne les classes d'objets COM fondés sur ATL et sur MFC, vous pouvez modifier l'implémentation des classes au moment où vous modifiez l'interface.  
  
> [!NOTE]
>  Pour les interfaces que vous avez définies à l'extérieur de la boîte de dialogue **Ajouter une classe**, Visual C\+\+ ajoute les méthodes et propriétés au fichier .idl, et ajoute des stubs aux classes implémentant les méthodes, même si les interfaces sont ajoutées manuellement.  
  
 Les trois Assistants suivants vous aident à personnaliser les interfaces existantes.  Ils sont accessibles à partir de l'Affichage de classes :  
  
|Assistant|Type de projet|  
|---------------|--------------------|  
|[Assistant Ajout de propriété](../ide/names-add-property-wizard.md)|Projets ATL ou MFC prenant en charge ATL.  Cliquez avec le bouton droit sur l'interface à laquelle vous souhaitez ajouter la propriété.<br /><br /> Visual C\+\+ détecte le type de projet et modifie en conséquence les options de l'Assistant Ajout de propriété :<br /><br /> -   Pour les dispinterfaces de projets créés à l'aide de l'[Assistant Application MFC](../mfc/reference/mfc-application-wizard.md), l'appel de l'Assistant Ajout de propriété propose des options propres à MFC.<br />-   Pour les interfaces de contrôles ActiveX MFC, l'Assistant Ajout de propriété propose une liste de méthodes et de propriétés stock que vous pouvez personnaliser ou utiliser telles quelles pour votre contrôle.<br />-   Pour toutes les autres interfaces, l'Assistant Ajout de propriété propose des options utiles dans la plupart des situations.|  
|[Assistant Ajout de méthode](../ide/add-method-wizard.md)|Projets ATL ou MFC prenant en charge ATL.  Cliquez avec le bouton droit sur l'interface à laquelle vous souhaitez ajouter la méthode.<br /><br /> Visual C\+\+ détecte le type de projet et modifie en conséquence les options de l'Assistant Ajout de méthode :<br /><br /> -   Pour les dispinterfaces de projets créés à l'aide de l'[Assistant Application MFC](../mfc/reference/mfc-application-wizard.md), l'appel de l'Assistant Ajout de méthode propose des options propres à MFC.<br />-   Pour les interfaces de contrôles ActiveX MFC, l'Assistant Ajout de méthode propose une liste de méthodes et de propriétés stock que vous pouvez personnaliser ou utiliser telles quelles pour votre contrôle.<br />-   Pour toutes les autres interfaces, les Assistants **Ajout de méthode** proposent des options utiles dans la plupart des situations.|  
  
 Vous pouvez également implémenter de nouvelles interfaces sur votre contrôle COM en cliquant avec le bouton droit sur la classe de contrôle de l'objet dans l'Affichage de classes et en cliquant sur [Implémenter l'interface](../ide/implement-interface-wizard.md).  
  
## Voir aussi  
 [Working with Resource Files](../mfc/working-with-resource-files.md)   
 [Ajout de fonctionnalités à l'aide des Assistants Code](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Types de projets Visual C\+\+](../ide/visual-cpp-project-types.md)