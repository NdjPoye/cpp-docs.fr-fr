---
title: "Prise en charge de l&#39;interaction souris pendant l&#39;inactivit&#233; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles ActiveX MFC, interaction souris"
ms.assetid: b09106bf-44c7-4b9b-a6d9-0d624f16f5b3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Prise en charge de l&#39;interaction souris pendant l&#39;inactivit&#233;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si votre contrôle n'est pas immédiatement activé, il est possible que vous vouliez qu'il traite des messages `WM_SETCURSOR` et `WM_MOUSEMOVE`, même si le contrôle n'a pas de fenêtre propre.  Cela peut être accompli en activant l'implémentation `COleControl` de l'interface `IPointerInactive`, qui est désactivée par défaut. \(Voir *ActiveX Kit de développement logiciel \(SDK\)* pour une description de cette interface.\) Pour l'activer, incluez la balise`pointerInactive` dans l'ensemble de balises retournées par [COleControl::GetControlFlags](../Topic/COleControl::GetControlFlags.md):  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/CPP/providing-mouse-interaction-while-inactive_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#10](../mfc/codesnippet/CPP/providing-mouse-interaction-while-inactive_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/CPP/providing-mouse-interaction-while-inactive_3.cpp)]  
  
 Le code pour inclure cette balise est automatiquement généré si vous sélectionnez l'option **Notifications du pointeur de la souris pendant l'inactivité** dans la page [Paramètres du contrôle](../mfc/reference/control-settings-mfc-activex-control-wizard.md) quand vous creéz votre contrôle avec **Assistant Contrôle ActiveX MFC**.  
  
 Lorsque l'interface `IPointerInactive` est activée, le conteneur lui délègue les messages `WM_SETCURSOR` et  `WM_MOUSEMOVE`.  L'implémentation de `COleControl` de `IPointerInactive` répartit les messages via la table des messages de votre contrôle, après avoir ajusté les coordonnées de la souris correctement.  Vous pouvez traiter les messages comme des messages ordinaires de fenêtre, en ajoutant des entrées correspondantes dans la table des messages.  Dans les gestionnaires de ces messages, évitez d'utiliser la variable membre `m_hWnd` \(ou une fonction membre qui utilise\) sans vérifier d'abord que la valeur n'est pas **NULL**.  
  
 Il est possible que vous vouliez aussi qu'un contrôle inactif à être la cible d'une opération de glisser\-déplacer OLE.  Cela nécessite l'activation du contrôle au moment où l'utilisateur fait glisser un objet dessus, de sorte que la fenêtre de contrôle peut être inscrite en tant que cible de suppression.  Pour déclencher l'activation pendant un glisser\-déplacer, substituez [COleControl::GetActivationPolicy](../Topic/COleControl::GetActivationPolicy.md), et retournez la balise **POINTERINACTIVE\_ACTIVATEONDRAG** :  
  
 [!code-cpp[NVC_MFC_AxOpt#11](../mfc/codesnippet/CPP/providing-mouse-interaction-while-inactive_4.cpp)]  
  
 Activer l'interface `IPointerInactive` signifie généralement que le contrôle soit capable de traiter les messages de la souris à tout moment.  Pour obtenir ce résultat dans un conteneur qui ne prend pas en charge l'interface `IPointerInactive`, votre contrôle doit être toujours activé quand il est visible, ce qui signifie que le contrôle doit inclure la balise **OLEMISC\_ACTIVATEWHENVISIBLE** parmi ses diverses balises.  Toutefois, pour éviter que cette balise prenne effet dans un conteneur qui prend en charge `IPointerInactive`, vous pouvez également spécifier la balise **OLEMISC\_IGNOREACTIVATEWHENVISIBLE** :  
  
 [!code-cpp[NVC_MFC_AxOpt#12](../mfc/codesnippet/CPP/providing-mouse-interaction-while-inactive_5.cpp)]  
  
## Voir aussi  
 [Contrôles ActiveX MFC : optimisation](../mfc/mfc-activex-controls-optimization.md)