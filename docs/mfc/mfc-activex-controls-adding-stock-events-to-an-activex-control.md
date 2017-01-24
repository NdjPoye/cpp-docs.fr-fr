---
title: "Contr&#244;les ActiveX MFC&#160;: ajout d&#39;&#233;v&#233;nements stock &#224; un contr&#244;le ActiveX | Microsoft Docs"
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
  - "EVENT__STOCK_ERROR"
  - "EVENT__STOCK_READYSTATECHANGE"
  - "ReadyStateChange"
  - "EVENT__STOCK_MOUSEMOVE"
  - "EVENT__STOCK_MOUSEUP"
  - "EVENT__STOCK_DBLCLICK"
  - "KeyPress"
  - "EVENT__STOCK_KEYDOWN"
  - "EVENT__STOCK"
  - "EVENT__STOCK_MOUSEDOWN"
  - "EVENT__STOCK_KEYPRESS"
  - "EVENT__STOCK_CLICK"
  - "EVENT__STOCK_KEYUP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EVENT_STOCK (préfixe)"
  - "EVENT_STOCK_CLICK (événement)"
  - "EVENT_STOCK_DBLCLICK (événement)"
  - "EVENT_STOCK_ERROREVENT (événement)"
  - "EVENT_STOCK_KEYDOWN (événement)"
  - "EVENT_STOCK_KEYPRESS (événement)"
  - "EVENT_STOCK_KEYPRESS (macro)"
  - "EVENT_STOCK_KEYUP (événement)"
  - "EVENT_STOCK_MOUSEDOWN (événement)"
  - "EVENT_STOCK_MOUSEMOVE (événement)"
  - "EVENT_STOCK_MOUSEUP (événement)"
  - "EVENT_STOCK_READYSTATECHANGE (événement)"
  - "événements (C++), stock"
  - "FireClick (événement)"
  - "FireDblClick (événement)"
  - "FireError (événement)"
  - "FireKeyDown (événement)"
  - "FireKeyPress (événement)"
  - "FireKeyUp (événement)"
  - "FireMouseDown (événement)"
  - "FireMouseMove (événement)"
  - "FireMouseUp (événement)"
  - "KeyPress (événement)"
  - "contrôles ActiveX MFC, événements"
  - "ReadyStateChange (événement)"
ms.assetid: 3eeadc67-4b3d-4444-8caa-53054073988a
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX MFC&#160;: ajout d&#39;&#233;v&#233;nements stock &#224; un contr&#244;le ActiveX
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les événements standard sont différents des événements personnalisés du fait qu'ils ne sont pas automatiquement générés par la classe [](../mfc/reference/colecontrol-class.md "COleControl Class").  `COleControl` contient les méthodes prédéfinies qui déclenchent des événements provenant d'actions courantes.  Certaines actions courantes implémentées par `COleControl` incluent les clics simples et doubles sur le contrôle, les événements du clavier, et les modifications de l'état des boutons de la souris.  Les entrées de table pour les événements standard sont toujours précédés par le préfixe **EVENT\_STOCK**.  
  
