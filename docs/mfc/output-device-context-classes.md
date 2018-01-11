---
title: "Sortie (contexte de périphérique) Classes | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.output
dev_langs: C++
helpviewer_keywords:
- device contexts [MFC], classes
- screen output classes [MFC]
- printing classes [MFC]
- window drawing classes [MFC]
- painting classes [MFC]
- output classes [MFC]
ms.assetid: 35fd6435-a38e-42c6-a3fa-cd6f39370fc3
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: db7080c263ee6e98d458381d59446263490dfd7a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="output-device-context-classes"></a>Classes de sortie (contexte de périphérique)
Ces classes encapsulent les différents types de contextes de périphérique disponibles dans Windows.  
  
 La plupart des classes suivantes encapsulent un handle vers un contexte de périphérique Windows. Un contexte de périphérique est un objet de Windows qui contient des informations sur les attributs de dessin d’un périphérique tel qu’un écran ou une imprimante. Tous les appels de dessin sont effectués via un objet de contexte de périphérique. Autres classes dérivées de `CDC` encapsulent des fonctionnalités spécialisées de contexte de périphérique, y compris la prise en charge des métafichiers Windows.  
  
 [CAPTURE DE DONNÉES MODIFIÉES](../mfc/reference/cdc-class.md)  
 La classe de base pour les contextes de périphérique. Utilisés directement pour l’accès à l’affichage complet et pour accéder aux contextes de nondisplay, tels que des imprimantes.  
  
 [CPaintDC](../mfc/reference/cpaintdc-class.md)  
 Utilisé dans un contexte d’affichage `OnPaint` les fonctions membres de windows. Appelle automatiquement `BeginPaint` lors de la construction et `EndPaint` lors de la destruction.  
  
 [CClientDC](../mfc/reference/cclientdc-class.md)  
 Un contexte d’affichage pour les zones clientes de windows. Utilisé, par exemple, pour dessiner dans une réponse immédiate aux événements de souris.  
  
 [CWindowDC](../mfc/reference/cwindowdc-class.md)  
 Un contexte d’affichage pour tout entier de windows, y compris les zones clientes et client.  
  
 [CMetaFileDC](../mfc/reference/cmetafiledc-class.md)  
 Un contexte de périphérique pour les métafichiers Windows. Un métafichier Windows contient une séquence de commandes graphics device interface (GDI) qui peuvent être relues pour créer une image. Les appels aux fonctions de membre d’un `CMetaFileDC` sont enregistrées dans un métafichier.  
  
## <a name="related-classes"></a>Classes associées  
 [CPoint](../atl-mfc-shared/reference/cpoint-class.md)  
 Contient les paires de coordonnées (x, y).  
  
 [CSize](../atl-mfc-shared/reference/csize-class.md)  
 Contient la distance, les positions relatives ou les paires de valeurs.  
  
 [CRect](../atl-mfc-shared/reference/crect-class.md)  
 Contient les coordonnées de zones rectangulaires.  
  
 [CRgn](../mfc/reference/crgn-class.md)  
 Encapsule une région GDI pour la manipulation d’une zone elliptique ou polygonale irrégulière dans une fenêtre. Utilisée conjointement avec les fonctions membres de l’extrait de la classe `CDC`.  
  
 [CRectTracker](../mfc/reference/crecttracker-class.md)  
 Affiche et gère l’interface utilisateur pour le redimensionnement et le déplacement d’objets rectangulaires.  
  
 [CColorDialog](../mfc/reference/ccolordialog-class.md)  
 Fournit une boîte de dialogue standard permettant de sélectionner une couleur.  
  
 [CFontDialog](../mfc/reference/cfontdialog-class.md)  
 Fournit une boîte de dialogue standard pour la sélection d’une police.  
  
 [CPrintDialog](../mfc/reference/cprintdialog-class.md)  
 Fournit une boîte de dialogue standard pour l’impression d’un fichier.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../mfc/class-library-overview.md)

