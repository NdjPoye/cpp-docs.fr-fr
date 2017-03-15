---
title: "Comment&#160;: impl&#233;menter le suivi dans votre code | Microsoft Docs"
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
  - "CRectTracker (classe), implémenter des dispositifs de suivi"
ms.assetid: baaeca2c-5114-485f-bf58-8807db1bc973
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Comment&#160;: impl&#233;menter le suivi dans votre code
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour suivre un élément OLE, vous devez gérer certains événements associés à l'élément, tel que cliquer sur l'élément ou mettre à jour la vue du document.  Dans tous les cas, il suffit de déclarer un objet temporaire de [CRectTracker](../mfc/reference/crecttracker-class.md) et de manipuler l'élément au moyen de cet objet.  
  
 Lorsqu'un utilisateur sélectionne un élément ou insère un objet avec une commande de menu, vous devez initialiser le mécanisme de suivi avec les styles appropriés pour représenter l'état de l'élément OLE.  Le tableau suivant présente les conventions utilisées par l'exemple OCLIENT.  Pour plus d'informations sur ces styles, consultez `CRectTracker`.  
  
### Styles de conteneur et états de l'élément OLE.  
  
|Style d'affichage|État de l'élément OLE|  
|-----------------------|---------------------------|  
|Bordure en pointillés|L'élément est lié|  
|Bordure pleine|L'élément est incorporé dans le document|  
|Poignées de redimensionnement|L'élément est actuellement sélectionné.|  
|Bordure hachée|L'élément est actuellement actif en place|  
|Le modèle de hachurage recouvre l'élément|Le serveur de l'élément est ouvert|  
  
 Vous pouvez traiter cette initialisation facilement à l'aide d'une procédure qui vérifie l'état de l'élément OLE et qui définit les styles appropriés.  La fonction de **SetupTracker** trouvée dans l'exemple de OCLIENT illustre l'initialisation de suivi.  Les paramètres de cette fonction sont l'adresse du dispositif de suivi, *pTracker*; un pointeur vers l'élément client qui est associée au mécanisme de suivi, `pItem`; et un pointeur vers un rectangle, *pTrueRect*.  Pour un exemple plus compet illustrant cette fonctionnalité, consultez l'exemple de liaison et incorporation d'objets MFC [OCLIENT](../top/visual-cpp-samples.md).  
  
 L'exemple de code de **SetupTracker** présente une seule fonction ; les lignes de la fonction sont mélangées à l'explication des fonctionnalités de la fonction :  
  
 [!code-cpp[NVC_MFCOClient#1](../mfc/codesnippet/CPP/how-to-implement-tracking-in-your-code_1.cpp)]  
  
 Le dispositif de suivi est initialisé en définissant la taille minimale et en effaçant le style du dispositif de suivi.  
  
 [!code-cpp[NVC_MFCOClient#2](../mfc/codesnippet/CPP/how-to-implement-tracking-in-your-code_2.cpp)]  
  
 Les lignes suivantes permettent de voir si l'élément est sélectionné et si l'élément est lié au document ou incorporé dans celle\-ci.  Des poignées de redimensionnement placées à l'intérieur de la bordure sont ajoutées au style, ce qui indique que l'élément est sélectionné.  Si l'élément est lié à votre document, le style de bordure en pointillés est utilisé.  Une bordure pleine est utilisée si l'élément est incorporé.  
  
 [!code-cpp[NVC_MFCOClient#3](../mfc/codesnippet/CPP/how-to-implement-tracking-in-your-code_3.cpp)]  
  
 Le code suivant recouvre l'élément avec un modèle haché si l'élément est ouvert.  
  
 [!code-cpp[NVC_MFCOClient#4](../mfc/codesnippet/CPP/how-to-implement-tracking-in-your-code_4.cpp)]  
  
 Vous pouvez ensuite appeler cette fonction lorsque le mécanisme de suivi doit être affiché.  Par exemple, appeler cette fonction depuis la fonction `OnDraw` de la classe d'affichage.  Cela met à jour l'apparence du dispositif de suivi lorsque la vue est redessinée.  Pour obtenir un exemple complet, consultez la fonction **CMainView::OnDraw** de l'exemple de MFC OLE [OCLIENT](../top/visual-cpp-samples.md).  
  
 Dans votre application, les événements qui requièrent un code de suivi, tel que le redimensionnement, le déplacement, ou la détection d'accès, se produisent.  Ces actions indiquent généralement qu'une tentative a lieu pour attraper ou déplacer l'élément.  Dans ce cas, vous devez déterminer ce qui a été saisi : une poignée de redimensionnement ou une partie de la bordure entre les poignées de redimensionnement.  Le gestionnaire de messages `OnLButtonDown` est un bon endroit pour tester la position de la souris par rapport à l'élément.  Effectuez un appel à `CRectTracker::HitTest`.  Si le test retourne un problème outre **CRectTracker::hitOutside**, l'élément est en train d'être redimensionné ou déplacé.  Par conséquent, vous devez effectuer un appel à la fonction membre `Track`.  Consultez la fonction **CMainView::OnLButtonDown** qui se trouve dans l'exemple de liaison et incorporation d'objets MFC [OCLIENT](../top/visual-cpp-samples.md) pour obtenir un exemple complet.  
  
 La classe `CRectTracker` fournit différentes formes de curseur utilisés pour indiquer si un déplacement, un redimensionnement, ou un glissement a lieu.  Pour gérer l'événement, activez la case à cocher pour déterminer si l'élément actuellement sous la souris est sélectionné.  Si tel est le cas, effectuez un appel à `CRectTracker::SetCursor`, ou appelez le gestionnaire par défaut.  L'exemple suivant provient de l'exemple de liaison et incorporation d'objets MFC [OCLIENT](../top/visual-cpp-samples.md):  
  
 [!code-cpp[NVC_MFCOClient#5](../mfc/codesnippet/CPP/how-to-implement-tracking-in-your-code_5.cpp)]  
  
## Voir aussi  
 [Dispositifs de suivi : implémentation de dispositifs de suivi dans votre application OLE](../mfc/trackers-implementing-trackers-in-your-ole-application.md)