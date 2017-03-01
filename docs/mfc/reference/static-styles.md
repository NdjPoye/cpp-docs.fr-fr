---
title: Styles statiques | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SS_SUNKEN
- SS_CENTER
- SS_ENHMETAFILE
- SS_RIGHT
- SS_BLACKRECT
- SS_LEFTNOWORDWRAP
- SS_GRAYFRAME
- SS_USERITEM
- SS_GRAYRECT
- SS_WHITEFRAME
- SS_ETCHEDFRAME
- SS_ETCHEDVERT
- SS_WHITERECT
- SS_PATHELLIPSIS
- SS_WORDELLIPSIS
- SS_NOPREFIX
- SS_BITMAP
- SS_SIMPLE
- SS_CENTERIMAGE
- SS_BLACKFRAME
- SS_OWNERDRAW
- SS_REALSIZEIMAGE
- SS_RIGHTJUST
- SS_ICON
- SS_NOTIFY
- SS_ETCHEDHORZ
- SS_LEFT
- SS_ENDELLIPSIS
dev_langs:
- C++
helpviewer_keywords:
- SS_ICON constant
- SS_WHITEFRAME constant
- SS_BLACKFRAME constant
- SS_ETCHEDHORZ constant
- SS_OWNERDRAW constant
- SS_BITMAP constant
- SS_NOPREFIX constant
- SS_NOTIFY constant
- SS_CENTER constant
- SS_REALSIZEIMAGE constant
- SS_ETCHEDFRAME constant
- SS_CENTERIMAGE constant
- SS_SUNKEN constant
- SS_ENDELLIPSIS constant
- SS_WORDELLIPSIS constant
- SS_WHITERECT constant
- SS_ETCHEDVERT constant
- SS_GRAYFRAME constant
- SS_LEFTNOWORDWRAP constant
- SS_LEFT constant
- SS_SIMPLE constant
- static styles
- SS_ENHMETAFILE constant
- SS_GRAYRECT constant
- SS_USERITEM constant
- SS_PATHELLIPSIS constant
- SS_BLACKRECT constant
- SS_RIGHT constant
- SS_RIGHTJUST constant
ms.assetid: a1114548-fc6d-491d-8c46-21d11b8574f5
caps.latest.revision: 12
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ad34c688fdfd3c2b4c81a0a03fbce53a905162ad
ms.lasthandoff: 02/24/2017

---
# <a name="static-styles"></a>Styles statiques
-   **SS_BITMAP** spécifie une image bitmap à afficher dans le contrôle statique. Le texte spécifié est le nom de la bitmap (pas un nom de fichier) définie ailleurs dans le fichier de ressources. Le style ignore les paramètres nWidth et nHeight ; le contrôle redimensionne automatiquement pour prendre en charge de la bitmap.  
  
-   **SS_BLACKFRAME** spécifie une zone avec une image dessinée avec la même couleur que les cadres de fenêtres. La valeur par défaut est noir.  
  
-   **SS_BLACKRECT** spécifie un rectangle rempli avec la couleur utilisée pour dessiner des cadres de fenêtre. La valeur par défaut est noir.  
  
-   **SS_CENTER** désigne un rectangle simple et affiche le texte donné est centré dans le rectangle. Le texte est mis en forme avant d’être affiché. Les mots qui seraient étend au-delà de la fin d’une ligne sont automatiquement renvoyées au début de la ligne suivante centré.  
  
-   **SS_CENTERIMAGE** Spécifie que si l’icône ou le bitmap est inférieure à la zone cliente du contrôle statique, le reste de la zone cliente est rempli avec la couleur du pixel dans le coin supérieur gauche de l’image bitmap ou icône. Si le contrôle statique contient une seule ligne de texte, le texte est centré verticalement dans la zone cliente du contrôle.  
  
-   **SS_ENDELLIPSIS** ou **SS_PATHELLIPSIS** remplace une partie de la chaîne donnée par les points de suspension, si nécessaire, pour que le résultat tienne dans le rectangle spécifié.  
  
     Vous pouvez spécifier **SS_END_ELLIPSIS** pour remplacer des caractères à la fin de la chaîne, ou **SS_PATHELLIPSIS** pour remplacer des caractères au milieu de la chaîne. Si la chaîne contient une barre oblique inverse (\\) caractères, **SS_PATHELLIPSIS** conserve autant du texte après la dernière barre oblique inverse que possible.  
  
-   **SS_ENHMETAFILE** spécifie un métafichier amélioré doit être affichée dans le contrôle statique. Le texte spécifié est le nom d’un métafichier. Un contrôle statique métafichier amélioré a une taille fixe ; le métafichier est redimensionné pour s’ajuster à la zone du client du contrôle statique.  
  
-   **SS_ETCHEDFRAME** Dessine le cadre du contrôle statique en utilisant le **EDGE_ETCHED** edge du style.  
  
-   **SS_ETCHEDHORZ** dessine les bords supérieur et inférieur du contrôle statique en utilisant le **EDGE_ETCHED** edge du style.  
  
