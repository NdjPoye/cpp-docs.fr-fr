---
title: "CDC, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDC (classe)"
  - "coordinates in Windows 95/98 [C++]"
  - "device contexts [C++], CDC (classe)"
  - "screen coordinates in device contexts"
  - "Windows (C++), device contexts"
  - "Windows 95 [C++], coordonnées de l'écran"
  - "Windows 98 [C++], coordonnées de l'écran"
ms.assetid: 715b3334-cb2b-4c9c-8067-02eb7c66c8b2
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDC, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit une classe d'objets contexte de périphérique.  
  
## Syntaxe  
  
```  
class CDC : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDC::CDC](../Topic/CDC::CDC.md)|Construit un objet `CDC`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDC::AbortDoc](../Topic/CDC::AbortDoc.md)|Termine le travail d'impression actuelle, la suppression pendant que l'application a entré à l'appareil depuis le dernier appel de la fonction membre d' `StartDoc` .|  
|[CDC::AbortPath](../Topic/CDC::AbortPath.md)|Ferme et ignore tous les chemins dans le contexte de périphérique.|  
|[CDC::AddMetaFileComment](../Topic/CDC::AddMetaFileComment.md)|Copie le commentaire d'une mémoire tampon dans un métafichier spécifié d'améliorer\-format.|  
|[CDC::AlphaBlend](../Topic/CDC::AlphaBlend.md)|Affiche les bitmaps qui ont des pixels transparents ou translucides.|  
|[CDC::AngleArc](../Topic/CDC::AngleArc.md)|Dessine un segment de ligne et un arc, et déplace la position actuelle au point de terminaison de l'arc.|  
|[CDC::Arc](../Topic/CDC::Arc.md)|Dessine un arc elliptique.|  
|[CDC::ArcTo](../Topic/CDC::ArcTo.md)|Dessine un arc elliptique.  Cette fonction est semblable à `Arc`, sauf que la position actuelle est mise à jour.|  
|[CDC::Attach](../Topic/CDC::Attach.md)|Joint un contexte de périphérique windows à cet objet d' `CDC` .|  
|[CDC::BeginPath](../Topic/CDC::BeginPath.md)|Ouvre une parenthèse de chemin d'accès dans le contexte de périphérique.|  
|[CDC::BitBlt](../Topic/CDC::BitBlt.md)|Copie une bitmap d'un contexte spécifié de périphérique.|  
|[CDC::Chord](../Topic/CDC::Chord.md)|Dessine une pression simultanée \(une figure fermée limitées par l'intersection d'une ellipse et un segment de ligne\).|  
|[CDC::CloseFigure](../Topic/CDC::CloseFigure.md)|Ferme une figure ouverte dans un chemin d'accès.|  
|[CDC::CreateCompatibleDC](../Topic/CDC::CreateCompatibleDC.md)|Crée un contexte de périphérique qui est compatible avec un autre contexte de périphérique.  Vous pouvez utiliser des préparations image dans la mémoire.|  
|[CDC::CreateDC](../Topic/CDC::CreateDC.md)|Crée un contexte de périphérique pour un appareil spécifique.|  
|[CDC::CreateIC](../Topic/CDC::CreateIC.md)|Crée un contexte d'informations pour un appareil spécifique.  Cela offre un moyen rapide pour obtenir des informations sur le périphérique sans créer un contexte de périphérique.|  
|[CDC::DeleteDC](../Topic/CDC::DeleteDC.md)|Supprime le contexte de périphérique windows associé à cet objet d' `CDC` .|  
|[CDC::DeleteTempMap](../Topic/CDC::DeleteTempMap.md)|Appelé par le gestionnaire comme les temps d'inactivité d' `CWinApp` pour supprimer tout objet temporaire d' `CDC` créé par `FromHandle`.  Détache également le contexte de périphérique.|  
|[CDC::Detach](../Topic/CDC::Detach.md)|Détache le contexte de périphérique windows de cet objet d' `CDC` .|  
|[CDC::DPtoHIMETRIC](../Topic/CDC::DPtoHIMETRIC.md)|Convertit les unités dans des unités HIMETRIC.|  
|[CDC::DPtoLP](../Topic/CDC::DPtoLP.md)|Convertit les unités en unités logiques.|  
|[CDC::Draw3dRect](../Topic/CDC::Draw3dRect.md)|Dessine un rectangle en trois dimensions.|  
|[CDC::DrawDragRect](../Topic/CDC::DrawDragRect.md)|Les effacements et redessine un rectangle à mesure qu'il est déplacé.|  
|[CDC::DrawEdge](../Topic/CDC::DrawEdge.md)|Dessine les bords d'un rectangle.|  
|[CDC::DrawEscape](../Topic/CDC::DrawEscape.md)|Accède aux fonctionnalités de dessin d'un affichage vidéo qui ne sont pas directement accessibles via le Graphics Device Interface \(GDI\).|  
|[CDC::DrawFocusRect](../Topic/CDC::DrawFocusRect.md)|Dessine un rectangle dans le style utilisé pour indiquer le focus.|  
|[CDC::DrawFrameControl](../Topic/CDC::DrawFrameControl.md)|Dessinez un contrôle image.|  
|[CDC::DrawIcon](../Topic/CDC::DrawIcon.md)|Dessine une icône.|  
|[CDC::DrawState](../Topic/CDC::DrawState.md)|Affiche une image et applique un effet visuel pour indiquer un rapport.|  
|[CDC::DrawText](../Topic/CDC::DrawText.md)|Dessine du texte mis en forme dans le rectangle spécifié.|  
|[CDC::DrawTextEx](../Topic/CDC::DrawTextEx.md)|Dessine du texte mis en forme dans le rectangle spécifié à l'aide de les formats supplémentaires.|  
|[CDC::Ellipse](../Topic/CDC::Ellipse.md)|Dessine une ellipse.|  
|[CDC::EndDoc](../Topic/CDC::EndDoc.md)|Effectue un travail d'impression démarrée par la fonction membre d' `StartDoc` .|  
|[CDC::EndPage](../Topic/CDC::EndPage.md)|Informe le pilote de périphérique qu'une page termine.|  
|[CDC::EndPath](../Topic/CDC::EndPath.md)|Ferme une parenthèse de chemin d'accès et sélectionne le chemin défini par la parenthèse dans le contexte de périphérique.|  
|[CDC::EnumObjects](../Topic/CDC::EnumObjects.md)|Énumère les stylets et des pinceaux disponibles dans un contexte de périphérique.|  
|[CDC::Escape](../Topic/CDC::Escape.md)|Permet aux applications d'accéder aux fonctionnalités qui ne sont pas directement à partir d'un appareil particulier à GDI.  Permet également l'accès aux fonctions d'échappement windows.  Les appels d'échappement effectuées par une application sont traduits et envoyés au pilote de périphérique.|  
|[CDC::ExcludeClipRect](../Topic/CDC::ExcludeClipRect.md)|Crée une zone de découpage qui inclut la région de découpage existante moins le rectangle spécifié.|  
|[CDC::ExcludeUpdateRgn](../Topic/CDC::ExcludeUpdateRgn.md)|Empêché le dessin dans les zones non valides d'une fenêtre en excluant une zone mise à jour dans la fenêtre d'une zone de découpage.|  
|[CDC::ExtFloodFill](../Topic/CDC::ExtFloodFill.md)|Remplit la zone de pinceau actuel.  Fournit plus de flexibilité que la fonction membre de [CDC::FloodFill](../Topic/CDC::FloodFill.md) .|  
|[CDC::ExtTextOut](../Topic/CDC::ExtTextOut.md)|Écrit une chaîne dans une zone rectangulaire à l'aide de la police sélectionnée.|  
|[CDC::FillPath](../Topic/CDC::FillPath.md)|Ferme les figures ouvertes dans le chemin d'accès actuel et remplit intérieur de le tracé à l'aide de le mode actuel de pinceau et de remplissage de polygones.|  
|[CDC::FillRect](../Topic/CDC::FillRect.md)|Remplit le rectangle donné à l'aide d'un pinceau spécifique.|  
|[CDC::FillRgn](../Topic/CDC::FillRgn.md)|Remplit une zone spécifique du pinceau spécifié.|  
|[CDC::FillSolidRect](../Topic/CDC::FillSolidRect.md)|Remplit le rectangle de couleur unie.|  
|[CDC::FlattenPath](../Topic/CDC::FlattenPath.md)|Transforme les courbes dans le chemin d'accès sélectionné dans le contexte actuel du périphérique, et transforme chaque courbe en une séquence de lignes.|  
|[CDC::FloodFill](../Topic/CDC::FloodFill.md)|Remplit la zone de pinceau actuel.|  
|[CDC::FrameRect](../Topic/CDC::FrameRect.md)|Dessine une bordure autour d'un rectangle.|  
|[CDC::FrameRgn](../Topic/CDC::FrameRgn.md)|Dessine une bordure autour d'une zone spécifique à l'aide d'un pinceau.|  
|[CDC::FromHandle](../Topic/CDC::FromHandle.md)|Retourne un pointeur vers un objet d' `CDC` une fois donné un handle vers un contexte de périphérique.  Si un objet d' `CDC` n'est pas attaché au handle, un objet temporaire d' `CDC` est créé et joint.|  
|[CDC::GetArcDirection](../Topic/CDC::GetArcDirection.md)|Retourne la direction actuelle de l'arc pour le contexte de périphérique.|  
|[CDC::GetAspectRatioFilter](../Topic/CDC::GetAspectRatioFilter.md)|Extrait la configuration du filtre actif de respect des proportions.|  
|[CDC::GetBkColor](../Topic/CDC::GetBkColor.md)|Extrait la couleur d'arrière\-plan actuelle.|  
|[CDC::GetBkMode](../Topic/CDC::GetBkMode.md)|Récupère le mode arrière\-plan.|  
|[CDC::GetBoundsRect](../Topic/CDC::GetBoundsRect.md)|Retourne le rectangle englobant accumulé par courant pour le contexte spécifié de périphérique.|  
|[CDC::GetBrushOrg](../Topic/CDC::GetBrushOrg.md)|Récupère l'origine du pinceau actuel.|  
|[CDC::GetCharABCWidths](../Topic/CDC::GetCharABCWidths.md)|Extrait la largeur, en unités logiques, de caractères consécutifs dans une plage donnée de la police actuelle.|  
|[CDC::GetCharABCWidthsI](../Topic/CDC::GetCharABCWidthsI.md)|Extrait la largeur, en unités logiques, d'index de glyphe consécutifs dans une plage spécifiée de polices TrueType actuelle.|  
|[CDC::GetCharacterPlacement](../Topic/CDC::GetCharacterPlacement.md)|Extrait de différents types d'informations sur une chaîne.|  
|[CDC::GetCharWidth](../Topic/CDC::GetCharWidth.md)|Récupère les largeurs fractionnaires des caractères consécutifs dans une plage donnée de la police actuelle.|  
|[CDC::GetCharWidthI](../Topic/CDC::GetCharWidthI.md)|Récupère les largeurs, dans les coordonnées logiques, des index de glyphe consécutifs dans une plage spécifiée de la police actuelle.|  
|[CDC::GetClipBox](../Topic/CDC::GetClipBox.md)|Récupère les dimensions du rectangle englobant le plus serré autour de les limites actuelle de découpage.|  
|[CDC::GetColorAdjustment](../Topic/CDC::GetColorAdjustment.md)|Récupère les valeurs de réglage des couleurs pour le contexte de périphérique.|  
|[CDC::GetCurrentBitmap](../Topic/CDC::GetCurrentBitmap.md)|Retourne un pointeur vers l'objet actuellement sélectionné d' `CBitmap` .|  
|[CDC::GetCurrentBrush](../Topic/CDC::GetCurrentBrush.md)|Retourne un pointeur vers l'objet actuellement sélectionné d' `CBrush` .|  
|[CDC::GetCurrentFont](../Topic/CDC::GetCurrentFont.md)|Retourne un pointeur vers l'objet actuellement sélectionné d' `CFont` .|  
|[CDC::GetCurrentPalette](../Topic/CDC::GetCurrentPalette.md)|Retourne un pointeur vers l'objet actuellement sélectionné d' `CPalette` .|  
|[CDC::GetCurrentPen](../Topic/CDC::GetCurrentPen.md)|Retourne un pointeur vers l'objet actuellement sélectionné d' `CPen` .|  
|[CDC::GetCurrentPosition](../Topic/CDC::GetCurrentPosition.md)|Extrait la position actuelle du stylet \(dans les coordonnées logiques\).|  
|[CDC::GetDCBrushColor](../Topic/CDC::GetDCBrushColor.md)|Extrait la couleur actuelle du pinceau.|  
|[CDC::GetDCPenColor](../Topic/CDC::GetDCPenColor.md)|Extrait la couleur du stylet actuelle.|  
|[CDC::GetDeviceCaps](../Topic/CDC::GetDeviceCaps.md)|Récupère un type spécifié d'informations spécifiques à l'appareil sur les fonctions données d'un périphérique d'affichage.|  
|[CDC::GetFontData](../Topic/CDC::GetFontData.md)|Récupère des informations métriques de la police à partir d'un fichier de police évolutif.  Les informations à récupérer sont identifiées en spécifiant un offset dans le fichier de police et la longueur des informations à retourner.|  
|[CDC::GetFontLanguageInfo](../Topic/CDC::GetFontLanguageInfo.md)|Retourne des informations sur la police sélectionnée pour le contexte d'affichage spécifié.|  
|[CDC::GetGlyphOutline](../Topic/CDC::GetGlyphOutline.md)|Extrait la courbe ou la bitmap d'ensemble pour un caractère d'ensemble de la police actuelle.|  
|[CDC::GetGraphicsMode](../Topic/CDC::GetGraphicsMode.md)|Récupère le mode graphique actuel du contexte spécifié de périphérique.|  
|[CDC::GetHalftoneBrush](../Topic/CDC::GetHalftoneBrush.md)|Récupère un pinceau en demi\-teintes.|  
|[CDC::GetKerningPairs](../Topic/CDC::GetKerningPairs.md)|Récupère les règles de crénage de caractères pour la police actuellement sélectionnée dans le contexte spécifié de périphérique.|  
|[CDC::GetLayout](../Topic/CDC::GetLayout.md)|Extrait la disposition d'un contexte \(DC\) de périphérique.  La disposition peut être de gauche à droite \(valeur par défaut\) ou de droite à gauche \(réfléchi\).|  
|[CDC::GetMapMode](../Topic/CDC::GetMapMode.md)|Récupère le mode de mappage actuel.|  
|[CDC::GetMiterLimit](../Topic/CDC::GetMiterLimit.md)|Retourne la limite de mitre pour le contexte de périphérique.|  
|[CDC::GetNearestColor](../Topic/CDC::GetNearestColor.md)|Extrait la plus proche couleur logique à une couleur logique spécifique à l'appareil donné peut représenter.|  
|[CDC::GetOutlineTextMetrics](../Topic/CDC::GetOutlineTextMetrics.md)|Récupère des informations métriques de la police des polices truetype.|  
|[CDC::GetOutputCharWidth](../Topic/CDC::GetOutputCharWidth.md)|Récupère les largeurs des caractères à un groupe consécutif de caractères de la police actuelle de l'utilisation du contexte de périphérique de sortie.|  
|[CDC::GetOutputTabbedTextExtent](../Topic/CDC::GetOutputTabbedTextExtent.md)|Calcule la largeur et la hauteur d'une chaîne dans le contexte de périphérique de sortie.|  
|[CDC::GetOutputTextExtent](../Topic/CDC::GetOutputTextExtent.md)|Calcule la largeur et la hauteur d'une ligne de texte dans le contexte de périphérique de sortie à l'aide de la police actuelle pour déterminer les dimensions.|  
|[CDC::GetOutputTextMetrics](../Topic/CDC::GetOutputTextMetrics.md)|Récupère les mesures de la police actuel du contexte de périphérique de sortie.|  
|[CDC::GetPath](../Topic/CDC::GetPath.md)|Récupère les coordonnées définissant des points de terminaison les lignes et les points de contrôle de courbes trouvé dans le chemin d'accès qui est sélectionné dans le contexte de périphérique.|  
|[CDC::GetPixel](../Topic/CDC::GetPixel.md)|Récupère la valeur de couleur RVB du pixel au point spécifié.|  
|[CDC::GetPolyFillMode](../Topic/CDC::GetPolyFillMode.md)|Extrait l'état actuel de remplissage de polygones.|  
|[CDC::GetROP2](../Topic/CDC::GetROP2.md)|Récupère le mode dessin actuelle.|  
|[CDC::GetSafeHdc](../Topic/CDC::GetSafeHdc.md)|Retourne [CDC::m\_hDC](../Topic/CDC::m_hDC.md), le contexte de périphérique de sortie.|  
|[CDC::GetStretchBltMode](../Topic/CDC::GetStretchBltMode.md)|Récupère le mode bitmap\- d'étirement actuel.|  
|[CDC::GetTabbedTextExtent](../Topic/CDC::GetTabbedTextExtent.md)|Calcule la largeur et la hauteur d'une chaîne dans le contexte de périphérique d'attribut.|  
|[CDC::GetTextAlign](../Topic/CDC::GetTextAlign.md)|Récupère les balises d'alignement de texte.|  
|[CDC::GetTextCharacterExtra](../Topic/CDC::GetTextCharacterExtra.md)|Extrait la configuration actuelle pour la quantité d'espacement des caractères.|  
|[CDC::GetTextColor](../Topic/CDC::GetTextColor.md)|Extrait la couleur actuelle de texte.|  
|[CDC::GetTextExtent](../Topic/CDC::GetTextExtent.md)|Calcule la largeur et la hauteur d'une ligne de texte dans le contexte de périphérique d'attribut à l'aide de la police actuelle pour déterminer les dimensions.|  
|[CDC::GetTextExtentExPointI](../Topic/CDC::GetTextExtentExPointI.md)|Récupère le nombre de caractères dans une chaîne spécifiée qui entrera dans un espace spécifié et remplit tableau d'étendue de texte pour chacun de ces caractères.|  
|[CDC::GetTextExtentPointI](../Topic/CDC::GetTextExtentPointI.md)|Extrait la largeur et la hauteur du tableau spécifiée d'index de glyphe.|  
|[CDC::GetTextFace](../Topic/CDC::GetTextFace.md)|Copie le nom de police de la police actuelle dans une mémoire tampon comme une chaîne terminée par le caractère NULL.|  
|[CDC::GetTextMetrics](../Topic/CDC::GetTextMetrics.md)|Récupère les mesures de la police actuel du contexte de périphérique d'attribut.|  
|[CDC::GetViewportExt](../Topic/CDC::GetViewportExt.md)|Récupère le x et les étendues y de la fenêtre d'affichage.|  
|[CDC::GetViewportOrg](../Topic/CDC::GetViewportOrg.md)|Récupère les coordonnées x et y de l'origine de la fenêtre d'affichage.|  
|[CDC::GetWindow](../Topic/CDC::GetWindow.md)|Retourne la fenêtre associée au contexte de périphérique d'affichage.|  
|[CDC::GetWindowExt](../Topic/CDC::GetWindowExt.md)|Récupère le x et les étendues y de la fenêtre associée.|  
|[CDC::GetWindowOrg](../Topic/CDC::GetWindowOrg.md)|Récupère les coordonnées x et y de la fenêtre associée.|  
|[CDC::GetWorldTransform](../Topic/CDC::GetWorldTransform.md)|Extrait la transformation de page actuelle espace de Worldspace.|  
|[CDC::GradientFill](../Topic/CDC::GradientFill.md)|Remplit le rectangle et les structures de triangle avec graduer couleurs.|  
|[CDC::GrayString](../Topic/CDC::GrayString.md)|Draws est grisé le texte \(grisé\) à l'emplacement donné.|  
|[CDC::HIMETRICtoDP](../Topic/CDC::HIMETRICtoDP.md)|Unités HIMETRIC de convertis en unités.|  
|[CDC::HIMETRICtoLP](../Topic/CDC::HIMETRICtoLP.md)|Unités HIMETRIC de convertis en unités logiques.|  
|[CDC::IntersectClipRect](../Topic/CDC::IntersectClipRect.md)|Crée une zone de découpage en signe plus constituée par l'intersection de la zone active et d'un rectangle.|  
|[CDC::InvertRect](../Topic/CDC::InvertRect.md)|Inverse le contenu d'un rectangle.|  
|[CDC::InvertRgn](../Topic/CDC::InvertRgn.md)|Inverse les couleurs dans la zone.|  
|[CDC::IsPrinting](../Topic/CDC::IsPrinting.md)|Détermine si le contexte de périphérique est utilisé pour imprimer.|  
|[CDC::LineTo](../Topic/CDC::LineTo.md)|Dessine une ligne de la position actuelle jusqu'à, mais sans, un point.|  
|[CDC::LPtoDP](../Topic/CDC::LPtoDP.md)|Convertit les unités logiques dans des unités.|  
|[CDC::LPtoHIMETRIC](../Topic/CDC::LPtoHIMETRIC.md)|Convertit les unités logiques dans les unités HIMETRIC.|  
|[CDC::MaskBlt](../Topic/CDC::MaskBlt.md)|Combine des données couleur de la source et les bitmaps de destination à l'aide de le masque et l'opération raster donnés.|  
|[CDC::ModifyWorldTransform](../Topic/CDC::ModifyWorldTransform.md)|Modifie la transformation universelle pour un contexte de périphérique à l'état spécifié.|  
|[CDC::MoveTo](../Topic/CDC::MoveTo.md)|Déplace la position actuelle.|  
|[CDC::OffsetClipRgn](../Topic/CDC::OffsetClipRgn.md)|Déplace la région de découpage du périphérique donné.|  
|[CDC::OffsetViewportOrg](../Topic/CDC::OffsetViewportOrg.md)|Modifie l'origine de la fenêtre d'affichage par rapport à les détails de l'origine de la fenêtre d'affichage actuelle.|  
|[CDC::OffsetWindowOrg](../Topic/CDC::OffsetWindowOrg.md)|Modifie l'origine de la fenêtre rapport à les coordonnées d'origine actuelle de la fenêtre.|  
|[CDC::PaintRgn](../Topic/CDC::PaintRgn.md)|Remplit la zone de pinceau sélectionné.|  
|[CDC::PatBlt](../Topic/CDC::PatBlt.md)|Crée un modèle binaire.|  
|[CDC::Pie](../Topic/CDC::Pie.md)|Dessine une forme secteur\- shim.|  
|[CDC::PlayMetaFile](../Topic/CDC::PlayMetaFile.md)|Lit le contenu du métafichier spécifié sur le périphérique donné.  La version améliorée d' `PlayMetaFile` affiche l'image stockée dans le métafichier donné d'améliorer\- format.  Métafichier peut être lu plusieurs fois.|  
|[CDC::PlgBlt](../Topic/CDC::PlgBlt.md)|Exécute un transfert par bloc de bits des bits des données couleur du rectangle spécifié dans le contexte du périphérique source au parallélogramme spécifié dans le contexte donné de périphérique.|  
|[CDC::PolyBezier](../Topic/CDC::PolyBezier.md)|Dessine un ou plusieurs splines de Bézier.  La position actuelle n'est ni utilisée est mise à jour.|  
|[CDC::PolyBezierTo](../Topic/CDC::PolyBezierTo.md)|Dessine un ou plusieurs splines de Bézier, et déplace la position actuelle au point de terminaison du dernier spline de Bézier.|  
|[CDC::PolyDraw](../Topic/CDC::PolyDraw.md)|Dessine un ensemble de segments et de splines de Bézier de ligne.  Cette fonction met à jour la position actuelle.|  
|[CDC::Polygon](../Topic/CDC::Polygon.md)|Dessine un polygone deux ou plusieurs composants se passe \(les sommets\) connecté par des lignes.|  
|[CDC::Polyline](../Topic/CDC::Polyline.md)|Dessine un ensemble de segments de ligne reliant les points spécifiés.|  
|[CDC::PolylineTo](../Topic/CDC::PolylineTo.md)|Dessine un ou plusieurs lignes droites et déplace la position actuelle au point de terminaison de la dernière ligne.|  
|[CDC::PolyPolygon](../Topic/CDC::PolyPolygon.md)|Crée deux ou plusieurs polygones qui sont remplis avec l'état actuel de remplissage de polygones.  Les polygones peuvent être disjoignent ils peuvent se chevaucher.|  
|[CDC::PolyPolyline](../Topic/CDC::PolyPolyline.md)|Dessine plusieurs série de segments de ligne connectés.  La position actuelle n'est ni utilisée est mise à jour par cette fonction.|  
|[CDC::PtVisible](../Topic/CDC::PtVisible.md)|Spécifie si le point donné se trouve dans la région de découpage.|  
|[CDC::RealizePalette](../Topic/CDC::RealizePalette.md)|Mappe les entrées de la palette dans la palette logique actuelle à la palette système.|  
|[CDC::Rectangle](../Topic/CDC::Rectangle.md)|Dessine un rectangle à l'aide de le stylet actuel et le remplit avec le pinceau actuel.|  
|[CDC::RectVisible](../Topic/CDC::RectVisible.md)|Détermine si une partie du rectangle donné se trouve en dessous de la zone de découpage.|  
|[CDC::ReleaseAttribDC](../Topic/CDC::ReleaseAttribDC.md)|Libère `m_hAttribDC`, le contexte de périphérique d'attribut.|  
|[CDC::ReleaseOutputDC](../Topic/CDC::ReleaseOutputDC.md)|Libère `m_hDC`, le contexte de périphérique de sortie.|  
|[CDC::ResetDC](../Topic/CDC::ResetDC.md)|Met à jour le contexte de périphérique d' `m_hAttribDC` .|  
|[CDC::RestoreDC](../Topic/CDC::RestoreDC.md)|Restaure le contexte de périphérique à un état enregistré précédent avec `SaveDC`.|  
|[CDC::RoundRect](../Topic/CDC::RoundRect.md)|Dessine un rectangle à angles arrondis à l'aide de le stylet actuel et remplis avec le pinceau actuel.|  
|[CDC::SaveDC](../Topic/CDC::SaveDC.md)|Enregistre l'état actuel du contexte de périphérique.|  
|[CDC::ScaleViewportExt](../Topic/CDC::ScaleViewportExt.md)|Modifie l'étendue de la fenêtre d'affichage par rapport à les valeurs actuelles.|  
|[CDC::ScaleWindowExt](../Topic/CDC::ScaleWindowExt.md)|Modifie les étendues de la fenêtre rapport à les valeurs actuelles.|  
|[CDC::ScrollDC](../Topic/CDC::ScrollDC.md)|Fait défiler un rectangle de bits horizontalement et verticalement.|  
|[CDC::SelectClipPath](../Topic/CDC::SelectClipPath.md)|Sélectionne le chemin d'accès actuel comme une région de découpage pour le contexte de périphérique, associant la zone à une zone de découpage existante à l'aide de le mode spécifié.|  
|[CDC::SelectClipRgn](../Topic/CDC::SelectClipRgn.md)|Combine la zone donnée à la zone de découpage actuelle à l'aide de le mode spécifié.|  
|[CDC::SelectObject](../Topic/CDC::SelectObject.md)|Sélectionne GDI dessinant l'objet comme un stylet.|  
|[CDC::SelectPalette](../Topic/CDC::SelectPalette.md)|Sélectionne la palette logique.|  
|[CDC::SelectStockObject](../Topic/CDC::SelectStockObject.md)|Sélectionne une des stylets, les pinceaux, ou des polices d'actions prédéfinies fournies par windows.|  
|[CDC::SetAbortProc](../Topic/CDC::SetAbortProc.md)|Définit une fonction de rappel fournie programmeur que les appels de fenêtres si un travail d'impression doit être interrompue.|  
|[CDC::SetArcDirection](../Topic/CDC::SetArcDirection.md)|Définit le sens de dessin à utiliser pour l'arc et le rectangle s'exécute.|  
|[CDC::SetAttribDC](../Topic/CDC::SetAttribDC.md)|Définit `m_hAttribDC`, le contexte de périphérique d'attribut.|  
|[CDC::SetBkColor](../Topic/CDC::SetBkColor.md)|Définit la couleur d'arrière\-plan actuelle.|  
|[CDC::SetBkMode](../Topic/CDC::SetBkMode.md)|Définit le mode arrière\-plan.|  
|[CDC::SetBoundsRect](../Topic/CDC::SetBoundsRect.md)|Contrôle l'accumulation des informations de rectangle englobant de le contexte spécifié de périphérique.|  
|[CDC::SetBrushOrg](../Topic/CDC::SetBrushOrg.md)|Spécifie l'origine du premier pinceau sélectionné dans un contexte de périphérique.|  
|[CDC::SetColorAdjustment](../Topic/CDC::SetColorAdjustment.md)|Définit les valeurs de réglage des couleurs pour le contexte de périphérique à l'aide de les valeurs spécifiées.|  
|[CDC::SetDCBrushColor](../Topic/CDC::SetDCBrushColor.md)|Définit la couleur actuelle du pinceau.|  
|[CDC::SetDCPenColor](../Topic/CDC::SetDCPenColor.md)|Définit la couleur du stylet actuelle.|  
|[CDC::SetGraphicsMode](../Topic/CDC::SetGraphicsMode.md)|Définit le mode graphique actuel du contexte spécifié de périphérique.|  
|[CDC::SetLayout](../Topic/CDC::SetLayout.md)|Modifie la disposition d'un contexte \(DC\) de périphérique.|  
|[CDC::SetMapMode](../Topic/CDC::SetMapMode.md)|Définit le mode de mappage actuel.|  
|[CDC::SetMapperFlags](../Topic/CDC::SetMapperFlags.md)|Modifie l'algorithme que le mappeur de polices utilise lorsqu'il mappe les polices logiques des polices physiques.|  
|[CDC::SetMiterLimit](../Topic/CDC::SetMiterLimit.md)|Définit la limite de la longueur des jointures de mitre pour le contexte de périphérique.|  
|[CDC::SetOutputDC](../Topic/CDC::SetOutputDC.md)|Définit `m_hDC`, le contexte de périphérique de sortie.|  
|[CDC::SetPixel](../Topic/CDC::SetPixel.md)|Définit le pixel au point spécifié à l'approximation la plus proche de la couleur spécifiée.|  
|[CDC::SetPixelV](../Topic/CDC::SetPixelV.md)|Définit le pixel aux coordonnées spécifiées à l'approximation la plus proche de la couleur spécifiée.  `SetPixelV` est plus rapide que `SetPixel` car il n'a pas besoin de retourner la valeur de couleur du point réellement peint.|  
|[CDC::SetPolyFillMode](../Topic/CDC::SetPolyFillMode.md)|Définit le mode de remplissage de polygones.|  
|[CDC::SetROP2](../Topic/CDC::SetROP2.md)|Définit le mode dessin actuelle.|  
|[CDC::SetStretchBltMode](../Topic/CDC::SetStretchBltMode.md)|Définit le mode bitmap\- d'étirement.|  
|[CDC::SetTextAlign](../Topic/CDC::SetTextAlign.md)|Définit les balises d'alignement de texte.|  
|[CDC::SetTextCharacterExtra](../Topic/CDC::SetTextCharacterExtra.md)|Définit la quantité d'espacement des caractères.|  
|[CDC::SetTextColor](../Topic/CDC::SetTextColor.md)|Définit la couleur du texte.|  
|[CDC::SetTextJustification](../Topic/CDC::SetTextJustification.md)|Ajoute l'espace aux caractères de soulignement dans une chaîne.|  
|[CDC::SetViewportExt](../Topic/CDC::SetViewportExt.md)|Définit le x et les étendues y de la fenêtre d'affichage.|  
|[CDC::SetViewportOrg](../Topic/CDC::SetViewportOrg.md)|Définit l'origine de la fenêtre d'affichage.|  
|[CDC::SetWindowExt](../Topic/CDC::SetWindowExt.md)|Définit le x et les étendues y de la fenêtre associée.|  
|[CDC::SetWindowOrg](../Topic/CDC::SetWindowOrg.md)|Définit l'origine de la fenêtre du contexte de périphérique.|  
|[CDC::SetWorldTransform](../Topic/CDC::SetWorldTransform.md)|Définit Worldspace actuel à la transformation de page espace.|  
|[CDC::StartDoc](../Topic/CDC::StartDoc.md)|Informe le pilote de périphérique qu'une nouvelle travail d'impression démarre.|  
|[CDC::StartPage](../Topic/CDC::StartPage.md)|Informe le pilote de périphérique qu'une nouvelle page commence.|  
|[CDC::StretchBlt](../Topic/CDC::StretchBlt.md)|Entre une bitmap d'un rectangle source et le périphérique dans un rectangle de destination, d'étirement ou comprimant la bitmap si nécessaire en fonction de les dimensions du rectangle de destination.|  
|[CDC::StrokeAndFillPath](../Topic/CDC::StrokeAndFillPath.md)|Ferme les figures ouvertes dans un chemin d'accès, les types le plan du chemin d'accès à l'aide de le stylet actuel, et remplit son contrôle en utilisant le pinceau actuel.|  
|[CDC::StrokePath](../Topic/CDC::StrokePath.md)|Affiche le chemin d'accès spécifié à l'aide de le stylet actuel.|  
|[CDC::TabbedTextOut](../Topic/CDC::TabbedTextOut.md)|Écrit une chaîne de caractères à un emplacement spécifié, le développement des tabulations en valeurs spécifiées dans un tableau de caractères de tabulation.|  
|[CDC::TextOut](../Topic/CDC::TextOut.md)|Écrit une chaîne de caractères à un emplacement spécifié à l'aide de la police sélectionnée.|  
|[CDC::TransparentBlt](../Topic/CDC::TransparentBlt.md)|Transfère un bloc de bits de données couleur du contexte de périphérique source spécifié dans un contexte de périphérique de destination, en affichant une couleur spécifiée transparente dans la migration.|  
|[CDC::UpdateColors](../Topic/CDC::UpdateColors.md)|Met à jour la zone cliente du contexte de périphérique en correspondant à des couleurs actuelle dans la zone cliente de la palette système sur une base de pixel par pixel.|  
|[CDC::WidenPath](../Topic/CDC::WidenPath.md)|Redéfinit le chemin d'accès actuel en tant que zone qui est peinte si le chemin d'accès ne frottés à l'aide de le stylet actuellement sélectionné dans le contexte de périphérique.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDC::operator HDC](../Topic/CDC::operator%20HDC.md)|Récupère le handle du contexte de périphérique.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDC::m\_hAttribDC](../Topic/CDC::m_hAttribDC.md)|Le contexte de périphérique attributs utilisés par cet objet d' `CDC` .|  
|[CDC::m\_hDC](../Topic/CDC::m_hDC.md)|Le contexte de périphérique de sortie utilisé par cet objet d' `CDC` .|  
  
## Notes  
 L'objet d' `CDC` fournit les fonctions membres pour utiliser un contexte de périphérique, comme un écran ou une imprimante, ainsi que des membres pour utiliser un contexte d'affichage associé à la zone cliente d'une fenêtre.  
  
 Effectuez tout le dessin via les fonctions membres d'un objet d' `CDC` .  La classe fournit les fonctions membres pour les opérations de périphérique\- contexte, l'utilisation des outils de dessin, la sélection de type sécurisé d'objet de définition de données \(GDI\) Graphics Device Interface, et l'utilisation des couleurs et des palettes.  Il fournit également des fonctions membres pour les attributs de dessin d'obtention et de configuration, le mappage, l'exécution avec la fenêtre d'affichage, l'exécution avec l'étendue de la fenêtre, convertissant les coordonnées, vous travaillez avec des régions, le découpage, les lignes de dessin, et les formes simples de dessin, les points de suspension, et les polygones.  Les fonctions membres sont également données pour le dessin de texte, vous travaillez avec les polices, en utilisant échappe d'imprimante, le défilement, et lire des métafichiers.  
  
 Pour utiliser un objet d' `CDC` , construisez\- le, puis appelez ses fonctions membres qui les fonctions Windows parallèles qui utilisent des contextes de périphérique.  
  
> [!NOTE]
>  Sous Windows 95\/98, toutes les coordonnées d'écran sont limitées à 16 bits.  Par conséquent, `int` passé à une fonction membre d' `CDC` doit être localiser dans la plage – 32768 à 32767.  
  
 Pour les utilisations spécifiques, la bibliothèque MFC fournit plusieurs classes dérivées d' `CDC` .  `CPaintDC` encapsule des appels à `BeginPaint` et à `EndPaint`.  `CClientDC` gère un contexte d'affichage associé à la zone cliente d'une fenêtre.  `CWindowDC` gère un contexte d'affichage associé à une fenêtre entière, y compris son frame et.  `CMetaFileDC` associe un contexte de périphérique avec un métafichier.  
  
 `CDC` fournit deux fonctions membres, [GetLayout](../Topic/CDC::GetLayout.md) et [SetLayout](../Topic/CDC::SetLayout.md), pour annuler la disposition d'un contexte de périphérique, qui n'hérite pas sa disposition d'une fenêtre.  Une telle orientation de droite à gauche est nécessaire pour les applications écrites de cultures, telles que l'arabe ou en hébreu, où la disposition de caractère n'est pas la norme européenne.  
  
 `CDC` contient deux contextes de périphérique, [m\_hDC](../Topic/CDC::m_hDC.md) et [m\_hAttribDC](../Topic/CDC::m_hAttribDC.md), qui, sur la création d'un objet d' `CDC` , fait référence au même périphérique.  `CDC` dirige tous les appels GDI de sortie à `m_hDC` et la plupart des appels de GDI d'attribut à `m_hAttribDC`.  \(Un exemple d'appel d'attribut est `GetTextColor`, tandis que `SetTextColor` est un appel de sortie.\)  
  
 Par exemple, l'infrastructure utilise ces contextes de deux systèmes pour implémenter un objet d' `CMetaFileDC` qui envoie la sortie vers un métafichier en lisant les attributs d'un périphérique physique.  l'aperçu avant impression est implémenté dans l'infrastructure de la même façon.  Vous pouvez également utiliser les deux contextes de périphérique d'une manière similaire dans votre code spécifique à l'application.  
  
 Il arrive où vous pouvez avoir besoin d'informations métriques texte des contextes de périphérique d' `m_hDC` et d' `m_hAttribDC` .  Les paires suivantes de fonctions fournissent cette fonction :  
  
|Utilise le m\_hAttribDC|Utilise le m\_hDC|  
|-----------------------------|-----------------------|  
|[GetTextExtent](../Topic/CDC::GetTextExtent.md)|[GetOutputTextExtent](../Topic/CDC::GetOutputTextExtent.md)|  
|[GetTabbedTextExtent](../Topic/CDC::GetTabbedTextExtent.md)|[GetOutputTabbedTextExtent](../Topic/CDC::GetOutputTabbedTextExtent.md)|  
|[GetTextMetrics](../Topic/CDC::GetTextMetrics.md)|[GetOutputTextMetrics](../Topic/CDC::GetOutputTextMetrics.md)|  
|[GetCharWidth](../Topic/CDC::GetCharWidth.md)|[GetOutputCharWidth](../Topic/CDC::GetOutputCharWidth.md)|  
  
 Pour plus d'informations sur `CDC`, consultez [contextes de périphérique](../../mfc/device-contexts.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDC`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CPaintDC Class](../../mfc/reference/cpaintdc-class.md)   
 [CWindowDC Class](../../mfc/reference/cwindowdc-class.md)   
 [CClientDC Class](../../mfc/reference/cclientdc-class.md)   
 [CMetaFileDC Class](../../mfc/reference/cmetafiledc-class.md)