---
title: "Objets graphiques | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "HRGN"
  - "HFONT"
  - "HBITMAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bitmaps (C++), créer dans des contextes de périphérique"
  - "pinceaux, créer dans un contexte de périphérique"
  - "CBitmap (classe), HBITMAP (type de handle)"
  - "CBrush (classe), HBRUSH (type de handle)"
  - "CFont (classe), HFONT (type de handle)"
  - "CPalette (classe), HPALETTE (type de handle)"
  - "CPen (classe), HPEN (type de handle)"
  - "CRgn (classe), HRGN (type de handle)"
  - "contextes de périphérique, objets graphiques"
  - "dessiner, dans des contextes de périphérique"
  - "polices (C++), créer dans un contexte de périphérique"
  - "GDI (C++), classes d'objets graphiques"
  - "objets GDI (C++)"
  - "objets GDI (C++), classes d'objets graphiques"
  - "objets graphiques"
  - "objets graphiques, créer dans un contexte de périphérique"
  - "HBITMAP et classe CBitmap"
  - "HBRUSH et classe CBrush"
  - "HFONT et classe CFont"
  - "HPALETTE et classe CPalette"
  - "HPEN"
  - "HRGN"
  - "images (C++), objets graphiques"
  - "mémoire (C++), contextes d'affichage"
  - "MFC, objets graphiques"
  - "objets (C++), graphiques"
  - "objets (C++), objets graphiques"
  - "peinture et contexte de périphérique"
  - "objets de palette"
  - "palettes, créer dans un contexte de périphérique"
  - "objets Pen"
  - "stylets, créer dans un contexte de périphérique"
  - "objets de zone"
  - "régions, créer dans un contexte de périphérique"
ms.assetid: 41963b25-34b7-4343-8446-34ba516b83ca
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Objets graphiques
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows propose divers outils de dessin à utiliser dans des contextes de périphériques.  On trouve des stylets pour tracer des lignes, des pinceaux pour remplir des intérieurs et des polices pour dessiner du texte.  MFC propose des classes d'objets graphiques équivalentes aux outils de dessin de Windows.  Le tableau ci\-dessous présente les classes disponibles et les types de handle GDI \(Graphics Device Interface\) Windows équivalents.  
  
> [!NOTE]
>  GDI\+ est fourni avec Windows XP et est disponible sous forme de composant redistribuable pour Windows NT 4.0 SP6, Windows 2000, Windows 98 et Windows Me.  Pour télécharger le composant redistribuable le plus récent, consultez [http:\/\/www.microsoft.com\/msdownload\/platformsdk\/sdkupdate\/psdkredist.htm](http://www.microsoft.com/msdownload/platformsdk/sdkupdate/psdkredist.htm).  Pour plus d'informations, consultez la documentation du Kit de développement logiciel \(SDK\) GDI\+ dans MSDN : [http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/gdicpp\/GDIPlus\/GDIPlus.asp](http://msdn.microsoft.com/library/default.asp?url=/library/gdicpp/GDIPlus/GDIPlus.asp).  
  
 Cet article explique l'utilisation de ces classes d'objets graphiques :  
  
### Classes pour objets Windows GDI  
  
|Classe|Type de handle Windows|  
|------------|----------------------------|  
|[CPen](../mfc/reference/cpen-class.md)|`HPEN`|  
|[CBrush](../mfc/reference/cbrush-class.md)|`HBRUSH`|  
|[CFont](../mfc/reference/cfont-class.md)|**HFONT**|  
|[CBitmap](../mfc/reference/cbitmap-class.md)|`HBITMAP`|  
|[CPalette](../mfc/reference/cpalette-class.md)|`HPALETTE`|  
|[CRgn](../mfc/reference/crgn-class.md)|**HRGN**|  
  
> [!NOTE]
>  La classe [CImage](../atl-mfc-shared/reference/cimage-class.md) assure une prise en charge améliorée des images bitmap.  
  
 À chaque classe d'objets graphiques de la bibliothèque de classes correspond un constructeur qui vous permet de créer des objets graphiques de cette classe, que vous devez ensuite initialiser avec la fonction de création appropriée, comme `CreatePen`.  
  
 À chaque classe d'objets graphiques de la bibliothèque de classes correspond un opérateur de conversion de type \(transtypage\) chargé de convertir un objet MFC en handle Windows associé.  Le handle obtenu est valide tant que l'objet associé ne le détache pas.  Pour détacher le handle, utilisez la fonction membre **Detach** de l'objet.  
  
 Le code suivant convertit un `CPen` objet en handle Windows :  
  
 [!code-cpp[NVC_MFCDocViewSDI#5](../mfc/codesnippet/CPP/graphic-objects_1.cpp)]  
  
#### Pour créer un objet graphique dans un contexte de périphérique  
  
1.  Définissez un objet graphique sur le frame de pile.  Initialisez l'objet avec la fonction de création propre au type, par exemple, `CreatePen`.  Vous pouvez aussi initialiser l'objet dans le constructeur.  Consultez la rubrique qui décrit les [méthodes de création en une ou deux étapes](../mfc/one-stage-and-two-stage-construction-of-objects.md), dans laquelle vous trouverez un exemple de code.  
  
2.  [Sélectionnez l'objet dans le contexte de périphérique actuel](../mfc/selecting-a-graphic-object-into-a-device-context.md), en enregistrant l'ancien objet graphique qui était sélectionné auparavant.  
  
3.  Quand vous en avez terminé avec l'objet graphique actuel, sélectionnez à nouveau l'ancien objet graphique dans le contexte de périphérique pour restaurer son état.  
  
4.  Autorisez la suppression automatique de l'objet graphique alloué par le frame dès qu'il est hors de portée.  
  
> [!NOTE]
>  Si vous prévoyez d'utiliser un objet graphique de façon récurrente, vous pouvez l'allouer une fois et le sélectionner dans un contexte de périphérique chaque fois que vous en avez besoin.  Veillez à supprimer cet objet dès que vous n'en avez plus besoin.  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Construction d'objets graphiques en une ou deux étapes](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [Exemple de construction d'un stylet en une ou deux étapes](../mfc/one-stage-and-two-stage-construction-of-objects.md)  
  
-   [Sélection d'un objet graphique dans un contexte de périphérique](../mfc/selecting-a-graphic-object-into-a-device-context.md)  
  
-   [Contextes de périphérique](../mfc/device-contexts.md)  
  
-   [Limitations de CImage avec les systèmes d'exploitation antérieurs](../mfc/cimage-limitations-with-earlier-operating-systems.md)  
  
## Voir aussi  
 [Objets fenêtres](../mfc/window-objects.md)