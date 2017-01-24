---
title: "Styles statiques | Microsoft Docs"
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
  - "SS_SUNKEN"
  - "SS_CENTER"
  - "SS_ENHMETAFILE"
  - "SS_RIGHT"
  - "SS_BLACKRECT"
  - "SS_LEFTNOWORDWRAP"
  - "SS_GRAYFRAME"
  - "SS_USERITEM"
  - "SS_GRAYRECT"
  - "SS_WHITEFRAME"
  - "SS_ETCHEDFRAME"
  - "SS_ETCHEDVERT"
  - "SS_WHITERECT"
  - "SS_PATHELLIPSIS"
  - "SS_WORDELLIPSIS"
  - "SS_NOPREFIX"
  - "SS_BITMAP"
  - "SS_SIMPLE"
  - "SS_CENTERIMAGE"
  - "SS_BLACKFRAME"
  - "SS_OWNERDRAW"
  - "SS_REALSIZEIMAGE"
  - "SS_RIGHTJUST"
  - "SS_ICON"
  - "SS_NOTIFY"
  - "SS_ETCHEDHORZ"
  - "SS_LEFT"
  - "SS_ENDELLIPSIS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SS_BITMAP (constante)"
  - "SS_BLACKFRAME (constante)"
  - "SS_BLACKRECT (constante)"
  - "SS_CENTER (constante)"
  - "SS_CENTERIMAGE (constante)"
  - "SS_ENDELLIPSIS (constante)"
  - "SS_ENHMETAFILE (constante)"
  - "SS_ETCHEDFRAME (constante)"
  - "SS_ETCHEDHORZ (constante)"
  - "SS_ETCHEDVERT (constante)"
  - "SS_GRAYFRAME (constante)"
  - "SS_GRAYRECT (constante)"
  - "SS_ICON (constante)"
  - "SS_LEFT (constante)"
  - "SS_LEFTNOWORDWRAP (constante)"
  - "SS_NOPREFIX (constante)"
  - "SS_NOTIFY (constante)"
  - "SS_OWNERDRAW (constante)"
  - "SS_PATHELLIPSIS (constante)"
  - "SS_REALSIZEIMAGE (constante)"
  - "SS_RIGHT (constante)"
  - "SS_RIGHTJUST (constante)"
  - "SS_SIMPLE (constante)"
  - "SS_SUNKEN (constante)"
  - "SS_USERITEM (constante)"
  - "SS_WHITEFRAME (constante)"
  - "SS_WHITERECT (constante)"
  - "SS_WORDELLIPSIS (constante)"
  - "styles statiques"
ms.assetid: a1114548-fc6d-491d-8c46-21d11b8574f5
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Styles statiques
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **SS\_BITMAP** spécifie une bitmap où doit être affiché dans le contrôle statique.  Le texte donné est le nom de bitmap \(pas un nom fichier\) défini plus dans le fichier de ressources.  Le style ignore les éventuels paramètres de nWidth et de nHeight ; le contrôle de la classe s'ajuste automatiquement à la bitmap.  
  
-   **SS\_BLACKFRAME** spécifie une zone avec un cadre dessiné à la même couleur que les cadres de fenêtre.  La valeur par défaut est noir.  
  
-   **SS\_BLACKRECT** Spécifie un rectangle rempli avec la couleur utilisée pour ajouter des cadres de fenêtre.  La valeur par défaut est noir.  
  
-   **SS\_CENTRE** indique un rectangle simple et affiche le texte centré donné dans le rectangle.  Le texte est mis en forme pour qu'il s'affiche.  Les mots qui étendraient après la fin d'une ligne sont automatiquement inclus dans le début de la ligne centrée suivante.  
  
-   **SS\_CENTERIMAGE** spécifie que, si la bitmap ou l'icône est inférieure à la zone client du contrôle statique, le reste de la zone client est rempli avec les couleurs au minimum dans le coin supérieur gauche de la bitmap ou l'icône.  Si la vérification des types statiques contient une seule ligne de texte, le texte est centré verticalement dans la zone client du contrôle.  
  
-   **SS\_ENDELLIPSIS** ou **SS\_PATHELLIPSIS** remplace la partie de la chaîne donnée par des points de suspension si nécessaire, afin que les résultats s'intègrent dans le rectangle spécifié.  
  
     Vous pouvez spécifier **SS\_END\_ELLIPSIS** pour remplacer les caractères à la fin de la chaîne, ou **SS\_PATHELLIPSIS** pour remplacer des caractères au milieu de la chaîne.  Si la chaîne contient des caractères de barre oblique inverse \(\\\), **SS\_PATHELLIPSIS** conserve autant de texte après la dernière barre oblique inverse que possible.  
  
-   **SS\_ENHMETAFILE** spécifie un métafichier amélioré qui doit être affiché dans le contrôle statique.  Le texte donné est le nom d'un métafichier.  Un contrôle statique de métafichier amélioré a une taille fixe ; un métafichier est mis à l'échelle à la zone client de vérification des types statiques.  
  
-   **SS\_ETCHEDFRAME** dessine le cadre de vérification des types statiques avec le style de bord de **EDGE\_ETCHED**.  
  
-   **SS\_ETCHEDHORZ** dessine les sessions de haut et bas du contrôle statique à l'aide du style de bord de **EDGE\_ETCHED**.  
  