##  <a name="_core_stock_events_supported_by_classwizard"></a> Événements standard pris en charge par l'Assistant Ajout d'événement  
 La classe `COleControl` propose dix événements standard, répertoriés dans le tableau suivant.  Vous pouvez spécifier les événements que vous souhaitez dans votre contrôle à l'aide de l'[Assistant Ajout d'événement](../ide/add-event-wizard.md).  
  
### Evénements standard  
  
|Événement|Fonction de génération|Commentaires|  
|---------------|----------------------------|------------------|  
|Cliquez sur|**void FireClick\( \)**|Déclenché lorsque le contrôle capture la souris, un message **BUTTONUP** \(gauche, milieu ou droite\) est reçu, et le bouton est libéré sur le contrôle.  Les événements standard MouseDown et MouseUp se produisent avant cet événement.<br /><br /> Entrée de table d'événement : **EVENT\_STOCK\_CLICK\( \)**|  
|DblClick|**void FireDblClick\( \)**|Semblable au clic mais déclenché lorsqu'un message **BUTTONDBLCLK** est reçu.<br /><br /> Entrée de table d'événement : **EVENT\_STOCK\_DBLCLICK\( \)**|  
|Erreur|**void FireError\( SCODE**  *scode* **, LPCSTR**  `lpszDescription` **, UINT**  `nHelpID`  **\= 0 \)**|Déclenché lorsqu'une erreur se produit dans le contrôle ActiveX en dehors de l'étendue d'un appel de méthode ou d'une recherche de propriété.<br /><br /> Entrée de table d'événement : **EVENT\_STOCK\_ERROREVENT\( \)**|  
|KeyDown|**void FireKeyDown\( short**  `nChar` **, short**  `nShiftState`  **\)**|Déclenché lorsqu'un message `WM_SYSKEYDOWN` ou `WM_KEYDOWN` est reçu.<br /><br /> Entrée de table d'événement : **EVENT\_STOCK\_KEYDOWN\( \)**|  
|KeyPress|**void FireKeyPress\( short\***  `pnChar`  **\)**|Déclenché lorsqu'un message `WM_CHAR` est reçu.<br /><br /> Entrée de table d'événement : **EVENT\_STOCK\_KEYPRESS\( \)**|  
|KeyUp|**void FireKeyUp\( short**  `nChar` **, short**  `nShiftState`  **\)**|Déclenché lorsqu'un message `WM_SYSKEYUP` ou `WM_KEYUP` est reçu.<br /><br /> Entrée de table d'événement : **EVENT\_STOCK\_KEYUP\( \)**|  
|MouseDown|**void FireMouseDown\( short**  `nButton` **, short**  `nShiftState` **, float**  *X* **, float**  *y*  **\)**|Déclenché si tout **BUTTONDOWN** \(gauche, milieu, ou droite\) est reçu.  La souris est capturée immédiatement avant que cet événement soit déclenché.<br /><br /> Entrée de table d'événement : **EVENT\_STOCK\_MOUSEDOWN\( \)**|  
|MouseMove|**void FireMouseMove\( short**  `nButton` **, short**  `nShiftState` **, float**  *X* **, float**  *y*  **\)**|Déclenché lorsqu'un message `WM_MOUSEMOVE` est reçu.<br /><br /> Entrée de table d'événement : **EVENT\_STOCK\_MOUSEMOVE\( \)**|  
|MouseUp|**void FireMouseUp\( short**  `nButton` **, short**  `nShiftState` **, float**  *X* **, float**  *y*  **\)**|Déclenché si tout **BUTTONUP** \(gauche, milieu, ou droite\) est reçu.  La capture de la souris est libérée avant que cet événement soit déclenché.<br /><br /> Entrée de table d'événement : **EVENT\_STOCK\_MOUSEUP\( \)**|  
|ReadyStateChange|**void FireReadyStateChange\( \)**|Déclenché lorsqu'un contrôle passe à l'état prêt suivant en raison de la quantité de données reçues.<br /><br /> Entrée de table d'événement : **EVENT\_STOCK\_READYSTATECHANGE\( \)**|  
  
##  <a name="_core_adding_a_stock_event_using_classwizard"></a> Ajouter un événement standard à l'aide de l'assistant d'ajout d'événement  
 L'ajout d'événements standard requiert moins de travail que l'ajout d'évènements utilisateurs car le déclenchement de l'événement lui\-même est géré automatiquement par la classe de base, `COleControl`.  La procédure suivante ajoute un événement standard à un contrôle qui a été développé à l'aide de [Assistant Contrôle ActiveX MFC](../mfc/reference/mfc-activex-control-wizard.md).  L'événement, appelé KeyPress, se déclenche lorsqu'une touche est pressé et le contrôle est actif.  Vous pouvez également l'utiliser pour ajouter d'autres événements standard.  Remplacez le nom d'événement standard sélectionné par KeyPress.  
  
#### Pour ajouter l'évènement standard KeyPress à l'aide de l'assistant d'ajout d'événement  
  
1.  Chargez votre projet de contrôle.  
  
2.  Sous Affichage de classes, cliquez avec le bouton droit sur votre classe de contrôle ActiveX pour ouvrir le menu contextuel.  
  
3.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter un événement**.  
  
     Cela ouvre le menu de création d'événements.  
  
4.  Dans la liste déroulante **Nom d'évènement**, sélectionnez `KeyPress`.  
  
5.  Cliquez sur **Terminer**.  
  
##  <a name="_core_classwizard_changes_for_stock_events"></a> Modifications de l'Assistant Ajout d'événement pour les événements standard  
 Comme les événements standard sont gérés par la classe de base du contrôle, l'assistant d'ajout d'événement ne modifie pas la déclaration de classe de quelque manière que ce soit.  Il ajoute l'événement à la table des événements du contrôle et effectue une entrée dans le fichier .IDL.  La ligne suivante est ajoutée à la table des événements du contrôle, situé dans le fichier de l'implémentation du contrôle de classe \(.CPP\) :  
  
 [!code-cpp[NVC_MFC_AxUI#5](../mfc/codesnippet/CPP/mfc-activex-controls-adding-stock-events-to-an-activex-control_1.cpp)]  
  
 Ajouter le code déclenche un événement KeyPress lorsqu'un message `WM_CHAR` est reçu et le contrôle est actif.  L'événement KeyPress peut être activé à d'autres moments en appelant sa fonction d'activation \(par exemple, `FireKeyPress`\) à partir du code de contrôle.  
  
 L'assistant d'ajout d'événements ajoute la ligne de code suivante au fichier .IDL de contrôle :  
  
 [!code-cpp[NVC_MFC_AxUI#6](../mfc/codesnippet/CPP/mfc-activex-controls-adding-stock-events-to-an-activex-control_2.idl)]  
  
 Cette ligne associe l'événement KeyPress avec l'ID de dispatch standard et permet au conteneur d'anticiper l'événement de KeyPress.  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Contrôles ActiveX MFC : méthodes](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Class](../mfc/reference/colecontrol-class.md)