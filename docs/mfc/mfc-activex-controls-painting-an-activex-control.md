---
title: "Contr&#244;les ActiveX MFC&#160;: peinture d&#39;un contr&#244;le ActiveX | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles ActiveX MFC, optimiser"
  - "contrôles ActiveX MFC, peindre"
ms.assetid: 25fff9c0-4dab-4704-aaae-8dfb1065dee3
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX MFC&#160;: peinture d&#39;un contr&#244;le ActiveX
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article décrit le processus de peinture du contrôle ActiveX et comment modifier le code de peinture pour optimiser le processus. \(Consultez [Optimiser le dessin de contrôle](../mfc/optimizing-control-drawing.md) pour obtenir des techniques sur la façon d'optimiser le dessin pour ne pas avoir les contrôles restaurant individuellement les objets précédemment sélectionnés de GDI.  Une fois que toutes les vérifications ont été tirées, le conteneur peut automatiquement restaurer des objets d'origine.\)  
  
 Les exemples dans cet article proviennent d'un contrôle créé par l'Assistant de Contrôle ActiveX de MFC avec les paramètres par défaut.  Pour plus d'informations sur la création d'une application de contrôle squelette à l'aide de l'Assistant de Contrôle ActiveX de MFC, consultez l'article [Assistant de Contrôle ActiveX de MFC](../mfc/reference/mfc-activex-control-wizard.md).  
  
 Les rubriques suivantes sont couvertes:  
  