-   **SS\_ETCHEDVERT** dessine les bords droit et gauche du contrôle statique à l'aide du style de bord de EDGE\_ETCHED.  
  
-   **SS\_GRAYFRAME** spécifie une zone avec un cadre dessiné à la même couleur de l'arrière\-plan \(ordinateur\).  La valeur par défaut est gris.  
  
-   **SS\_GRAYRECT** spécifie un rectangle rempli avec la couleur utilisée pour remplir l'arrière\-plan.  La valeur par défaut est gris.  
  
-   **SS\_ICON** affiche une icône affichée dans la boîte de dialogue.  Le texte donné est le nom d'une icône \(pas un nom fichier\) défini dans le fichier de ressources.  Les paramètres de `nWidth` et de `nHeight` sont ignorés ; l'icône de classe se calibre automatiquement.  
  
-   **SS\_GAUCHE** indique un rectangle simple et affiche le vidage\- gauche donné de texte au rectangle.  Le texte est mis en forme pour qu'il s'affiche.  Les mots qui étendraient après la fin d'une ligne sont automatiquement inclus dans le début de la ligne centrée suivante.  
  
-   **SS\_LEFTNOWORDWRAP** indique un rectangle simple et affiche le vidage\- gauche donné de texte au rectangle.  Les Onglets sont développés, mais les mots ne sont pas inclus.  Texte qui s'étend au delà de la fin d'une ligne est tronqué.  
  
-   **SS\_NOPREFIX** à moins que le style est spécifié, Windows interprètera les caractères commercial \(&\) dans le texte du contrôle qui soient des caractères de préfixe des accélérateurs.  Dans ce cas, le commercial est supprimé et le caractère suivant dans la chaîne est souligné.  Si un contrôle statique est de type contenant le texte où cette fonctionnalité n'est pas demandée, **SS\_NOPREFIX** peut être ajoutée.  Ce style de contrôle statique peut être inclus dans les contrôles statiques définis.  Vous pouvez combiner **SS\_PASDEPREFIXE** avec d'autres styles à l'aide de l'opérateur de bits OR.  C'est le plus souvent lorsque les noms de fichiers ou d'autres chaînes qui peuvent contenir un besoin commercial d'être affiché dans un contrôle statique dans une boîte de dialogue.  
  
-   **SS\_NOTIFy** envoie les messages parents de la fenêtre **STN\_CLICKED**, aux notifications de **STN\_DBLCLK** de **STN\_DISABLE**, et de **STN\_ENABLE** lorsque l'utilisateur clique ou double\-clique sur le contrôle.  
  
-   **SS\_OWNERDRAW** spécifie que le propriétaire du contrôle statique est chargé de dessiner le contrôle.  La fenêtre propriétaire reçoit un message de `WM_DRAWITEM` chaque fois que les contrôles ont besoin d'être dessiné.  
  
-   **SS\_REALSIZEIMAGE** empêche une vérification des types d'icône ou bitmap \(autrement dit, les contrôles statiques qui ont le style de **SS\_ICON** ou de **SS\_BITMAP** \) d'être redimensionné tel qu'il est chargé ou dessiné.  Si l'icône ou bitmap est supérieure à la zone de destination, l'image est découpée.  
  
-   **SS\_RIGHT** indique un rectangle simple et affiche le vidage\-droit donné de texte au rectangle.  Le texte est mis en forme pour qu'il s'affiche.  Les mots qui étendraient après la fin d'une ligne sont automatiquement inclus dans le début de la ligne centrée droite suivante.  
  
-   **SS\_RIGHTJUST** spécifie que l'angle inférieur droit d'un contrôle statique avec le style de **SS\_BITMAP** ou de **SS\_ICON** doit rester là où le contrôle est redimensionné.  Seuls les premiers et les parties gauche sont ajustés pour permettre une nouvelle image ou icône.  
  
-   **SS\_SIMPLE** indique un rectangle simple et contient une seule ligne de vidage\-gauche de texte au rectangle.  La ligne de texte ne peut pas se raccourcir ou être modifié de quelque manière que ce soit. \(La fenêtre parente ou la boîte de dialogue du contrôle ne doit pas traiter le message de `WM_CTLCOLOR` .\)  
  
-   **SS\_SUNKEN** dessine une bordure semi\-enterrée autour d'un contrôle statique.  
  
-   **SS\_USERITEM** spécifie un élément défini par l'utilisateur.  
  
-   **SS\_WHITEFRAME** spécifie une zone avec un cadre dessiné avec la même couleur de l'arrière\-plan de la fenêtre.  La valeur par défaut est blanc.  
  
-   **SS\_RECTANGLEBLANC** spécifie un rectangle rempli avec la même couleur utilisée pour remplir l'arrière\-plan de la fenêtre.  La valeur par défaut est blanc.  
  
-   **SS\_WORDELLIPSIS** tronque les textes qui ne s'ajustent pas et ajoute des points de suspension.  
  
## Voir aussi  
 [Styles utilisés par MFC](../../mfc/reference/styles-used-by-mfc.md)   
 [CStatic::Create](../Topic/CStatic::Create.md)   
 [DrawEdge](http://msdn.microsoft.com/library/windows/desktop/dd162477)   
 [Static Control Styles](http://msdn.microsoft.com/library/windows/desktop/bb760773)