-   **SS_ETCHEDVERT** dessine les bords gauche et droit du contrôle statique à l’aide du style de contour EDGE_ETCHED.  
  
-   **SS_GRAYFRAME** spécifie une zone avec une image dessinée avec la même couleur que l’arrière-plan de l’écran (bureau). La valeur par défaut est gris.  
  
-   **SS_GRAYRECT** spécifie un rectangle rempli avec la couleur utilisée pour remplir l’arrière-plan de l’écran. La valeur par défaut est gris.  
  
-   **SS_ICON** désigne une icône s’affichée dans la boîte de dialogue. Le texte spécifié est le nom d’une icône (pas un nom de fichier) définie ailleurs dans le fichier de ressources. Le `nWidth` et `nHeight` sont ignorés ; l’icône se redimensionne automatiquement.  
  
-   **SS_LEFT** désigne un rectangle simple et affiche le texte donné de vidage à gauche dans le rectangle. Le texte est mis en forme avant d’être affiché. Les mots qui seraient étend au-delà de la fin d’une ligne sont automatiquement renvoyées au début de la ligne suivante de vidage à gauche.  
  
-   **SS_LEFTNOWORDWRAP** désigne un rectangle simple et affiche le texte donné de vidage à gauche dans le rectangle. Onglets sont développées, mais les mots ne sont pas encapsulées. Texte qui s’étend au-delà de la fin d’une ligne est coupé.  
  
-   **SS_NOPREFIX** à moins que ce style est spécifié, Windows interprète les caractères « et commercial » (&) dans le texte du contrôle accélérateur des caractères de préfixe. Dans ce cas, l’et commercial est supprimé et le caractère suivant dans la chaîne est souligné. Si un contrôle statique doit contenir du texte dans lequel cette fonctionnalité n’est pas souhaitée, **SS_NOPREFIX** peuvent être ajoutés. Ce style de contrôle de code statique peut être inclus dans les contrôles statiques définis. Vous pouvez combiner **SS_NOPREFIX** avec d’autres styles à l’aide de l’opérateur OR. Cela est généralement utilisée lorsque des noms de fichiers ou d’autres chaînes qui peuvent contenir une esperluette doivent être affichés dans un contrôle statique dans une boîte de dialogue.  
  
-   **SS_NOTIFY** envoie la fenêtre parente **STN_CLICKED**, **STN_DBLCLK**, **STN_DISABLE**, et **STN_ENABLE** les messages de notification lorsque l’utilisateur clique ou double-clique sur le contrôle.  
  
-   **SS_OWNERDRAW** Spécifie que le propriétaire du contrôle statique est responsable du dessin du contrôle. La fenêtre propriétaire reçoit un `WM_DRAWITEM` message chaque fois que le contrôle doit être dessiné.  
  
-   **SS_REALSIZEIMAGE** empêche un contrôle statique d’une icône ou bitmap (autrement dit, les contrôles statiques dont le **SS_ICON** ou **SS_BITMAP** style) d’être redimensionnée lorsqu’il est chargé ou dessiner. Si l’icône ou le bitmap est supérieure à la zone de destination, l’image est découpée.  
  
-   **SS_RIGHT** désigne un rectangle simple et affiche le texte donné de vidage à droite dans le rectangle. Le texte est mis en forme avant d’être affiché. Les mots qui seraient étend au-delà de la fin d’une ligne sont automatiquement renvoyées au début de la ligne suivante de vidage à droite.  
  
-   **SS_RIGHTJUST** qui spécifie le coin inférieur droit d’un contrôle statique avec le **SS_BITMAP** ou **SS_ICON** style doit rester fixe lorsque le contrôle est redimensionné. Seuls les côtés gauche et supérieures sont ajustées pour prendre en charge une nouvelle image bitmap ou une icône.  
  
-   **SS_SIMPLE** désigne un rectangle simple et affiche une seule ligne de texte de vidage à gauche dans le rectangle. La ligne de texte ne peut pas être réduite ou modifiée. (Boîte de dialogue ou la fenêtre parent du contrôle ne doit pas traiter la `WM_CTLCOLOR` message.)  
  
-   **SS_SUNKEN** Dessine une bordure autour d’un contrôle statique demi enfoncée.  
  
-   **SS_USERITEM** spécifie un élément défini par l’utilisateur.  
  
-   **SS_WHITEFRAME** spécifie une zone avec une image dessinée avec la même couleur que l’arrière-plan de la fenêtre. La valeur par défaut est blanc.  
  
-   **SS_WHITERECT** spécifie un rectangle rempli avec la couleur utilisée pour remplir l’arrière-plan de la fenêtre. La valeur par défaut est blanc.  
  
-   **SS_WORDELLIPSIS** tronque le texte qui ne tient pas et ajoute les points de suspension.  
  
## <a name="see-also"></a>Voir aussi  
 [Styles utilisés par MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CStatic::Create](../../mfc/reference/cstatic-class.md#create)   
 [DrawEdge](http://msdn.microsoft.com/library/windows/desktop/dd162477)   
 [Styles de contrôle statique](http://msdn.microsoft.com/library/windows/desktop/bb760773)