-   [Le processus global pour peindre un contrôle et le code créés par l'Assistant de Contrôle ActiveX pour prendre en charge la peinture](#_core_the_painting_process_of_an_activex_control)  
  
-   [Comment optimiser le processus de peinture](#_core_optimizing_your_paint_code)  
  
-   [Comment peindre votre contrôle à l'aide de métafichiers](#_core_painting_your_control_using_metafiles)  
  
##  <a name="_core_the_painting_process_of_an_activex_control"></a> Le processus de peinture d'un contrôle ActiveX  
 Lorsque les contrôles ActiveX sont initialement affichés ou redessinés, ils suivent un processus de peinture semblable à d'autres applications développées à l'aide de MFC, avec une distinction importante: les contrôles ActiveX peuvent être dans un état actif ou inactif.  
  
 Un contrôle actif est représenté dans un conteneur de contrôles ActiveX par une fenêtre enfant.  Comme d'autres fenêtres, il est chargé de se peindre lorsqu'un message d' `WM_PAINT` est reçu.  La classe de base du contrôle, [COleControl](../mfc/reference/colecontrol-class.md), gère ce message dans sa fonction d' `OnPaint`.  Cette implémentation par défaut appelle la fonction d' `OnDraw` de votre contrôle.  
  
 Un contrôle inactif est peint différemment.  Lorsque le contrôle est inactif, sa fenêtre est invisible ou inexistante, donc il ne peut pas recevoir un message de peinture.  En revanche, le conteneur de contrôle appelle directement la fonction d' `OnDraw` du contrôle.  Ceci diffère du processus de peinture actif d'un contrôle en ce que la fonction membre d' `OnPaint` n'est jamais appelée.  
  
 Comme décrit dans les paragraphes précédents, comment un contrôle ActiveX est mis à jour dépend de l'état du contrôle.  Toutefois, étant donné que l'infrastructure appelle la fonction membre d' `OnDraw` dans les deux cas, vous ajoutez la majorité de votre code de peinture dans cette fonction membre.  
  
 La fonction membre d' `OnDraw` gère le contrôle de la peinture.  Lorsqu'un contrôle est inactif, le conteneur de contrôle appelle `OnDraw`, en passant le contexte de périphérique du conteneur de contrôle et les coordonnées de la zone rectangulaire occupée par le contrôle.  
  
 Le rectangle passé par l'infrastructure à la fonction membre d' `OnDraw` contient la zone occupée par le contrôle.  Si le contrôle est actif, l'angle supérieur gauche est \(0, 0\) et le contexte de périphérique est passé pour la fenêtre enfant qui contient le contrôle.  Si le contrôle est inactif, la coordonnée supérieure gauche n'est pas nécessairement \(0, 0\) et le contexte de périphérique est passé pour le conteneur de contrôle qui contient le contrôle.  
  
> [!NOTE]
>  Il est important que les modifications apportées à `OnDraw` ne dépendent pas du fait que le point supérieur gauche du rectangle soit égal à \(0, 0\) et que vous dessiniez uniquement à l'intérieur du rectangle passé à `OnDraw`.  Des résultats inattendus peuvent se produire si vous dessinez au delà de la zone du rectangle.  
  
 L'implémentation par défaut fournie par l'Assistant de Contrôle ActiveX de MFC dans le fichier d'implémentation du contrôle \(.CPP\), comme indiqué ci\-dessous, peint le rectangle avec un pinceau blanc et remplit l'ellipse avec la couleur d'arrière\-plan actuelle.  
  
 [!code-cpp[NVC_MFC_AxUI#1](../mfc/codesnippet/CPP/mfc-activex-controls-painting-an-activex-control_1.cpp)]  
  
> [!NOTE]
>  Lors de la peinture d'un contrôle, vous ne devez pas faire d'hypothèses concernant l'état du contexte de périphérique passé en tant que paramètre de *pdc* à la fonction d' `OnDraw`.  Occasionnellement le contexte de périphérique est fourni par l'application conteneur et n'est pas nécessairement initialisé à l'état par défaut.  En particulier, sélectionnez explicitement les stylets, pinceaux, couleurs, polices, et autres ressources dont votre code de dessin dépend.  
  
##  <a name="_core_optimizing_your_paint_code"></a> Optimiser votre code de peinture  
 Lorsque le contrôle se peint avec succès, l'étape suivante consiste à optimiser la fonction d' `OnDraw`.  
  
 L'implémentation par défaut du contrôle de peinture ActiveX peint la zone de contrôle entière.  Ceci suffit pour les contrôles simples, mais dans de nombreux cas redessiner le contrôle serait plus rapide si seulement la partie qui nécessitait une mise à jour était repeinte, au lieu du contrôle entier.  
  
 La fonction d' `OnDraw` fournit une méthode simple d'optimisation en passant `rcInvalid`, le champ rectangulaire de contrôle qui requiert d'être redessiné.  Utilisez cette zone, généralement inférieure à la zone de contrôle entière, pour accélérer le processus de peinture.  
  
##  <a name="_core_painting_your_control_using_metafiles"></a> Peinture de votre contrôle à l'aide de métafichiers  
 Dans la plupart des cas le paramètre d' `pdc` de la fonction d' `OnDraw` pointe sur un contexte d'écran de périphérique \(DC\).  Toutefois, lors de l'impression d'images du contrôle ou lors d'une session d'aperçu avant impression, le contrôleur de domaine reçu pour affichage est un type spécial appelé « contexte de périphérique de métafichier ».  Contrairement à un écran contrôleur de domaine, qui gère à la fois les demandes qui lui sont envoyées, les métafichiers DC emmagasine les demandes qui doivent être jouées ultérieurement.  Certaines applications conteneur peuvent également choisir d'afficher l'image de contrôle lorsqu'il se trouve en mode création à l'aide d'un métafichier DC.  
  
 Les demandes de dessin de métafichier peuvent être effectuées par le conteneur via deux fonctions d'interface : **IViewObject::Draw** \(cette fonction peut également être appelée pour le dessin non métafichier\) et **IDataObject::GetData**.  Lorsqu'un contexte de périphérique de métafichier est passé en tant que paramètre, l'infrastructure MFC passe un appel à [COleControl::OnDrawMetafile](../Topic/COleControl::OnDrawMetafile.md).  Puisqu'il s'agit d'une fonction membre virtuelle, remplacez cette fonction dans la classe de contrôle pour effectuer tout traitement spécial.  Le comportement par défaut appelle `COleControl::OnDraw`.  
  
 Pour garantir que le contrôle peut être dessiné à la fois sur l'écran et sur des contextes de périphérique de métafichier, vous ne devez utiliser que les fonctions membres qui sont prises en charge à la fois dans un écran et dans un contexte de périphérique de métafichier.  Sachez que le système de coordonnées peut ne pas être exprimé en pixels.  
  
 Etant donné que l'implémentation par défaut de `OnDrawMetafile` appelle la fonction d' `OnDraw` de contrôle, n'utilisez que les fonctions membres qui conviennent à la fois pour un métafichier et pour un contexte de périphérique, sauf si vous remplacez `OnDrawMetafile`.  Ce qui suit répertorie le sous\-ensemble de fonctions membres d' `CDC` qui peuvent être utilisées à la fois dans un métafichier et dans écran de contexte de périphérique.  Pour plus d'informations sur ces fonctions, consultez la classe [CDC](../mfc/reference/cdc-class.md) dans la *Référence de MFC*.  
  
|Arc|BibBlt|Corde|  
|---------|------------|-----------|  
|**Ellipse**|**Échappement**|`ExcludeClipRect`|  
|`ExtTextOut`|`FloodFill`|`IntersectClipRect`|  
|`LineTo`|`MoveTo`|`OffsetClipRgn`|  
|`OffsetViewportOrg`|`OffsetWindowOrg`|`PatBlt`|  
|`Pie`|**Polygon**|`Polyline`|  
|`PolyPolygon`|`RealizePalette`|`RestoreDC`|  
|`RoundRect`|`SaveDC`|`ScaleViewportExt`|  
|`ScaleWindowExt`|`SelectClipRgn`|`SelectObject`|  
|`SelectPalette`|`SetBkColor`|`SetBkMode`|  
|`SetMapMode`|`SetMapperFlags`|`SetPixel`|  
|`SetPolyFillMode`|`SetROP2`|`SetStretchBltMode`|  
|`SetTextColor`|`SetTextJustification`|`SetViewportExt`|  
|`SetViewportOrg`|`SetWindowExt`|`SetWindowORg`|  
|`StretchBlt`|`TextOut`||  
  
 Outre les fonctions membres d' `CDC`, il existe plusieurs autres fonctions compatibles dans un contexte de périphérique de métafichier.  Ceux\-ci incluent [CPalette::AnimatePalette](../Topic/CPalette::AnimatePalette.md), [CFont::CreateFontIndirect](../Topic/CFont::CreateFontIndirect.md), et trois fonctions membres d' `CBrush`: [CreateBrushIndirect](../Topic/CBrush::CreateBrushIndirect.md), [CreateDIBPatternBrush](../Topic/CBrush::CreateDIBPatternBrush.md) et [CreatePatternBrush](../Topic/CBrush::CreatePatternBrush.md).  
  
 Les fonctions qui ne sont pas stockées dans un métafichier sont : [DrawFocusRect](../Topic/CDC::DrawFocusRect.md), [DrawIcon](../Topic/CDC::DrawIcon.md), [DrawText](../Topic/CDC::DrawText.md), [ExcludeUpdateRgn](../Topic/CDC::ExcludeUpdateRgn.md), [FillRect](../Topic/CDC::FillRect.md), [FrameRect](../Topic/CDC::FrameRect.md), [GrayString](../Topic/CDC::GrayString.md), [InvertRect](../Topic/CDC::InvertRect.md), [ScrollDC](../Topic/CDC::ScrollDC.md) et [TabbedTextOut](../Topic/CDC::TabbedTextOut.md).  Étant donné qu'un contexte de périphérique de métafichier n'est pas réellement associé à un périphérique, vous ne pouvez pas utiliser SetDIBits, GetDIBits, et CreateDIBitmap avec un contexte de périphérique de métafichier.  Vous pouvez utiliser SetDIBitsToDevice et StretchDIBits avec un contexte de périphérique de métafichier comme destination.  [CreateCompatibleDC](../Topic/CDC::CreateCompatibleDC.md), [CreateCompatibleBitmap](../Topic/CBitmap::CreateCompatibleBitmap.md) et [CreateDiscardableBitmap](../Topic/CBitmap::CreateDiscardableBitmap.md) n'ont pas de sens avec un contexte de périphérique de métafichier.  
  
 Un autre point à prendre en considération lors de l'utilisation d'un contexte de périphérique de métafichier est que le système de coordonnées peut ne pas être exprimé en pixels.  Pour cette raison, tout le code de dessin doit être modifié pour faire en sorte de rentrer dans le rectangle passé à `OnDraw` dans le paramètre d' `rcBounds`.  Ceci empêche la peinture accidentelle en dehors du contrôle car `rcBounds` représente la taille de la fenêtre de contrôle.  
  
 Une fois que vous avez implémenté le rendu de métafichier pour le contrôle, utilisez Container Test pour tester le métafichier.  Pour plus d'informations sur la manière d'accéder à Test Container, consultez [Test des propriétés et des événements à l'aide de Test Container](../mfc/testing-properties-and-events-with-test-container.md).  
  
#### Pour tester le métafichier du contrôle à l'aide de Test Container  
  
1.  Dans le menu **Modifier** de Test Container, cliquez sur **Insérer Nouveau Contrôle**.  
  
2.  Dans la boîte de dialogue d' **Insérer Nouveau Contrôle** , sélectionnez le contrôle et cliquez sur **OK**.  
  
     Le contrôle s'affiche dans le conteneur de test.  
  
3.  Dans le menu de **Contrôler** , cliquez sur **Dessiner Métafichier**.  
  
     Une fenêtre distincte apparaît dans laquelle le métafichier s'affiche.  Vous pouvez modifier la taille de cette fenêtre pour voir comment la mise à l'échelle affecte un métafichier du contrôle.  Vous pouvez fermer cette fenêtre à tout moment.  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)